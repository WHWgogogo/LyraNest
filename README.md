# LyraNest（律巢）

LyraNest（律巢）是一套自托管音乐播放与管理服务，面向个人 NAS、家庭服务器和局域网音乐库场景。本仓库是公开发行仓库，用于提供客户端安装包、服务端 Docker 部署文件和版本发布记录，不包含完整商业/私有版源代码。

## 功能简介

- **音乐库播放**：扫描服务端音乐库，在 Windows、Android 与网页端播放歌曲。
- **收藏与歌单**：支持收藏歌曲、播放列表和基础歌单管理。
- **歌词体验**：支持歌词显示、歌词跳转、桌面歌词以及逐曲歌词偏移调整。
- **离线下载**：客户端下载歌曲、封面与歌词，断网时也能播放已下载内容。
- **多端使用**：桌面端、移动端、网页端共享同一套服务端数据。
- **服务端部署**：提供 Docker 镜像与 Docker Compose 文件，适合 NAS 或 Linux 服务器部署。

## 下载最新版

- [Android ARM64 APK](https://github.com/WHWgogogo/LyraNest/releases/latest/download/LyraNest-Android-arm64.apk)
- [Windows x64 ZIP](https://github.com/WHWgogogo/LyraNest/releases/latest/download/LyraNest-Windows-x64.zip)
- [Docker Compose](https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml)
- [Docker 环境变量示例](https://github.com/WHWgogogo/LyraNest/releases/latest/download/LyraNest.env.example)
- [SHA-256 校验值](https://github.com/WHWgogogo/LyraNest/releases/latest/download/SHA256SUMS.txt)

## Docker 镜像

服务端镜像统一命名为：

```text
ghcr.io/whwgogogo/lyranest-server:0.1.8
```

也可以使用最新版标签：

```text
ghcr.io/whwgogogo/lyranest-server:latest
```

> Docker/OCI 镜像仓库名要求小写，因此镜像拉取名使用 `lyranest-server`；发行展示名称保持为 `LyraNest-server-0.1.8`。

## Docker Compose 完整配置

下面是发行仓库中的完整 `docker-compose.yml`，注释标出了常用修改项：

```yaml
# LyraNest ??? Docker Compose ??
# ???? .env.example ? .env?????? .env ??????

services:
  lyranest:
    # ????? LYRANEST_VERSION ???
    # ???????0.1.8?????????latest??? least??
    image: ghcr.io/whwgogogo/lyranest-server:${LYRANEST_VERSION:-0.1.8}
    container_name: lyranest
    restart: unless-stopped
    init: true

    # ??????? Linux AMD64?ARM ???????????????
    platform: linux/amd64
    pull_policy: always

    # ??????????? UID/GID???? id -u ? id -g ???
    user: ${PUID:-1000}:${PGID:-1000}

    # ?????????????????? 256 MB??? 128 MB?
    mem_limit: ${SERVER_MEMORY_LIMIT:-256m}
    mem_reservation: ${SERVER_MEMORY_RESERVATION:-128m}
    security_opt:
      - no-new-privileges:true

    environment:
      # ?????????????????
      SERVER_ADDR: :8080
      MUSIC_LIBRARY_DIR: /music
      MUSIC_DATA_DIR: /data
      GOMEMLIMIT: ${GOMEMLIMIT:-192MiB}
      GOGC: ${GOGC:-100}
      MUSICBRAINZ_USER_AGENT: ${MUSICBRAINZ_USER_AGENT:-LyraNest-server-0.1.8 (+https://github.com/WHWgogogo/LyraNest)}
      MUSICBRAINZ_BASE_URL: ${MUSICBRAINZ_BASE_URL:-https://musicbrainz.org}
      MUSICBRAINZ_TIMEOUT: ${MUSICBRAINZ_TIMEOUT:-20s}
      LOG_LEVEL: ${LOG_LEVEL:-info}
      SHUTDOWN_TIMEOUT: ${SHUTDOWN_TIMEOUT:-10s}
      AUTH_SESSION_TTL: ${AUTH_SESSION_TTL:-24h}
      HTTP_PROXY: ${HTTP_PROXY:-}
      HTTPS_PROXY: ${HTTPS_PROXY:-}
      NO_PROXY: ${NO_PROXY:-}

    ports:
      # ???????????? 8080 ??????
      # ?? SERVER_PORT=9090 ??????? http://?????:9090?
      - ${SERVER_PORT:-8080}:8080

    volumes:
      # ??????????????????????????????
      # ???????/mnt/music:/music:rw ? /volume1/music:/music:rw?
      - ${MUSIC_LIBRARY_HOST_DIR:-./music}:/music:rw
      # ?????????????????????
      - ${DATA_DIR:-./data}:/data:rw
      # ???????????
      - ${CACHE_DIR:-./cache}:/cache:rw

    healthcheck:
      test: ["CMD", "/usr/local/bin/music-player-server", "healthcheck"]
      interval: 30s
      timeout: 5s
      retries: 5
      start_period: 30s
```

## Docker Compose 部署

在 Linux 服务器上执行：

```bash
mkdir -p lyranest/{music,data,cache}
cd lyranest

curl -L -o docker-compose.yml \
  https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml
curl -L -o .env \
  https://github.com/WHWgogogo/LyraNest/releases/latest/download/LyraNest.env.example

docker compose pull
docker compose up -d
```

默认访问地址：

```text
http://服务器地址:8080
```

把音乐文件放入 `music/` 目录，服务端数据会保存到 `data/`，缓存保存到 `cache/`。

如果服务器用户的 UID/GID 不是 `1000:1000`，请在 `.env` 中把 `PUID`、`PGID` 改为以下命令的输出：

```bash
id -u
id -g
```

如需固定版本，在 `.env` 中设置：

```dotenv
LYRANEST_VERSION=0.1.8
```

如需跟随最新版，可以改为：

```dotenv
LYRANEST_VERSION=latest
```

升级时执行：

```bash
docker compose pull
docker compose up -d
```

## 版本管理

- 每个发行版永久保存在 `releases/<版本号>/`，后续版本不会覆盖旧版本文件。
- 每个发行版使用对应 Git 标签，例如 `v0.1.8`。
- README 中的下载链接使用 GitHub `releases/latest/download`，始终指向最新版。
- 固定版本镜像使用 `ghcr.io/whwgogogo/lyranest-server:<版本号>`。
- 最新版镜像使用 `ghcr.io/whwgogogo/lyranest-server:latest`。
- 发布前请使用对应版本目录中的 `SHA256SUMS.txt` 校验文件完整性。

## 当前版本

当前稳定版本：**0.1.8**

更新记录见 [`releases/0.1.8/CHANGELOG.md`](releases/0.1.8/CHANGELOG.md)。
