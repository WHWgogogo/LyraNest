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

> Docker/OCI 镜像拉取名使用 `lyranest-server`；

## Docker Compose 完整配置

下面是发行仓库中的完整 `docker-compose.yml`：

```yaml


services:
  lyranest:
    # 版本控制
    image: ghcr.io/whwgogogo/lyranest-server:${LYRANEST_VERSION:-latest}
    container_name: lyranest
    restart: unless-stopped
    init: true

    # 当前发行镜像为 Linux AMD64；ARM 服务器暂时不能直接使用此镜像。
    platform: linux/amd64
    pull_policy: always

    # 修改为服务器当前用户的 UID/GID，可通过 id -u 和 id -g 查询。
    user: ${PUID:-1000}:${PGID:-1000}

    # 可按服务器内存大小调整限制；默认最大 256 MB，预留 128 MB。
    mem_limit: ${SERVER_MEMORY_LIMIT:-256m}
    mem_reservation: ${SERVER_MEMORY_RESERVATION:-128m}
    security_opt:
      - no-new-privileges:true

    environment:
      # 容器内部监听端口，无需修改。
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
      # 左侧是主机访问端口，右侧 8080 是容器端口。
      # 例如 SERVER_PORT=9090 时，访问地址为 http://服务器地址:9090。
      - ${SERVER_PORT:-8080}:8080

    volumes:
      # 冒号左侧是主机目录，可以改成绝对路径；右侧容器目录不要修改。
      # 音乐目录示例：/mnt/music:/music:rw 或 /volume1/music:/music:rw。
      - ${MUSIC_LIBRARY_HOST_DIR:-./music}:/music:rw
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

## Docker 部署

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

## UI展示
1.网页端
![LyraNest UI screenshot 01](docs/images/1.png)
![LyraNest UI screenshot 02](docs/images/2.png)
![LyraNest UI screenshot 03](docs/images/3.png)
![LyraNest UI screenshot 04](docs/images/4.png)
![LyraNest UI screenshot 05](docs/images/5.png)
![LyraNest UI screenshot 06](docs/images/6.png)
![LyraNest UI screenshot 07](docs/images/7.png)
![LyraNest UI screenshot 08](docs/images/8.png)
![LyraNest UI screenshot 09](docs/images/9.png)
![LyraNest UI screenshot 10](docs/images/10.jpg)
2.安卓手机端
![LyraNest UI screenshot 11](docs/images/11.jpg)
![LyraNest UI screenshot 12](docs/images/12.jpg)
![LyraNest UI screenshot 13](docs/images/13.jpg)
![LyraNest UI screenshot 14](docs/images/14.jpg)
![LyraNest UI screenshot 15](docs/images/15.jpg)
![LyraNest UI screenshot 16](docs/images/16.jpg)
![LyraNest UI screenshot 17](docs/images/17.jpg)
![LyraNest UI screenshot 18](docs/images/18.jpg)
![LyraNest UI screenshot 19](docs/images/19.jpg)
![LyraNest UI screenshot 20](docs/images/20.jpg)
![LyraNest UI screenshot 21](docs/images/21.jpg)
![LyraNest UI screenshot 22](docs/images/22.jpg)
软件有桌面歌词，设置中可以修改歌词对齐方式、桌面歌词的颜色、字号等，点击暂停键上方下载右侧的图标，授予软件通知权限与悬浮窗权限，即可开启桌面歌词，桌面歌词可以随意拖动，其透明度可以在设置中进行修改。向右滑动，点击歌词右上角展开可以对齐歌词与播放进度（对于没有对齐的歌词）
![LyraNest UI screenshot 23](docs/images/23.jpg)
![LyraNest UI screenshot 24](docs/images/24a.jpg)
![LyraNest UI screenshot 25](docs/images/24b.jpg)
播放队列在右下角，可以拖动右侧滑条调整顺序，此外还有睡眠定时功能等不再赘述，你可以自行探索！
![LyraNest UI screenshot 26](docs/images/25.jpg)
![LyraNest UI screenshot 27](docs/images/26.jpg)
![LyraNest UI screenshot 28](docs/images/27.jpg)
发现页面与网页端类似，拥有每日推荐、猜你喜欢等内容
![LyraNest UI screenshot 29](docs/images/28.jpg)
![LyraNest UI screenshot 30](docs/images/29.jpg)
![LyraNest UI screenshot 31](docs/images/30.jpg)
![LyraNest UI screenshot 32](docs/images/31.jpg)
3.、平板、windows桌面端

![LyraNest UI screenshot 33](docs/images/32.png)
![LyraNest UI screenshot 34](docs/images/33.png)
![LyraNest UI screenshot 35](docs/images/34.png)
![LyraNest UI screenshot 36](docs/images/35.png)


## 未来规划
目前的开发已经告一段落，在未来，有如下规划：
将核心功能开源，方便喜欢开源软件的人部署；
增加多账户功能、增加音乐库功能（类似于飞牛的影视库的分级制度）；
增加k歌与点歌台的功能，这个一定会做的，因为我老妈超级爱唱歌，大家可以期待一下下；
增加共建评论区功能（如果合规的话我尽量尝试做一下，只通过歌名与歌手匹配）；
移植鸿蒙版（如果可以的话，我尽量做）；
其他···
如果您有好的建议和想法，欢迎给我提出来，我会尽量尝试做的！
后面有时间的话，我会将教程视频录制到我的b站账号上发布，也欢迎大家来评论区交流！


## 写在最后的话
律巢是我利用备考空闲时间做出的软件，我对其倾注了很多，虽然他不是很完美，但是我个人认为他足够的轻巧，功能也足够完善，后续肯定还会添加很多功能，但是我暂时精力有限很难去维护他，大概等到考研结束后，我会为他完善更多的功能，如果您在使用中遇到了任何问题，也欢迎与我联系。
我的邮箱：whw1377236334@163.com 
我的b站账号：https://space.bilibili.com/416521837?spm_id_from=333.1007.0.0
最后如果您觉得我的这个项目还不错，也欢迎赞助我，感谢您的支持！
