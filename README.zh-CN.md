# AckPulse

[English](README.md)

AckPulse 将 Mac 上 coding agent 的通知与审批操作发送到 iPhone 和 Apple Watch。

> **Beta：** AckPulse 面向 coding agent 工作流设计，但当前测试版只集成了 Claude Code，尚不支持其他 agent。

## 使用要求

- macOS 14 或更高版本。当前 Mac 测试版是同时支持 Apple 芯片和 Intel Mac 的 Universal 构建。
- iOS 17 或更高版本；使用 Apple Watch 时需要 watchOS 10 或更高版本。
- 通过 TestFlight 安装的 AckPulse iPhone App，以及 AckPulse for Mac。
- Mac 和 iPhone 都能访问的可信局域网。使用 Apple Watch 通知镜像时还应打开蓝牙。
- 当前测试版需要在 Mac 上安装 Claude Code。

## 下载

请从本仓库的 [Releases](../../releases) 页面下载 AckPulse for Mac。当前审核组合为 Mac `0.1.2 (2)` 与 iPhone、Watch 的 TestFlight 构建 `0.1.2 (1)`。Mac App 已签名并经过 Apple 公证。

Mac App 不会自动更新。更新时，请退出 AckPulse，用较新的 Release 替换 `/Applications` 中的 App，然后重新打开。

## 设置并测试一次审批

1. 下载并解压 Mac Release。**首次打开前**先把 `AckPulse.app` 移到 `/Applications`，再正常打开；AckPulse 会出现在菜单栏。
2. 在 iPhone 上打开 TestFlight 构建，允许**通知**和**本地网络**权限，并让 iPhone 与 Mac 保持在同一个可信网络中。
3. 在 Mac 上展开 **Paired iPhones**，选择 **Generate new pairing code**。在 iPhone 的 **Discovered on LAN** 中选择这台 Mac（也可手工填写地址），输入六位配对码和设备标签，再选择 **Pair with Mac**。
4. 在 Mac 菜单的 **Routed projects** 下添加测试项目。在 **Agents** 下启用 **Claude Code**，再启用 **Hold Bash commands for approval — BETA**。启用 agent 时，AckPulse 会为 Claude Code 设置添加 hooks；如果已有设置文件，则会在修改前先备份该文件。
5. 确认 iPhone 显示 **Connected**，并且最近事件中出现 **Uploaded APNs registration to Mac**。
6. 在刚才路由的项目中启动 Claude Code，让它执行一条无害的 Bash 命令，例如 `pwd`。在 iPhone 或 Apple Watch 上选择 **Approve** 或 **Deny**，再确认 Claude Code 按该结果继续。

当前审批选项会拦住路由项目中的**每一条** Bash 调用，包括 Claude Code 原本可能不会询问的调用。如果日常不需要这一行为，测试后请关闭该选项。主 **Claude Code** 选项可以继续保留，用于接收非阻塞的完成和输入提醒。

## 当前限制

- 每个 iPhone 安装实例同一时间只能与一台 Mac 保持活动配对；一台 Mac 可以配对多台 iPhone。
- Mac 与 iPhone 之间的局域网流量使用未加密 HTTP。请只在可信网络中使用 AckPulse。
- 锁屏和 Apple Watch 提醒依赖 Mac 的互联网连接及外部通知服务。如果这些服务失败，直接连接 Mac 的前台 iPhone 仍可能继续收到事件。不保证通知一定送达或补发。
- Mac App 没有自动更新机制，需要从 Releases 手工安装更新。

## 排障

**iPhone 找不到 Mac：** 确认两台设备都能访问同一个局域网，并在 iPhone“设置”→ AckPulse 中开启“本地网络”权限，然后重新打开 iPhone App。如果仍找不到 Mac，请在 **Manual host / port** 中填写 Mac 的局域网地址和端口 `37645`。

**配对成功但推送未登记：** 在 iPhone 最近事件中查找 **Uploaded APNs registration to Mac**。如果没有，请在 iPhone“设置”→ AckPulse 中允许通知，彻底关闭并重新打开 App，再重新连接。Mac 上的 **Push registrations** 应大于零。

**Mac 显示 Pending，但没有收到提醒：** 局域网连接正常不代表远程通知一定能送达。请检查 Mac 的互联网连接，并确认 **Push registrations** 大于零。锁屏和 Watch 提醒失败时，前台局域网路径可能仍然正常。

**Hooks 没有产生事件：** 保持 AckPulse 位于 `/Applications`，确认项目已列在 **Routed projects** 中，并检查 Claude Code 选项。如果 AckPulse 提示 hooks 仍指向旧位置，请使用 **Fix**。

**切换到另一台 Mac：** 先在 iPhone 上使用 **Change Mac** 或 **Remove pairing**。如果旧 Mac 无法访问，AckPulse 会先说明残留通知风险，再提供 **Forget previous Mac and continue**。旧 Mac 恢复可用后，请在旧 Mac 上移除这台 iPhone。

## 诊断与隐私

在 Mac 菜单或 iPhone 的 **Diagnostics** 中使用 **Copy diagnostics**。诊断不会自动上传；分享前请检查复制的信息，不要公开凭据或敏感的项目、事件内容。

局域网与云端处理、存储、权限、保留和删除的说明见 [AckPulse 隐私政策](PRIVACY.zh-CN.md)。
