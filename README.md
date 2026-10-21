# AckPulse

[简体中文](README.zh-CN.md)

AckPulse brings notifications and permission approvals from Claude Code and Codex on your Mac to iPhone and Apple Watch.

## Requirements and download

- macOS 14 or later; the Mac app supports Apple silicon and Intel Macs.
- iOS 17 or later. Apple Watch is optional and requires watchOS 10 or later.
- Claude Code or Codex installed and run at least once on the Mac.
- A trusted local network reachable by both Mac and iPhone.

Download the signed and notarized [AckPulse for Mac 0.1.3 (5)](../../releases/tag/0.1.3-3). Use it with iPhone and Watch TestFlight **0.1.3 (3)**. Update the iPhone and its Watch app first, then the Mac app. Use this build combination together.

TestFlight access depends on your test group and Apple's processing or review status. Downloading the Mac app does not grant access to the iPhone beta.

## Install and connect

1. Open the DMG, drag **AckPulse** into **Applications**, and eject the disk image. Open AckPulse from `/Applications`.
2. On Mac, open **Devices → Add iPhone** and generate a pairing code.
3. On iPhone, scan the QR code, or connect manually with the address, port and six-digit code shown on Mac. Allow Local Network access and Notifications.
4. On Mac, add your working folder under **Projects**. Open **Integrations** and connect Claude Code or Codex. For Codex, review and trust AckPulse's hooks in Codex when prompted; return to AckPulse and check the integration status.
5. Start a task in that folder. When the agent asks for permission, approve or deny on iPhone or Watch. Approving may allow the requested operation to run on your Mac.

Claude's terminal prompt remains answerable during remote approval; the first answer wins. Codex waits for a remote answer first, then returns to its configured approval flow if no answer arrives in time. Answer questions and plans in the agent on your Mac.

## Update

Finish pending approvals and choose **Quit AckPulse** before replacing the app with the new DMG. Closing the window keeps the service running. Pairing, projects and preferences are kept; updates are installed manually.

After updating, follow any setup prompts in **Integrations**. If shown, use **Complete Approval Setup** for Claude or **Complete Codex Setup** for Codex; review and trust updated Codex hooks in Codex. Existing Claude users can enable **Active session list** if wanted.

## Troubleshooting

- **Cannot connect:** check Local Network permission and that both devices are on the same reachable network. Use manual connection with the address and port shown on Mac.
- **No notifications:** allow Notifications, reopen AckPulse on iPhone and reconnect. Check push registration in iPhone diagnostics and the device status on Mac.
- **No approval:** check the project and integration settings. The agent must actually be asking for permission. For Codex, also check hook trust and the remote approval wait time.
- **App moved:** use **Integrations → Review and Repair…** to review and repair references to an old app location.
- **Switch Mac:** use **Settings → Mac** on iPhone to change Mac or remove pairing. If the old Mac is unreachable, remove the old iPhone entry there when it becomes available.

Use AckPulse only on a trusted network: local traffic uses unencrypted HTTP. Notifications depend on connectivity and system delivery. Approvals need a live request and a connection to the paired Mac; old notifications cannot approve an ended request.

See the [Privacy Policy](PRIVACY.md). Diagnostics stay on your devices unless you choose to copy and share them; review copied information before sharing.
