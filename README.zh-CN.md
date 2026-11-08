# AckPulse

[English](README.md)

AckPulse 将 Mac 上 Claude Code 和 Codex 的通知与权限审批发送到 iPhone 和 Apple Watch。

本仓库发布 Mac App 的版本。下载、帮助与推荐版本见官网 [ackpulse.cc](https://ackpulse.cc/zh-cn/)。

## 使用要求与下载

- macOS 14 或更高版本，支持 Apple 芯片和 Intel Mac。
- iOS 17 或更高版本；Apple Watch 可选，需要 watchOS 10 或更高版本。
- Mac 上已安装并至少运行过一次 Claude Code 或 Codex。
- Mac 与 iPhone 能相互访问的可信局域网。

从[官网](https://ackpulse.cc/zh-cn/)下载已签名并公证的 Mac App；[Releases](../../releases) 提供相同的 DMG 及其 SHA-256 校验值。iPhone App（含可选的 Apple Watch App）通过 App Store 分发，可用情况见官网。

Mac、iPhone 与 Apple Watch 上的 AckPulse 1.x 可以混用，新功能受较旧一端能力限制。0.1.x 测试版与 1.x 不兼容，请将所有设备更新到 1.x。

## 安装与连接

1. 打开 DMG，将 **AckPulse** 拖入“应用程序”，推出磁盘映像后从“应用程序”启动。不要直接在 DMG 内运行。
2. Mac 打开“设备 → 添加 iPhone”，点“生成配对码”。
3. iPhone 扫描二维码，或填写 Mac 显示的地址、端口和六位码手动连接；允许本地网络和通知权限。相机权限仅扫码时需要。
4. 在 Mac“项目”页添加工作文件夹，在“集成”页连接 Claude Code 或 Codex。Codex 还需按提示在 Codex 中审阅并信任 AckPulse Hook，再回到 AckPulse 检查状态。
5. 在该文件夹中开始任务。当 agent 请求权限时，在 iPhone 或 Watch 选择“允许一次”或“拒绝”。允许可能让对应操作在 Mac 执行。

Claude 的终端提示仍可回答，先响应者生效。Codex 会先等待远端回答，超时后交回其原有审批流程。提问和计划需回到 Mac 上的 agent 作答。

## 更新

Mac App 目前没有自动更新。先处理完等待中的审批，从菜单选择“退出 AckPulse”；关闭窗口不会退出服务。用新 DMG 中的 App 替换“应用程序”中的 AckPulse，推出映像后重新打开。配对、项目、偏好和历史会保留。

更新后查看“集成”页的提示：Claude 点击“完成审批配置”；Codex 点击“完成 Codex 配置”，再在 Codex 中信任更新后的 Hook。如果 agent 仍指向另一份 AckPulse，Claude 使用“检查并修复…”，Codex 使用“修复 Codex 连接”。

如果提示版本不兼容，请按提示更新对应设备上的 AckPulse；重新配对或清空数据不能解决版本不兼容。

## 排障

- **无法连接：** 确认 Mac 上的 AckPulse 正在运行、iPhone 已允许本地网络，且两端在同一可信网络。访客 Wi-Fi、设备隔离、VPN 路由和防火墙都可能阻止连接；可按 Mac 显示的地址与端口手动连接。
- **没有通知：** 允许通知并检查专注模式，再打开 iPhone App 重新连接；在 Mac“设备”页检查该 iPhone 的推送登记。
- **没有审批：** 检查项目与集成设置，确认 agent 确实正在请求权限；Codex 还需检查 Hook 信任状态及远程等待时间。
- **更换 Mac：** 在 iPhone“设置 → Mac”更换或移除配对。“在本机忘记旧 Mac 并继续”只清除 iPhone 一侧；旧 Mac 可用时，请在其“设备”页移除该 iPhone。

请只在可信网络使用：局域网通信使用未加密 HTTP。通知受网络和系统投递影响；审批需要仍有效的请求及与配对 Mac 的连接，旧通知不能批准已结束请求。

## 支持与隐私

见 [AckPulse 支持](https://ackpulse.cc/zh-cn/support/)，或发邮件至 [hi@ackpulse.cc](mailto:hi@ackpulse.cc)。可复现的问题请在 [Issues](../../issues) 报告；Issues 公开可见，发布前请移除凭据和私密的项目、事件信息。

诊断保存在本地，只有主动复制并分享时才会离开设备，分享前请检查内容。详见[隐私政策](https://ackpulse.cc/zh-cn/privacy/)（本仓库保留[副本](PRIVACY.zh-CN.md)）与[条款](https://ackpulse.cc/zh-cn/terms/)。
