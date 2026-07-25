# LyraNest（律巢）

<p align="center">
  <img src="docs/images/lyranest-logo.png" alt="LyraNest Logo" width="150" />
</p>

<p align="center">一套面向个人 NAS、家庭服务器与局域网音乐库的自托管音乐服务。</p>

<p align="center">
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest"><img src="https://img.shields.io/github/v/release/WHWgogogo/LyraNest?display_name=tag&label=Release" alt="Latest Release" /></a>
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest"><img src="https://img.shields.io/badge/Platform-Android%20%7C%20Windows-4f46e5" alt="Platforms" /></a>
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml"><img src="https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white" alt="Docker Compose" /></a>
</p>

<p align="center">
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest">下载最新版</a> ·
  <a href="#docker-compose-部署">Docker 部署</a> ·
  <a href="releases/0.1.9/CHANGELOG.md">更新日志</a> ·
  <a href="https://github.com/WHWgogogo/LyraNest-Community">开源社区版</a>
</p>

> **发行版说明**：此仓库用于发布 LyraNest 的客户端安装包、Docker 部署配置与更新记录，不包含完整版本源代码。若需要开源、可自行构建的基础版本，请前往 [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)。

将音乐文件保存在自己的服务器、NAS 或电脑中，即可通过 Web、Windows 和 Android 客户端管理、播放并同步个人音乐库。

当前稳定版本：`0.1.9`

交流 QQ 群：`700454910`

## 0.1.9 更新摘要

- **曲库与服务端**：流式全量/增量扫描、可持久化热更新、曲库变动推送，以及更可靠的大曲库首次部署。
- **刮削与播放**：新增 JSON 刮削源和批量刮削工作台；自动下载与播放缓存分离，支持边播边缓存与离线播放。
- **客户端与 Web**：新增完整 Web 刮削页，完善批量操作、中文与响应式界面，并同步修复 Windows、Android、Web 与 fnOS 的多项问题。
- **Docker 与 fnOS**：Docker 改为只读挂载音乐库，运行数据与缓存单独持久化；fnOS FPK 同步升级至 `0.1.9`。

完整升级注意事项和更新内容请查看 [`releases/0.1.9/CHANGELOG.md`](releases/0.1.9/CHANGELOG.md)。

## 功能简介

- **多端音乐库**：Web、Windows、Android 共用服务端曲库、收藏、歌单与播放队列。
- **完整播放体验**：歌词展示与逐曲偏移调整、桌面歌词、播放模式、睡眠定时、播放列表定位。
- **离线下载**：下载歌曲、封面与歌词，在离线状态下浏览并播放已下载内容。
- **发现与报告**：每日推荐、猜你喜欢、听歌排行、听歌热力图与个人听歌统计。
- **曲库管理**：搜索、排序、批量操作、专辑与艺术家浏览，以及元数据刮削。
- **轻量部署**：Docker Compose 一键部署，支持音乐目录、数据目录、端口和内存限制配置。

## 界面预览

### 网页端

<p align="center">
  <img src="docs/images/1.png" alt="LyraNest Web 1.png" width="32%" />
  <img src="docs/images/2.png" alt="LyraNest Web 2.png" width="32%" />
  <img src="docs/images/3.png" alt="LyraNest Web 3.png" width="32%" />
</p>

<p align="center">
  <img src="docs/images/4.png" alt="LyraNest Web 4.png" width="32%" />
  <img src="docs/images/5.png" alt="LyraNest Web 5.png" width="32%" />
  <img src="docs/images/6.png" alt="LyraNest Web 6.png" width="32%" />
</p>

<p align="center">
  <img src="docs/images/7.png" alt="LyraNest Web 7.png" width="32%" />
  <img src="docs/images/8.png" alt="LyraNest Web 8.png" width="32%" />
  <img src="docs/images/9.png" alt="LyraNest Web 9.png" width="32%" />
</p>

### Android 移动端

<p align="center">
  <img src="docs/images/10.jpg" alt="LyraNest Android 10.jpg" width="32%" />
  <img src="docs/images/11.jpg" alt="LyraNest Android 11.jpg" width="32%" />
  <img src="docs/images/12.jpg" alt="LyraNest Android 12.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/13.jpg" alt="LyraNest Android 13.jpg" width="32%" />
  <img src="docs/images/14.jpg" alt="LyraNest Android 14.jpg" width="32%" />
  <img src="docs/images/15.jpg" alt="LyraNest Android 15.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/16.jpg" alt="LyraNest Android 16.jpg" width="32%" />
  <img src="docs/images/17.jpg" alt="LyraNest Android 17.jpg" width="32%" />
  <img src="docs/images/18.jpg" alt="LyraNest Android 18.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/19.jpg" alt="LyraNest Android 19.jpg" width="32%" />
  <img src="docs/images/20.jpg" alt="LyraNest Android 20.jpg" width="32%" />
  <img src="docs/images/21.jpg" alt="LyraNest Android 21.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/22.jpg" alt="LyraNest Android 22.jpg" width="32%" />
  <img src="docs/images/23.jpg" alt="LyraNest Android 23.jpg" width="32%" />
  <img src="docs/images/24a.jpg" alt="LyraNest Android 24a.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/24b.jpg" alt="LyraNest Android 24b.jpg" width="32%" />
  <img src="docs/images/25.jpg" alt="LyraNest Android 25.jpg" width="32%" />
  <img src="docs/images/26.jpg" alt="LyraNest Android 26.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/27.jpg" alt="LyraNest Android 27.jpg" width="32%" />
  <img src="docs/images/28.jpg" alt="LyraNest Android 28.jpg" width="32%" />
  <img src="docs/images/29.jpg" alt="LyraNest Android 29.jpg" width="32%" />
</p>

<p align="center">
  <img src="docs/images/30.jpg" alt="LyraNest Android 30.jpg" width="32%" />
  <img src="docs/images/31.jpg" alt="LyraNest Android 31.jpg" width="32%" />
</p>

### Windows 桌面端

<p align="center">
  <img src="docs/images/32.png" alt="LyraNest Windows 32.png" width="32%" />
  <img src="docs/images/33.png" alt="LyraNest Windows 33.png" width="32%" />
  <img src="docs/images/34.png" alt="LyraNest Windows 34.png" width="32%" />
</p>

<p align="center">
  <img src="docs/images/35.png" alt="LyraNest Windows 35.png" width="32%" />
</p>

## 获取客户端与服务端

请前往 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载对应平台的文件。该链接会在新版本发布后自动指向最新稳定版：

| 文件 | 说明 |
| --- | --- |
| Android ARM64 APK | Android 手机、平板客户端 |
| Windows x64 ZIP | Windows 桌面客户端 |
| `LyraNest-0.1.9-fnos-x86.fpk` | 飞牛 fnOS x86 原生安装包（NAS 用户推荐） |
| `LyraNest-v0.1.9-docker-amd64.tar.gz` | Docker Linux AMD64 离线镜像包 |
| `docker-compose.yml` | Docker Compose 部署配置 |
| `LyraNest.env.example` | Docker 环境变量示例 |
| `SHA256SUMS.txt` | 发行文件 SHA-256 校验值 |
| `SHA256SUMS-fnOS.txt` | 飞牛 fnOS FPK 的 SHA-256 校验值 |

## 飞牛 fnOS 原生 FPK 安装（推荐）

飞牛 NAS 用户推荐从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载 `LyraNest-0.1.9-fnos-x86.fpk`，然后在飞牛应用中心使用“手动安装”导入该文件。

安装后，在应用设置中授权音乐目录并启动 LyraNest。默认使用飞牛统一网关访问：在你平时打开飞牛管理界面的局域网地址后追加 `/app/lyranest`。

如需独立局域网端口，可在 LyraNest 应用设置填写 `1024–65535` 的自定义端口，保存后重启应用，再通过 `http://<飞牛局域网地址>:<端口>/` 访问。留空则只保留飞牛网关入口；独立端口仅建议用于可信局域网，不要配置公网端口映射。

## Docker 镜像

本次发行提供 Docker 离线镜像包；导入后服务端镜像统一命名为：

```text
lyranest-server:0.1.9
```

生产环境请固定 `LYRANEST_VERSION=0.1.9`。后续升级时下载对应版本的离线镜像包、校验并导入，再将该变量更新为相同版本号；不提供不确定的 Docker `latest` 标签。

## Docker Compose 部署

根目录的 [`docker-compose.yml`](docker-compose.yml) 与发行附件均直接使用本次离线镜像；可直接保存为同名文件后执行部署：

```yaml
# LyraNest 服务端 Docker Compose 配置
# 建议复制 .env.example 为 .env，然后优先在 .env 中修改参数。

services:
  lyranest:
    # 镜像版本由 LYRANEST_VERSION 控制。
    # 固定版本示例：0.1.9。请先从 GitHub Release 下载并导入 Docker 离线包。
    image: lyranest-server:${LYRANEST_VERSION:-0.1.9}
    container_name: lyranest
    restart: unless-stopped
    init: true

    # 当前发行镜像为 Linux AMD64；ARM 服务器暂时不能直接使用此镜像。
    platform: linux/amd64

    # 修改为服务器当前用户的 UID/GID，可通过 id -u 和 id -g 查询。
    user: ${PUID:-1000}:${PGID:-1000}

    # 可按服务器内存大小调整限制；默认最大 256 MB，预留 128 MB。
    mem_limit: ${SERVER_MEMORY_LIMIT:-256m}
    mem_reservation: ${SERVER_MEMORY_RESERVATION:-128m}
    security_opt:
      - no-new-privileges:true

    environment:
      # 容器内部监听端口，一般不需要修改。
      SERVER_ADDR: :8080
      MUSIC_LIBRARY_DIR: /music
      MUSIC_DATA_DIR: /data
      MUSIC_CACHE_DIR: /cache
      GOMEMLIMIT: ${GOMEMLIMIT:-192MiB}
      GOGC: ${GOGC:-100}
      MUSICBRAINZ_USER_AGENT: ${MUSICBRAINZ_USER_AGENT:-LyraNest/0.1.9 (+https://github.com/WHWgogogo/LyraNest)}
      MUSICBRAINZ_BASE_URL: ${MUSICBRAINZ_BASE_URL:-https://musicbrainz.org}
      MUSICBRAINZ_TIMEOUT: ${MUSICBRAINZ_TIMEOUT:-20s}
      LOG_LEVEL: ${LOG_LEVEL:-info}
      SHUTDOWN_TIMEOUT: ${SHUTDOWN_TIMEOUT:-10s}
      AUTH_SESSION_TTL: ${AUTH_SESSION_TTL:-24h}
      HTTP_PROXY: ${HTTP_PROXY:-}
      HTTPS_PROXY: ${HTTPS_PROXY:-}
      NO_PROXY: ${NO_PROXY:-}

    ports:
      # 左侧是主机访问端口，右侧 8080 是容器端口。
      # 例如 SERVER_PORT=9090 时，访问地址为 http://服务器地址:9090。
      - ${SERVER_PORT:-8080}:8080

    volumes:
      # 冒号左侧是主机目录，可以改成绝对路径；右侧容器目录不要修改。
      # 音乐目录示例：/mnt/music:/music:ro 或 /volume1/music:/music:ro。
      - ${MUSIC_LIBRARY_HOST_DIR:-./music}:/music:ro
      # 数据目录保存账号、收藏、歌单和服务端状态。
      - ${DATA_DIR:-./data}:/data:rw
      # 缓存目录保存运行缓存。
      - ${CACHE_DIR:-./cache}:/cache:rw

    healthcheck:
      test: ["CMD", "/usr/local/bin/music-player-server", "healthcheck"]
      interval: 30s
      timeout: 5s
      retries: 5
      start_period: 30s
```

### 1. 准备目录与配置

```bash
mkdir -p lyranest && cd lyranest
curl -fLO https://github.com/WHWgogogo/LyraNest/releases/latest/download/LyraNest-v0.1.9-docker-amd64.tar.gz
curl -fLO https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml
curl -fLO https://github.com/WHWgogogo/LyraNest/releases/latest/download/LyraNest.env.example
docker load -i LyraNest-v0.1.9-docker-amd64.tar.gz
mkdir -p music data cache
cp .env.example .env
```

根目录的 [`docker-compose.yml`](docker-compose.yml) 已附带中文注释。可在 `.env` 中按需修改以下项目：

| 配置项 | 默认值 | 用途 |
| --- | --- | --- |
| `SERVER_PORT` | `8080` | 主机对外访问端口，例如 `18080` |
| `MUSIC_LIBRARY_HOST_DIR` | `./music` | 主机音乐目录，可替换为绝对路径 |
| `DATA_DIR` | `./data` | 用户、收藏、歌单和服务端数据目录 |
| `CACHE_DIR` | `./cache` | 服务端缓存目录 |
| `PUID` / `PGID` | `1000` | 容器访问挂载目录时使用的主机用户 ID |
| `LYRANEST_VERSION` | `0.1.9` | 本次离线镜像的服务端版本 |

### 2. 启动与检查

```bash
docker compose up -d
docker compose ps
curl http://127.0.0.1:8080/health
```

首次启动后，可使用 `http://服务器地址:8080` 打开网页端；Windows 与 Android 客户端填写相同的服务器地址并登录即可。

## 版本与校验

- 每个版本都保留独立 GitHub Release 与附件，不会覆盖旧版本。
- README 的下载入口使用 GitHub `releases/latest`，始终指向最新稳定发行。
- 下载完成后可用对应的 `SHA256SUMS.txt` 或 `SHA256SUMS-fnOS.txt` 校验文件完整性。
- 详细更新内容请查看对应版本的 `CHANGELOG.md`。

## 相关项目

- [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)：MIT 许可的开源基础版本。
- [LyraNest Releases](https://github.com/WHWgogogo/LyraNest/releases/latest)：完整发行版的最新下载页。
