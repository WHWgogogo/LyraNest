# LyraNest 0.2.4 更新日志

发布日期：2026 年 8 月 15 日

## 更新内容

- 修复客户端曲库字母轴在弱网、连续点击字母、切换排序或刷新时可能跳到错误位置的问题；旧分页请求不再覆盖最新跳转结果。
- 继续保留字母跳转后的前一页内容，向上滑动仍可查看该字母之前的曲目。
- Android 播放体验修复：恢复后台播放时的退出二次确认，并完善播放页歌词与曲目信息入口。
- 完善响应式封面、曲库分页、下载/离线页面与目录封面的稳定性修复。
- 服务端发行镜像内置 FFmpeg，转码能力可用时由服务端提前声明；同时保留客户端对旧服务端的兼容行为。
- 歌词搜索、歌单导入/导出、插件中心、下载插件与下载队列相关功能继续包含在 0.2.4 中。

## 飞牛包说明

- `LyraNest-0.2.4-fnos-x86.fpk`：标准飞牛 x86_64 版本，支持飞牛统一网关应用入口。
- `LyraNest-0.2.4-fnos-arm.fpk`：标准飞牛 ARM64 版本，支持飞牛统一网关应用入口。
- `LyraNest-Compat-0.2.4-fnos-x86.fpk`：x86_64 兼容版，不依赖统一网关集成。
- `LyraNest-Compat-0.2.4-fnos-arm.fpk`：ARM64 兼容版，不依赖统一网关集成。

请按 NAS CPU 架构只安装其中一个对应 FPK；标准版与兼容版不可同时安装。

## 客户端包

- Android 手机/平板：`LyraNest-0.2.4-android-arm64.apk`
- Windows x64：`LyraNest-0.2.4-windows-x64.zip`
- TV ARM64：`LyraNest-0.2.4-tv-arm64-v8a.apk`
- TV ARMv7：`LyraNest-0.2.4-tv-armeabi-v7a.apk`

## Docker 离线部署包

- `LyraNest-0.2.4-docker-linux-amd64.tar.gz`：Linux AMD64 离线部署包，包含对应架构的服务端二进制、`Dockerfile.prebuilt` 与 Compose 配置。
- `LyraNest-0.2.4-docker-linux-arm64.tar.gz`：Linux ARM64 离线部署包，包含对应架构的服务端二进制、`Dockerfile.prebuilt` 与 Compose 配置。

离线包可直接执行 `docker compose up -d --build --pull never`，镜像构建阶段由 Alpine 安装 FFmpeg。

## 校验

GitHub Release 附件页会显示每个附件的 SHA-256 摘要，可直接用于校验下载文件完整性。
