# AckPulse

[简体中文](README.zh-CN.md)

AckPulse brings notifications and permission approvals from Claude Code and Codex on your Mac to iPhone and Apple Watch.

This repository publishes the Mac app's releases. Downloads, help and the recommended version are on [ackpulse.cc](https://ackpulse.cc/).

## Requirements and download

- macOS 14 or later; the Mac app supports Apple silicon and Intel Macs.
- iOS 17 or later. Apple Watch is optional and requires watchOS 10 or later.
- Claude Code or Codex installed and run at least once on the Mac.
- A trusted local network reachable by both Mac and iPhone.

Download the signed and notarized Mac app from [ackpulse.cc](https://ackpulse.cc/). [Releases](../../releases) carry the same DMG files with their SHA-256 checksums. The iPhone app, with its optional Apple Watch app, is distributed through the App Store; see the website for availability.

AckPulse 1.x on Mac, iPhone and Apple Watch can be mixed, with newer features limited by the older app. The 0.1.x beta builds are not compatible with 1.x; update every device to 1.x.

## Install and connect

1. Open the DMG, drag **AckPulse** into **Applications** and eject the disk image. Open AckPulse from Applications; do not run it from inside the DMG.
2. On Mac, open **Devices → Add iPhone** and choose **Generate Pairing Code**.
3. On iPhone, scan the QR code, or connect manually with the address, port and six-digit code shown on Mac. Allow Local Network access and Notifications; camera access is only needed for scanning.
4. On Mac, add your working folder under **Projects** and connect Claude Code or Codex under **Integrations**. For Codex, review and trust AckPulse's hooks in Codex when prompted, then check the integration status in AckPulse.
5. Start a task in that folder. When the agent asks for permission, choose **Allow once** or **Deny** on iPhone or Apple Watch. Allowing may let the requested operation run on your Mac.

Claude's terminal prompt remains answerable during remote approval; the first answer wins. Codex waits for a remote answer first, then returns to its configured approval flow if no answer arrives in time. Answer questions and plans in the agent on your Mac.

## Update

The Mac app has no automatic updater. Finish pending approvals and choose **Quit AckPulse**; closing the window keeps the service running. Replace AckPulse in Applications with the app from the new DMG, eject the image and reopen AckPulse. Pairing, projects, preferences and history are kept.

After updating, follow any prompts in **Integrations**: **Complete Approval Setup** for Claude, or **Complete Codex Setup** for Codex followed by trusting the updated hooks in Codex. If an agent still points to another copy of AckPulse, use **Review and Repair…** for Claude or **Repair Codex Connection** for Codex.

If AckPulse reports incompatible versions, update the app on the device it names. Re-pairing or clearing data does not fix a version mismatch.

## Troubleshooting

- **Cannot connect:** check that AckPulse is running on Mac, Local Network access is allowed on iPhone, and both devices are on the same trusted network. Guest Wi-Fi, device isolation, VPN routing and firewalls can block the connection. Use manual connection with the address and port shown on Mac.
- **No notifications:** allow Notifications, check Focus settings, then open AckPulse on iPhone and reconnect. Check the iPhone's push registration under **Devices** on Mac.
- **No approval:** check the project and integration settings. The agent must actually be asking for permission. For Codex, also check hook trust and the remote approval wait time.
- **Switch Mac:** use **Settings → Mac** on iPhone to change Mac or remove pairing. **Forget Previous Mac and Continue** clears only the iPhone side; remove that iPhone under **Devices** on the old Mac when it is available.

Use AckPulse only on a trusted network: local traffic uses unencrypted HTTP. Notifications depend on connectivity and system delivery. Approvals need a live request and a connection to the paired Mac; old notifications cannot approve an ended request.

## Support and privacy

See [AckPulse Support](https://ackpulse.cc/support/) or email [hi@ackpulse.cc](mailto:hi@ackpulse.cc). Report reproducible problems in [Issues](../../issues); issues are public, so remove credentials and private project or event details first.

Diagnostics stay on your devices unless you choose to copy and share them; review copied information before sharing. Read the [Privacy Policy](https://ackpulse.cc/privacy/) (a [copy](PRIVACY.md) is kept here) and the [Terms](https://ackpulse.cc/terms/).
