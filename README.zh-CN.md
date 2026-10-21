# AckPulse

[English](README.md)

AckPulse 将 Mac 上 Claude Code 和 Codex 的通知与权限审批发送到 iPhone 和 Apple Watch。

## 使用要求与下载

- macOS 14 或更高版本，支持 Apple 芯片和 Intel Mac。
- iOS 17 或更高版本；Apple Watch 可选，需要 watchOS 10 或更高版本。
- Mac 上已安装并至少运行过一次 Claude Code 或 Codex。
- Mac 与 iPhone 能相互访问的可信局域网。

下载已签名并公证的 [AckPulse for Mac 0.1.3 (5)](../../releases/tag/0.1.3-3)，配套 iPhone／Watch TestFlight **0.1.3 (3)**。先更新 iPhone 及其 Watch App，再更新 Mac，请使用这组配套构建。

TestFlight 可用状态取决于所在测试组及 Apple 的处理或审核结果。下载 Mac App 不会自动获得 iPhone 测试资格。

## 安装与连接

1. 打开 DMG，将 **AckPulse** 拖入 **应用程序**，推出磁盘映像后从 `/Applications` 启动。
2. Mac 打开“设备 → 添加 iPhone”，生成配对码。
3. iPhone 扫描二维码，或填写 Mac 显示的地址、端口和六位码手动连接；允许本地网络和通知权限。
4. 在 Mac“项目”页添加工作文件夹，在“集成”页连接 Claude Code 或 Codex。Codex 还需按提示在 Codex 中审阅并信任 AckPulse Hook，再回到 AckPulse 检查状态。
5. 在该文件夹中开始任务。当 agent 请求权限时，在 iPhone 或 Watch 批准或拒绝。批准可能让对应操作在 Mac 执行。

Claude 的终端提示仍可回答，先响应者生效。Codex 会先等待远端回答，超时后交回其原有审批流程。提问和计划需回到 Mac 上的 agent 作答。

## 更新

先处理完等待中的审批，从菜单选择“退出 AckPulse”，再用新 DMG 替换。关闭窗口不会退出服务；更新保留配对、项目和偏好，目前需手动安装更新。

更新后查看“集成”页的设置提示。如有提示，Claude 点击“完成审批配置”，Codex 点击“完成 Codex 配置”并在 Codex 中重新审阅信任。旧版 Claude 用户可按需开启“活跃会话名单”。

## 排障

- **无法连接：** 检查本地网络权限和两端网络是否互通；可按 Mac 显示的地址与端口手动连接。
- **没有通知：** 允许通知，重新打开 iPhone App 并重连；检查手机诊断中的推送登记及 Mac 的设备状态。
- **没有审批：** 检查项目与集成设置，确认 agent 确实正在请求权限；Codex 还需检查 Hook 信任状态及远程等待时间。
- **App 位置变化：** 在“集成 → 检查并修复…”中查看并修复旧 App 路径。
- **更换 Mac：** 在 iPhone“设置 → Mac”更换或移除配对；旧 Mac 不可达时，待其恢复后再移除原 iPhone 登记。

请只在可信网络使用：局域网通信使用未加密 HTTP。通知受网络和系统投递影响；审批需要仍有效的请求及与配对 Mac 的连接，旧通知不能批准已结束请求。

数据处理详情见[隐私政策](PRIVACY.zh-CN.md)。诊断保存在本地，只有主动复制并分享时才会离开设备，分享前请检查内容。
