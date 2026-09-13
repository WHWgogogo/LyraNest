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
  <a href="https://lyranest.dpdns.org/">官网</a> ·
  <a href="#docker-compose-部署">Docker 部署</a> ·
  <a href="releases/0.2.7/CHANGELOG.md">更新日志</a> ·
  <a href="https://github.com/WHWgogogo/LyraNest-Community">开源社区版</a>
</p>

> **发行版说明**：此仓库用于发布 LyraNest 的客户端安装包、Docker 部署配置与更新记录，不包含完整版本源代码。若需要开源、可自行构建的基础版本，请前往 [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)。

将音乐文件保存在自己的服务器、NAS 或电脑中，即可通过 Web、Windows 和 Android 客户端管理、播放并同步个人音乐库。

当前稳定版本：`0.2.7`


交流 QQ 群：`700454910`

## 0.2.7 更新日志

### NAS 原生支持与安装

- **新增原生 NAS 安装包**：本次提供 QNAP、Synology DSM、绿联 NAS 和铁威马 TOS 7 的原生安装包，分别覆盖 x86/AMD64 与 ARM64 设备；下载时必须选择 NAS 系统和 CPU 架构都匹配的文件。
- **fnOS 安装向导**：标准版与 Compat 版均新增音乐、有声书目录挂载提醒和可选的自定义局域网端口设置，首次安装可跳过，后续在设置中补充。

### 曲库管理与有声书

- **一键曲库去重与清理**：可按音频规格、时长、添加时间等四种策略保留曲目，批量隐藏重复歌曲；管理员可在确认目录写入权限后清理隐藏文件。
- **播放与封面优化**：播放收藏仅加入收藏曲目；未内嵌封面、未刮削的歌曲可自动使用同目录封面。
- **有声书书架重构**：优化封面、进度、演播者和章节展示，并改进大屏和移动端全屏播放体验。

### Web、客户端与 TV

- **PWA 与锁屏控制**：Web 支持添加到 iOS、HarmonyOS 桌面；MediaSession 可显示歌曲信息与封面，并支持锁屏暂停、切歌。
- **移动端适配**：修复兼容模式报告在小屏上的横向溢出和播放页触摸穿透问题。
- **客户端连接**：新增 fnid 外网地址支持；修复收藏页播放和定时结束播放问题。
- **TV 与小爱桥接**：TV 首页和播放页体验优化，新增转码与标签功能；小爱桥接器支持自定义语音口令以及控制曲库、歌单播放。

完整更新记录请查看 [`releases/0.2.7/CHANGELOG.md`](releases/0.2.7/CHANGELOG.md)。

## 功能简介

- **多端音乐库**：Web、Windows、Android 共用服务端曲库、收藏、歌单与播放队列。
- **完整播放体验**：歌词展示与逐曲偏移调整、桌面歌词、播放模式、睡眠定时、播放列表定位。
- **离线下载**：下载歌曲、封面与歌词，在离线状态下浏览并播放已下载内容。
- **发现与报告**：每日推荐、猜你喜欢、听歌排行、听歌热力图与个人听歌统计。
- **曲库管理**：搜索、排序、批量操作、专辑与艺术家浏览，以及元数据刮削。
- **轻量部署**：Docker Compose 一键部署，支持音乐目录、数据目录、端口和内存限制配置。

## 界面预览

### 0.2.3 新功能预览

<p align="center">
  <img src="releases/0.2.3/UI%20image/1.jpg" alt="LyraNest 0.2.3 下载插件入口" width="32%" />
  <img src="releases/0.2.3/UI%20image/2.jpg" alt="LyraNest 0.2.3 插件中心配置" width="32%" />
  <img src="releases/0.2.3/UI%20image/3.jpg" alt="LyraNest 0.2.3 插件中心" width="32%" />
</p>

<p align="center">
  <img src="releases/0.2.3/UI%20image/4.jpg" alt="LyraNest 0.2.3 插件市场" width="32%" />
  <img src="releases/0.2.3/UI%20image/5.jpg" alt="LyraNest 0.2.3 下载搜索" width="32%" />
  <img src="releases/0.2.3/UI%20image/6.jpg" alt="LyraNest 0.2.3 下载队列" width="32%" />
</p>

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
| `LyraNest-0.2.7-android-arm64.apk` | Android 手机、平板客户端 |
| `LyraNest-0.2.7-windows-x64.zip` | Windows 桌面客户端 |
| `LyraNest-0.2.7-fnos-x86.fpk` | 飞牛 fnOS x86 原生安装包（NAS 用户推荐） |
| `LyraNest-0.2.7-fnos-arm.fpk` | 飞牛 fnOS ARM 原生安装包 |
| `LyraNest-Compat-0.2.7-fnos-x86.fpk` | fnOS x86 兼容版（不依赖统一网关） |
| `LyraNest-Compat-0.2.7-fnos-arm.fpk` | fnOS ARM 兼容版（不依赖统一网关） |
| `LyraNest-0.2.7-qnap-x86.qpkg` | QNAP x86_64 原生安装包 |
| `LyraNest-0.2.7-qnap-arm64.qpkg` | QNAP ARM64 原生安装包 |
| `LyraNest-0.2.7-synology-x86.spk` | Synology DSM x86_64 原生安装包 |
| `LyraNest-0.2.7-synology-arm64.spk` | Synology DSM ARM64 原生安装包 |
| `LyraNest-0.2.7-ugnas-amd64.upk` | 绿联 NAS AMD64 原生安装包 |
| `LyraNest-0.2.7-ugnas-arm64.upk` | 绿联 NAS ARM64 原生安装包 |
| `LyraNest-0.2.7-terramaster-x86_64.deb` | 铁威马 TOS 7 x86_64 原生安装包 |
| `LyraNest-0.2.7-terramaster-aarch64.deb` | 铁威马 TOS 7 ARM64 原生安装包 |
| `lyranest_x86_64.deb` | 铁威马 TOS 7 应用中心官方规范包 (x86_64) |
| `lyranest_aarch64.deb` | 铁威马 TOS 7 应用中心官方规范包 (aarch64) |
| `LyraNest-TV-0.2.7-arm64-v8a.apk` | Android TV ARM64 客户端 |
| `LyraNest-TV-0.2.7-armeabi-v7a.apk` | Android TV ARM32 客户端 |
| `LyraNest-0.2.7-docker-linux-amd64.tar.gz` | Docker Linux AMD64 离线镜像归档（`docker load`） |
| `LyraNest-0.2.7-docker-linux-arm64.tar.gz` | Docker Linux ARM64 离线镜像归档（`docker load`） |
| `docker-compose.yml` | Docker Compose 在线部署配置 |
## 飞牛 fnOS 原生 FPK 安装（推荐）

飞牛 NAS 用户请从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载对应架构的 FPK：x86_64 使用 `LyraNest-0.2.7-fnos-x86.fpk`，ARM64 使用 `LyraNest-0.2.7-fnos-arm.fpk`；标准版与兼容版二选一，不可同时安装。

安装后，在应用设置中授权音乐目录并启动 LyraNest。默认使用飞牛统一网关访问：在你平时打开飞牛管理界面的局域网地址后追加 `/app/lyranest`。

如需独立局域网端口，可在 LyraNest 应用设置填写 `1024–65535` 的自定义端口，保存后重启应用，再通过 `http://<飞牛局域网地址>:<端口>/` 访问。留空则只保留飞牛网关入口；独立端口仅建议用于可信局域网，不要配置公网端口映射。

## 其他 NAS 原生安装包

QNAP、Synology DSM、绿联 NAS 与铁威马 TOS 7 用户可从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载对应的原生包，在各自系统的应用中心或套件中心选择手动安装。请先在 NAS 系统信息中确认 CPU 架构：x86/x86_64 或 AMD64 设备使用 `x86`/`amd64` 文件，ARM64 设备使用 `arm64`/`aarch64` 文件；不同 NAS 系统的安装包不能交叉安装。

- QNAP：`LyraNest-0.2.7-qnap-x86.qpkg` 或 `LyraNest-0.2.7-qnap-arm64.qpkg`。
- Synology DSM：`LyraNest-0.2.7-synology-x86.spk` 或 `LyraNest-0.2.7-synology-arm64.spk`。
- 绿联 NAS：`LyraNest-0.2.7-ugnas-amd64.upk` 或 `LyraNest-0.2.7-ugnas-arm64.upk`。
- 铁威马 TOS 7：`LyraNest-0.2.7-terramaster-x86_64.deb` 或 `LyraNest-0.2.7-terramaster-aarch64.deb`（亦提供应用中心规范包 `lyranest_x86_64.deb` 与 `lyranest_aarch64.deb`）。

## Docker 镜像

服务端镜像统一命名为：

```text
ghcr.io/whwgogogo/lyranest-server:0.2.7
```

生产环境请固定 `LYRANEST_VERSION=0.2.7`。同时发布 `0.2.7` 与 `latest` 标签，其中 `latest` 指向当前稳定版 `0.2.7`；同一个多架构标签会按设备自动选择 AMD64 或 ARM64 镜像。

> 如果 Docker 报出 `proxyconnect tcp ... 127.0.0.1:27897: connect: connection refused`，请移除 Docker 守护进程中失效的 HTTP/HTTPS 代理后再拉取。若设备不能联网，可使用本次发行的 Docker 离线包并按下方命令导入和标记镜像。

## Docker Compose 部署

根目录的 [`docker-compose.yml`](docker-compose.yml) 与发行附件使用同一个正式镜像和版本：

```yaml
services:
  music-server:
    image: ghcr.io/whwgogogo/lyranest-server:${LYRANEST_VERSION:-0.2.7}
    container_name: lyranest-server
    restart: unless-stopped
    mem_limit: 256m
    mem_reservation: 128m
    environment:
      SERVER_ADDR: ":8080"
      MUSIC_LIBRARY_DIR: /music
      MUSIC_LIBRARY_ROOTS: "/music:/downloads"
      MUSIC_DATA_DIR: /data
      MUSIC_CACHE_DIR: /cache
      DOWNLOADS_ROOT: /downloads
      PROVIDER_CREDENTIAL_KEY: "${PROVIDER_CREDENTIAL_KEY:-}"
      GOMEMLIMIT: "192MiB"
      GOGC: "100"
      MEDIA_EXTRACT_CONCURRENCY: "4"
      MEDIA_SCRAPE_CONCURRENCY: "2"
      MUSICBRAINZ_USER_AGENT: "LyraNest/0.2.7 (+https://github.com/WHWgogogo/LyraNest)"
      MUSICBRAINZ_BASE_URL: "https://musicbrainz.org"
      MUSICBRAINZ_TIMEOUT: "20s"
      LOG_LEVEL: "info"
      SHUTDOWN_TIMEOUT: "10s"
      AUTH_SESSION_TTL: "24h"
      LYRANEST_DISCOVERY: "1"
    ports:
      - "8080:8080"
    volumes:
      - ./music:/music:ro
      # - ./music1:/music1:ro
      - ./downloads:/downloads:rw
      - ./data:/data:rw
      - ./cache:/cache:rw
```

如需挂载多个音乐目录，在 `volumes` 中继续添加 `./music1:/music1:ro`、`./music2:/music2:ro` 等只读挂载；服务端会自动发现这些目录。

### 1. 在线部署

```bash
mkdir -p lyranest && cd lyranest
curl -fLO https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml
mkdir -p music downloads data cache
docker compose pull
docker compose up -d
```

简化版 Compose 直接使用相对目录。需要调整端口、音乐目录、数据目录或缓存目录时，直接修改 `docker-compose.yml` 中对应的 `ports` 和 `volumes` 行即可。

### 2. GHCR 无法访问时离线部署

优先下载与设备架构匹配的 Docker 离线镜像归档：AMD64 使用 `LyraNest-0.2.7-docker-linux-amd64.tar.gz`，ARM64 使用 `LyraNest-0.2.7-docker-linux-arm64.tar.gz`。两份归档均包含完整镜像，按设备架构选择其中一份即可。

```bash
docker load -i LyraNest-0.2.7-docker-linux-amd64.tar.gz
docker tag lyranest-server:0.2.7 ghcr.io/whwgogogo/lyranest-server:0.2.7
curl -fLO https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml
mkdir -p music downloads data cache
docker compose up -d --pull never
```

ARM64 设备使用下面的归档和本地标签：

```bash
docker load -i LyraNest-0.2.7-docker-linux-arm64.tar.gz
docker tag lyranest-server:0.2.7-arm64 ghcr.io/whwgogogo/lyranest-server:0.2.7
docker compose up -d --pull never
```

离线启动时不要执行 `docker compose pull`；如果 NAS 图形界面会强制拉取镜像，请关闭“启动前拉取镜像”选项。
### 3. 检查服务

```bash
docker compose ps
curl http://127.0.0.1:8080/health
```

首次启动后，可使用 `http://服务器地址:8080` 打开网页端；Windows 与 Android 客户端填写相同的服务器地址并登录即可。

## 版本与校验

- 每个版本都保留独立 GitHub Release 与附件，不会覆盖旧版本。
- README 的下载入口使用 GitHub `releases/latest`，始终指向最新稳定发行。
- GitHub Release 附件页会显示每个附件的 SHA-256 摘要，可直接用于校验下载文件完整性。
- 详细更新内容请查看对应版本的 `CHANGELOG.md`。

## 项目友链

- [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)：MIT 许可的开源基础版本。
- [LyraNest Releases](https://github.com/WHWgogogo/LyraNest/releases/latest)：完整发行版的最新下载页。
- [simple_sq_music_plus](https://github.com/59799517/simple_sq_music_plus)：SQ 音乐下载插件项目。
- [LyraNest Xiaomi Bridge](https://github.com/WHWgogogo/LyraNest-Xiaomi-Bridge)：LyraNest 小爱音响桥接项目。
- [Solara](https://github.com/akudamatata/Solara)：Solara音乐下载插件项目。
- [GoMusic](https://github.com/Bistutu/GoMusic)：GoMusic歌单导入项目。

## Star History

<a href="https://www.star-history.com/?repos=WHWgogogo%2FLyraNest&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=WHWgogogo/LyraNest&type=date&theme=dark&legend=top-left&sealed_token=BFPkuSGjk3RETAbD68uyiDigKZz8HiRPhNvfUeeF43jX9EUx4dFQ-oEqkgaWsaB5AehmQkSYmLx1-XzIHtLZzRhDLkaHjEZV-jdupKibjnmtt0TxixrUmA" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=WHWgogogo/LyraNest&type=date&legend=top-left&sealed_token=BFPkuSGjk3RETAbD68uyiDigKZz8HiRPhNvfUeeF43jX9EUx4dFQ-oEqkgaWsaB5AehmQkSYmLx1-XzIHtLZzRhDLkaHjEZV-jdupKibjnmtt0TxixrUmA" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=WHWgogogo/LyraNest&type=date&legend=top-left&sealed_token=BFPkuSGjk3RETAbD68uyiDigKZz8HiRPhNvfUeeF43jX9EUx4dFQ-oEqkgaWsaB5AehmQkSYmLx1-XzIHtLZzRhDLkaHjEZV-jdupKibjnmtt0TxixrUmA" />
 </picture>
</a>

## 感谢赞助

感谢每一位为 LyraNest 为爱发电的朋友。你们的支持让项目能够持续维护、修复问题并带来更多功能。

<p align="center">
  <img src="releases/0.2.3/%E4%B8%BA%E7%88%B1%E5%8F%91%E7%94%B5image/DDT.jpg" alt="DDT" width="56" height="56" />
  <img src="releases/0.2.3/%E4%B8%BA%E7%88%B1%E5%8F%91%E7%94%B5image/Heartless.jpg" alt="Heartless" width="56" height="56" />
  <img src="releases/0.2.3/%E4%B8%BA%E7%88%B1%E5%8F%91%E7%94%B5image/%E7%8E%A9%E7%94%B5%E7%9A%84%E5%B0%8F%E5%AD%A9%E0%B2%A5_%E0%B2%A5.jpg" alt="玩电的小孩ಥ_ಥ" width="56" height="56" />
</p>

<p align="center">DDT · Heartless · 玩电的小孩ಥ_ಥ</p>

感谢你们的信任与鼓励，也感谢每一位使用、反馈和传播 LyraNest 的朋友。
