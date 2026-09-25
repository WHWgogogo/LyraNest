# LyraNest（律巢）

<p align="center">
  <img src="docs/images/lyranest-logo.png" alt="LyraNest Logo" width="150" />
</p>

<p align="center">一套面向个人 NAS、家庭服务器与局域网音乐库的自托管音乐服务。</p>

<p align="center">
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest"><img src="https://img.shields.io/github/v/release/WHWgogogo/LyraNest?display_name=tag&label=Release" alt="Latest Release" /></a>
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest"><img src="https://img.shields.io/badge/Platform-Android%20%7C%20iOS%20%7C%20HarmonyOS%20%7C%20Windows%20%7C%20macOS%20%7C%20TV-4f46e5" alt="Platforms" /></a>
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml"><img src="https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white" alt="Docker Compose" /></a>
</p>

<p align="center">
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest">下载最新版</a> ·
  <a href="https://lyranest.cc.cd/">官网</a> ·
  <a href="#docker-compose-部署">Docker 部署</a> ·
  <a href="releases/0.2.8/CHANGELOG.md">更新日志</a> ·
  <a href="https://github.com/WHWgogogo/LyraNest-Community">开源社区版</a>
</p>

> **发行版说明**：此仓库用于发布 LyraNest 的客户端安装包、Docker 部署配置与更新记录，不包含完整版本源代码。若需要开源、可自行构建的基础版本，请前往 [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)。

将音乐文件保存在自己的服务器、NAS 或电脑中，即可通过 Web、Windows、macOS、iOS、Android 和 Android TV 客户端管理、播放并同步个人音乐库。

当前稳定版本：`0.2.8`


交流 QQ 群：`700454910`

## 0.2.8 更新日志

### 投播生态与多设备音频输出

- **全新 AirPlay 2 桥接支持**：推出官方独立插件 [LyraNest AirPlay Bridge](https://github.com/WHWgogogo/LyraNest-AirPlay-Bridge)，支持将曲库音频无线投送至苹果 HomePod、Apple TV 及第三方 AirPlay 兼容音箱，支持全端独立音量与播控调节。
- **全新本机 3.5mm / ALSA 声卡直出**：推出官方独立插件 [LyraNest Local Output](https://github.com/WHWgogogo/LyraNest-Local-Output)，专为 NAS 与主机硬件打造，通过 ALSA / MPD 直通 NAS 本地 3.5mm 耳机孔或 USB DAC 外置声卡，无损原音输出，内存占用仅 13MB。
- **全端聚合投送中心**：统一聚合 AirPlay 2、本地声卡、DLNA 及小爱音箱四大通道，支持设备状态实时探测、进度条拖拽同步（Seek Offset）与音量滑块调节。
- **小爱音箱桥接器升级至 v1.1.6**：官方插件 [LyraNest Xiaomi Bridge](https://github.com/WHWgogogo/LyraNest-Xiaomi-Bridge) 全面升级，新增多音箱会话隔离与多账号用户设备绑定，支持有声书语音点播与双向断点续播，引入虚拟播放时钟解决休眠状态回传延迟与断流问题。

### 连接架构与免配扫码登录

- **X25519 局域网端到端加密扫码登录**：手机 App 扫描 Web 端或 TV 端二维码即可秒级完成安全配对与跨端鉴权，彻底告别手动输入 IP、端口与密码。
- **飞牛 FNID 穿透与跨网自适应**：重构 FNID 多端点竞速优选与双签名鉴权算法，大幅提升无公网 IP 环境下的跨网穿透连通率与冷启动速度；隔离同 IP 多端口的会话冲突。

### 无损格式与网络串流

- **原生支持 STRM 网络流媒体文件**：音乐与有声书全面支持 `.strm` 文件识别与入库，支持 302 重定向、反代播放与动态按需转码；有声书 STRM 章节支持跨端拖拽寻道与进度断点记忆。
- **CUE 虚拟分轨与切片串流**：整轨音频配合同名 `.cue` 索引文件自动虚拟分轨入库，服务端支持任意时间偏移切片 Seeking，实现精准秒开。
- **扩充高清无损解码**：新增 DSF、DFF（DSD 母带级音频）、WavPack、CAF 与 AIFF-C 高清无损音频解码嗅探与元数据提取，集成 APE 专用头部解析器。

### 曲库治理、有声书与全端体验

- **隐藏歌曲独立管理页**：集中查看被去重或手动隐藏的全部曲目，支持单曲恢复与批量一键移出隐藏名单；TV 端深度适配遥控器方向键快捷操作。
- **挂载目录失效容错**：磁盘离线或物理路径变更时自动标记失效状态，并允许直接在管理面板中安全解挂与删除。
- **智能刮削算法 V2**：引入证据门控与冲突抑制模型，大幅降低误刮削；强化基于目录层级与 URL 的路径元数据推断机制（PathMeta）。
- **有声书系统深化**：支持全网有声书搜索并直接下载导入专属私有书架，全屏播放器增加专属书籍标签与章节树，支持整本书籍加入跨端投送队列。
- **全平台客户端原生齐备**：移动端新增悬浮毛玻璃胶囊导航栏与旋转黑胶 Disc 迷你播放器；正式推出 macOS 原生客户端（DMG / ZIP）与 iOS 原生客户端（IPA）；Android TV 端全面对齐 STRM 串流与免配扫码登录；全 NAS 体系官方包覆盖飞牛、群晖、铁威马、威联通、绿联、畅网。

完整更新记录请查看 [`releases/0.2.8/CHANGELOG.md`](releases/0.2.8/CHANGELOG.md)。

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

> [!IMPORTANT]
> **测试版客户端与签名说明**：
> 目前 **iOS (`.ipa`)**、**macOS (`.dmg` / `.zip`)** 与 **鸿蒙 HarmonyOS (`.hap`)** 版本处于测试公测阶段，安装包均为**无开发者签名版本**，需要用户自行签名或侧载安装：
> - **iOS 端**：需使用个人开发者证书或第三方侧载工具（如 AltStore、SideStore、牛蛙助手、爱思助手等）签名后安装。
> - **macOS 端**：通用架构安装包初次打开若提示“无法验证开发者”或“已损坏”，请在 macOS「系统设置」→「隐私与安全性」中选择「仍要打开」，或在终端执行 `sudo xattr -rd com.apple.quarantine /Applications/LyraNest.app` 解除 Gatekeeper 隔离。
> - **鸿蒙 HarmonyOS 端**：需在系统设置中开启「开发者选项」，使用 DevEco Studio 或鸿蒙命令行工具侧载签名安装。

| 文件 | 说明 |
| --- | --- |
| `LyraNest-0.2.8-android-arm64.apk` | Android 手机、平板客户端 |
| `LyraNest-0.2.8-ios-arm64.ipa` | iOS 移动客户端（测试阶段，无签名，需自行签名侧载安装） |
| `LyraNest-0.2.8-harmony.hap` | 华为鸿蒙 HarmonyOS 原生客户端（测试阶段，无签名，需开发者模式安装） |
| `LyraNest-0.2.8-windows-x64.zip` | Windows 桌面客户端 |
| `LyraNest-Server-0.2.8-windows-x64.zip` | Windows 服务端独立运行包 |
| `LyraNest-0.2.8-macos-universal.dmg` | macOS 桌面客户端（通用架构 DMG，测试阶段，无签名，需允许安全偏好） |
| `LyraNest-0.2.8-macos-universal.zip` | macOS 桌面客户端（通用架构免安装 ZIP 归档，测试阶段，无签名） |
| `LyraNest-TV-0.2.8-arm64-v8a.apk` | Android TV ARM64 客户端 |
| `LyraNest-TV-0.2.8-armeabi-v7a.apk` | Android TV ARM32 客户端 |
| `LyraNest-0.2.8-fnos-x86.fpk` | 飞牛 fnOS x86 原生安装包（NAS 用户推荐） |
| `LyraNest-0.2.8-fnos-arm.fpk` | 飞牛 fnOS ARM 原生安装包 |
| `LyraNest-Compat-0.2.8-fnos-x86.fpk` | fnOS x86 兼容版（不依赖统一网关） |
| `LyraNest-Compat-0.2.8-fnos-arm.fpk` | fnOS ARM 兼容版（不依赖统一网关） |
| `LyraNest-0.2.8-synology-x86_64.spk` | Synology DSM x86_64 原生安装包 |
| `LyraNest-0.2.8-synology-armv8.spk` | Synology DSM ARM64 原生安装包 |
| `LyraNest-0.2.8-terramaster-x86_64.deb` | 铁威马 TOS 7 x86_64 原生安装包 |
| `LyraNest-0.2.8-terramaster-aarch64.deb` | 铁威马 TOS 7 ARM64 原生安装包 |
| `LyraNest-0.2.8-qnap-x86_64.qpkg` | QNAP x86_64 原生安装包 |
| `LyraNest-0.2.8-qnap-arm_64.qpkg` | QNAP ARM64 原生安装包 |
| `LyraNest-0.2.8-ugnas-amd64.upk` | 绿联 NAS AMD64 原生安装包 |
| `LyraNest-0.2.8-ugnas-arm64.upk` | 绿联 NAS ARM64 原生安装包 |
| `LyraNest-0.2.8-cwnas.cpk` | 畅网 NAS (CWNAS / AINAS) 原生应用包 |
| `LyraNest-0.2.8-docker-linux-amd64.tar.gz` | Docker Linux AMD64 离线镜像归档（`docker load`） |
| `LyraNest-0.2.8-docker-linux-arm64.tar.gz` | Docker Linux ARM64 离线镜像归档（`docker load`） |
| `docker-compose.yml` | Docker Compose 在线部署配置 |

## 飞牛 fnOS 原生 FPK 安装（推荐）

飞牛 NAS 用户请从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载对应架构的 FPK：x86_64 使用 `LyraNest-0.2.8-fnos-x86.fpk`，ARM64 使用 `LyraNest-0.2.8-fnos-arm.fpk`；标准版与兼容版二选一，不可同时安装。

安装后，在应用设置中授权音乐目录并启动 LyraNest。默认使用飞牛统一网关访问：在你平时打开飞牛管理界面的局域网地址后追加 `/app/lyranest`。

如需独立局域网端口，可在 LyraNest 应用设置填写 `1024–65535` 的自定义端口，保存后重启应用，再通过 `http://<飞牛局域网地址>:<端口>/` 访问。留空则只保留飞牛网关入口；独立端口仅建议用于可信局域网，不要配置公网端口映射。

## 畅网 NAS (CWNAS / AINAS) 原生 CPK 安装

畅网 NAS 用户可下载 `LyraNest-0.2.8-cwnas.cpk`。在畅网 NAS 系统应用管理器中点击“手动安装 / 本地安装”，选择下载的 `.cpk` 文件即可一键部署并注册后台服务与入口图标。

## 其他 NAS 原生安装包

QNAP、Synology DSM、绿联 NAS 与铁威马 TOS 7 用户可从 [GitHub 最新发行版](https://github.com/WHWgogogo/LyraNest/releases/latest) 下载对应的原生包，在各自系统的应用中心或套件中心选择手动安装。请先在 NAS 系统信息中确认 CPU 架构：x86/x86_64 或 AMD64 设备使用 `x86_64`/`amd64` 文件，ARM64 设备使用 `arm_64`/`armv8`/`aarch64` 文件；不同 NAS 系统的安装包不能交叉安装。

- QNAP：`LyraNest-0.2.8-qnap-x86_64.qpkg` 或 `LyraNest-0.2.8-qnap-arm_64.qpkg`。
- Synology DSM：`LyraNest-0.2.8-synology-x86_64.spk` 或 `LyraNest-0.2.8-synology-armv8.spk`。
- 绿联 NAS：`LyraNest-0.2.8-ugnas-amd64.upk` 或 `LyraNest-0.2.8-ugnas-arm64.upk`。
- 铁威马 TOS 7：`LyraNest-0.2.8-terramaster-x86_64.deb` 或 `LyraNest-0.2.8-terramaster-aarch64.deb`。

## Docker 镜像

服务端镜像统一命名为：

```text
ghcr.io/whwgogogo/lyranest-server:0.2.8
```

生产环境请固定 `LYRANEST_VERSION=0.2.8`。同时发布 `0.2.8` 与 `latest` 标签，其中 `latest` 指向当前稳定版 `0.2.8`；同一个多架构标签会按设备自动选择 AMD64 或 ARM64 镜像。

> 如果 Docker 报出 `proxyconnect tcp ... 127.0.0.1:27897: connect: connection refused`，请移除 Docker 守护进程中失效的 HTTP/HTTPS 代理后再拉取。若设备不能联网，可使用本次发行的 Docker 离线包并按下方命令导入和标记镜像。

## Docker Compose 部署

根目录的 [`docker-compose.yml`](docker-compose.yml) 与发行附件使用同一个正式镜像和版本：

```yaml
services:
  music-server:
    image: ghcr.io/whwgogogo/lyranest-server:${LYRANEST_VERSION:-0.2.8}
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
      MUSICBRAINZ_USER_AGENT: "LyraNest/0.2.8 (+https://github.com/WHWgogogo/LyraNest)"
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

优先下载与设备架构匹配的 Docker 离线镜像归档：AMD64 使用 `LyraNest-0.2.8-docker-linux-amd64.tar.gz`，ARM64 使用 `LyraNest-0.2.8-docker-linux-arm64.tar.gz`。两份归档均包含完整镜像，按设备架构选择其中一份即可。

```bash
docker load -i LyraNest-0.2.8-docker-linux-amd64.tar.gz
docker tag lyranest-server:0.2.8 ghcr.io/whwgogogo/lyranest-server:0.2.8
curl -fLO https://github.com/WHWgogogo/LyraNest/releases/latest/download/docker-compose.yml
mkdir -p music downloads data cache
docker compose up -d --pull never
```

ARM64 设备使用下面的归档和本地标签：

```bash
docker load -i LyraNest-0.2.8-docker-linux-arm64.tar.gz
docker tag lyranest-server:0.2.8-arm64 ghcr.io/whwgogogo/lyranest-server:0.2.8
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

## 官方插件与扩展生态
 
LyraNest 提供模块化的外部音频输出与设备桥接插件，均已独立开源发布并支持 Docker Compose 与全 NAS 原生部署：

- [LyraNest AirPlay Bridge](https://github.com/WHWgogogo/LyraNest-AirPlay-Bridge)：AirPlay 2 无线音频桥接服务，支持将曲库音频投送至苹果 HomePod、Apple TV 及第三方 AirPlay 兼容音箱，支持全端独立音量与多房间同步。
- [LyraNest Local Output](https://github.com/WHWgogogo/LyraNest-Local-Output)：NAS 本机 3.5mm 耳机孔与 USB DAC 外置声卡直出服务，极低内存占用（约 13MB），提供母带级无损直通输出。
- [LyraNest Xiaomi Bridge](https://github.com/WHWgogogo/LyraNest-Xiaomi-Bridge)：小爱音箱语音联动与投送桥接服务，支持多音箱隔离、语音点播曲库/歌单与断点续播。

## 项目友链

- [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)：MIT 许可的开源基础版本。
- [LyraNest Releases](https://github.com/WHWgogogo/LyraNest/releases/latest)：完整发行版的最新下载页。
- [simple_sq_music_plus](https://github.com/59799517/simple_sq_music_plus)：SQ 音乐下载插件项目。
- [Solara](https://github.com/akudamatata/Solara)：Solara 音乐下载插件项目。
- [GoMusic](https://github.com/Bistutu/GoMusic)：GoMusic 歌单导入项目。

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
