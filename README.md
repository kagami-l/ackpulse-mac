# AckPulse

[简体中文](README.zh-CN.md)

AckPulse brings notifications and approval actions from coding agents on your Mac to iPhone and Apple Watch.

> **Beta:** AckPulse is designed for coding-agent workflows, but the current beta integrates with Claude Code only. Other agents are not yet supported.

## Requirements

- macOS 14 or later. The current Mac beta is a Universal build for Apple silicon and Intel Macs.
- iOS 17 or later and, for Apple Watch, watchOS 10 or later.
- AckPulse for iPhone from TestFlight and AckPulse for Mac.
- A trusted local network that both the Mac and iPhone can reach. Bluetooth should be on for Apple Watch notification mirroring.
- Claude Code installed on the Mac for the current beta.

## Download

Download AckPulse for Mac from this repository's [Releases](../../releases) page. The current review combination is Mac `0.1.2 (2)` with iPhone and Watch TestFlight build `0.1.2 (1)`. The Mac app is signed and notarized.

The Mac app does not update itself. To update, quit AckPulse, replace it in `/Applications` with the newer release, and reopen it.

## Set up and test an approval

1. Download and unzip the Mac release. Move `AckPulse.app` to `/Applications` **before opening it**, then open it normally. AckPulse appears in the menu bar.
2. Open the TestFlight build on the iPhone. Allow **Notifications** and **Local Network** access, and keep the iPhone and Mac on the same trusted network.
3. On the Mac, expand **Paired iPhones** and choose **Generate new pairing code**. On the iPhone, select the Mac under **Discovered on LAN** (or enter its address manually), enter the six-digit code and a device label, then choose **Pair with Mac**.
4. In the Mac menu, add the test project under **Routed projects**. Under **Agents**, enable **Claude Code**, then enable **Hold Bash commands for approval — BETA**. Enabling the agent adds hooks to Claude Code's settings and backs up an existing settings file before modifying it.
5. Confirm that the iPhone shows **Connected** and its recent events include **Uploaded APNs registration to Mac**.
6. Start Claude Code inside the routed project and ask it to run a harmless Bash command such as `pwd`. Choose **Approve** or **Deny** on the iPhone or Apple Watch and confirm that Claude Code continues with that result.

The approval option currently holds **every** Bash call in a routed project, including calls Claude Code might not otherwise ask about. Turn it off after testing if you do not want that behavior. The main **Claude Code** option can remain on for non-blocking completion and input alerts.

## Current limitations

- One iPhone installation can have only one active Mac pairing at a time. One Mac can pair with multiple iPhones.
- Mac–iPhone traffic on the local network uses unencrypted HTTP. Use AckPulse only on a network you trust.
- Lock-screen and Apple Watch alerts depend on the Mac's internet connection and external notification services. A foreground iPhone connected directly to the Mac may continue receiving events if those services fail. Notifications are not guaranteed to be delivered or replayed.
- The Mac app has no automatic update mechanism; install updates manually from Releases.

## Troubleshooting

**The Mac does not appear on the iPhone:** Confirm that both devices can reach the same local network and that Local Network access is enabled in iPhone Settings → AckPulse. Reopen the iPhone app. If discovery still fails, use the Mac's local address and port `37645` under **Manual host / port**.

**Pairing succeeds but push registration does not:** Look for **Uploaded APNs registration to Mac** in the iPhone's recent events. If it is missing, allow Notifications in iPhone Settings → AckPulse, fully close and reopen the app, then reconnect. **Push registrations** on the Mac should be greater than zero.

**The Mac shows a pending approval but no alert arrives:** A working local connection does not guarantee remote notification delivery. Check the Mac's internet connection and confirm that **Push registrations** is nonzero. The foreground local-network path may still work while lock-screen and Watch alerts do not.

**Hooks produce no events:** Keep AckPulse in `/Applications`, confirm that the project is under **Routed projects**, and check the Claude Code options. If AckPulse shows that hooks point to an old location, use **Fix**.

**Switching to another Mac:** Use **Change Mac** or **Remove pairing** on the iPhone first. If the old Mac is unreachable, AckPulse explains the residual-notification risk before offering **Forget previous Mac and continue**. Remove that iPhone from the old Mac when it becomes available.

## Diagnostics and privacy

Use **Copy diagnostics** in the Mac menu or the iPhone's **Diagnostics** section. Diagnostics are not uploaded automatically; review copied information before sharing it and do not publish credentials or sensitive project or event content.

See the [AckPulse Privacy Policy](PRIVACY.md) for information about local-network and cloud processing, storage, permissions, retention, and deletion.
