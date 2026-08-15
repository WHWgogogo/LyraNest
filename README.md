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
  <a href="releases/0.2.4/CHANGELOG.md">更新日志</a> ·
  <a href="https://github.com/WHWgogogo/LyraNest-Community">开源社区版</a>
</p>

> **发行版说明**：此仓库用于发布 LyraNest 的客户端安装包、Docker 部署配置与更新记录，不包含完整版本源代码。若需要开源、可自行构建的基础版本，请前往 [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)。

将音乐文件保存在自己的服务器、NAS 或电脑中，即可通过 Web、Windows 和 Android 客户端管理、播放并同步个人音乐库。

当前稳定版本：`0.2.4`

交流 QQ 群：`700454910`

## 0.2.4 更新摘要

- **曲库字母轴修复**：修复曲库字母轴在弱网、连续点击字母、切换排序或刷新时可能跳到错误位置的问题；旧分页请求不再覆盖最新跳转结果。
- **浏览体验**：继续保留字母跳转后的前一页内容，向上滑动仍可查看该字母之前的曲目。
- **Android 播放**：恢复后台播放时的退出二次确认，并完善播放页歌词与曲目信息入口。
- **稳定性**：完善响应式封面、曲库分页、下载/离线页面与目录封面的稳定性修复。
- **服务端**：发行镜像内置 FFmpeg，转码能力可用时由服务端提前声明；同时保留客户端对旧服务端的兼容行为。
- **歌词与歌单**：歌词搜索、歌单导入导出、插件中心、下载插件与下载队列相关功能继续包含在 0.2.4 中。
- **正式部署包**：Windows、Android、Android TV arm64/v7a、fnOS（x86/ARM 标准版与兼容版）与 Docker Linux AMD64/ARM64 发行包统一升级至 `0.2.4`。

完整升级注意事项和更新内容请查看 [`releases/0.2.4/CHANGELOG.md`](releases/0.2.4/CHANGELOG.md)。

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
| `LyraNest-0.2.4-android-arm64.apk` | Android 手机、平板客户端 |
| `LyraNest-0.2.4-tv-arm64-v8a.apk` | Android TV ARM64 客户端 |
| `LyraNest-0.2.4-tv-armeabi-v7a.apk` | Android TV ARMv7 客户端 |
| `LyraNest-0.2.4-windows-x64.zip` | Windows 桌面客户端 |
| `LyraNest-0.2.4-fnos-x86.fpk` | 飞牛 fnOS x86 原生安装包（NAS 用户推荐） |
| `LyraNest-0.2.4-fnos-arm.fpk` | 飞牛 fnOS ARM 原生安装包 |
| `LyraNest-Compat-0.2.4-fnos-x86.fpk` | fnOS x86 兼容版（不依赖统一网关） |
| `LyraNest-Compat-0.2.4-fnos-arm.fpk` | fnOS ARM 兼容版（不依赖统一网关） |
| `LyraNest-0.2.4-docker-linux-amd64.tar.gz` | Docker Linux AMD64 离线部署包 |
| `LyraNest-0.2.4-docker-linux-arm64.tar.gz` | Docker Linux ARM64 离线部署包 |
| `docker-compose.yml` | Docker Compose 在线部署配置 |
## 飞牛 fnOS 原生 FPK 安装（推荐）

飞牛 NAS 用户请从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载对应架构的 FPK：x86_64 使用 `LyraNest-0.2.4-fnos-x86.fpk`，ARM64 使用 `LyraNest-0.2.4-fnos-arm.fpk`；标准版与兼容版二选一，不可同时安装。

安装后，在应用设置中授权音乐目录并启动 LyraNest。默认使用飞牛统一网关访问：在你平时打开飞牛管理界面的局域网地址后追加 `/app/lyranest`。

如需独立局域网端口，可在 LyraNest 应用设置填写 `1024–65535` 的自定义端口，保存后重启应用，再通过 `http://<飞牛局域网地址>:<端口>/` 访问。留空则只保留飞牛网关入口；独立端口仅建议用于可信局域网，不要配置公网端口映射。

## Docker 镜像

服务端镜像统一命名为：

```text
ghcr.io/whwgogogo/lyranest-server:0.2.4
```

生产环境请固定 `LYRANEST_VERSION=0.2.4`。同时发布 `0.2.4` 与 `latest` 标签，其中 `latest` 指向当前稳定版 `0.2.4`。

> 如果 Docker 报出 `proxyconnect tcp ... 127.0.0.1:27897: connect: connection refused`，请移除 Docker 守护进程中失效的 HTTP/HTTPS 代理后再拉取。若设备不能联网，可使用本次发行的 Docker 离线包并按下方命令导入和标记镜像。

## Docker Compose 部署

根目录的 [`docker-compose.yml`](docker-compose.yml) 与发行附件使用同一个正式镜像和版本：

```yaml
services:
  music-server:
    image: ghcr.io/whwgogogo/lyranest-server:${LYRANEST_VERSION:-0.2.4}
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
      MUSICBRAINZ_USER_AGENT: "LyraNest/0.2.4 (+https://github.com/WHWgogogo/LyraNest)"
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

从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载与设备架构匹配的离线部署包：AMD64 使用 `LyraNest-0.2.4-docker-linux-amd64.tar.gz`，ARM64 使用 `LyraNest-0.2.4-docker-linux-arm64.tar.gz`。

```bash
tar -xzf LyraNest-0.2.4-docker-linux-amd64.tar.gz
cd LyraNest-0.2.4-docker-linux-amd64
mkdir -p music downloads data cache
docker compose up -d --build --pull never
```

离线部署包已包含对应架构的服务端二进制与 Dockerfile，无需访问 GHCR，也不要执行 `docker compose pull`。启动前请按实际情况修改 `docker-compose.yml` 中的目录挂载；如果 NAS 图形界面会强制拉取镜像，请关闭“启动前拉取镜像”选项。

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

## 相关项目

- [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)：MIT 许可的开源基础版本。
- [LyraNest Releases](https://github.com/WHWgogogo/LyraNest/releases/latest)：完整发行版的最新下载页。
- [59799517/simple_sq_music_plus](https://github.com/59799517/simple_sq_music_plus)：SQ 音乐下载插件项目。


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
