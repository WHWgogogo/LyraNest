# LyraNest（律巢）

<p align="center">
  <img src="docs/images/lyranest-logo.png" alt="LyraNest Logo" width="150" />
</p>

<p align="center">一套面向个人 NAS、家庭服务器与局域网音乐库的自托管音乐服务。</p>

<p align="center">
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest"><img src="https://img.shields.io/github/v/release/WHWgogogo/LyraNest?display_name=tag&label=Release" alt="Latest Release" /></a>
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest"><img src="https://img.shields.io/badge/Platform-Android%20%7C%20Windows-4f46e5" alt="Platforms" /></a>
  <a href="docker-compose.yml"><img src="https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white" alt="Docker Compose" /></a>
</p>

<p align="center">
  <a href="https://github.com/WHWgogogo/LyraNest/releases/latest">下载最新版</a> ·
  <a href="#docker-compose-部署">Docker 部署</a> ·
  <a href="releases/0.1.8/CHANGELOG.md">更新日志</a> ·
  <a href="https://github.com/WHWgogogo/LyraNest-Community">开源社区版</a>
</p>

> **发行版说明**：此仓库用于发布 LyraNest 的客户端安装包、Docker 部署配置与更新记录，不包含完整版本源代码。若需要开源、可自行构建的基础版本，请前往 [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)。

将音乐文件保存在自己的服务器、NAS 或电脑中，即可通过 Web、Windows 和 Android 客户端管理、播放并同步个人音乐库。

当前稳定版本：`0.1.8`

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
| `docker-compose.yml` | Docker Compose 部署配置 |
| `LyraNest.env.example` | Docker 环境变量示例 |
| `SHA256SUMS.txt` | 发行文件 SHA-256 校验值 |

## Docker 镜像

服务端镜像统一命名为：

```text
ghcr.io/whwgogogo/lyranest-server:0.1.8
```

如需跟随后续发行，可将 Compose 中的 `LYRANEST_VERSION` 改为已发布的明确版本号；生产环境建议固定具体版本，便于回滚。

## Docker Compose 部署

### 1. 准备目录与配置

```bash
git clone https://github.com/WHWgogogo/LyraNest.git
cd LyraNest
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
| `LYRANEST_VERSION` | `0.1.8` | 服务端镜像版本 |

### 2. 启动与检查

```bash
docker compose pull
docker compose up -d
docker compose ps
curl http://127.0.0.1:8080/health
```

首次启动后，可使用 `http://服务器地址:8080` 打开网页端；Windows 与 Android 客户端填写相同的服务器地址并登录即可。

## 版本与校验

- 每个版本都保留独立 GitHub Release 与附件，不会覆盖旧版本。
- README 的下载入口使用 GitHub `releases/latest`，始终指向最新稳定发行。
- 下载完成后可用 `SHA256SUMS.txt` 校验文件完整性。
- 详细更新内容请查看对应版本的 `CHANGELOG.md`。

## 相关项目

- [LyraNest Community](https://github.com/WHWgogogo/LyraNest-Community)：MIT 许可的开源基础版本。
- [LyraNest Releases](https://github.com/WHWgogogo/LyraNest/releases/latest)：完整发行版的最新下载页。
