# AckPulse

[简体中文](README.zh-CN.md)

AckPulse brings notifications and permission approvals from coding agents on your Mac to iPhone and Apple Watch.

> **Beta:** The current beta integrates with Claude Code. Other agents are not yet supported.

## Requirements

- macOS 14 or later. The Mac app is a Universal build for Apple silicon and Intel Macs.
- iOS 17 or later; Apple Watch is optional and requires watchOS 10 or later.
- AckPulse for iPhone from TestFlight and AckPulse for Mac, both on version **0.1.3**.
- A trusted local network reachable by both Mac and iPhone. Keep Bluetooth on for Apple Watch notification mirroring.
- Claude Code installed and run at least once on the Mac for the integration.

## Download

Download the signed and notarized [AckPulse for Mac 0.1.3 DMG](../../releases/tag/0.1.3). Use Mac **0.1.3 (4)** with iPhone and Watch TestFlight build **0.1.3 (2)**. Update all three apps together before testing; older versions are not a supported combination.

TestFlight availability depends on your test group and Apple's processing or review status. A Mac release does not itself grant access to the iPhone beta.

## Install and update

1. Open the downloaded DMG and drag **AckPulse** into **Applications**.
2. Eject the disk image, then open AckPulse from `/Applications`.
3. Follow the Mac window's **Overview** to connect your iPhone and choose projects.

To update, finish any pending approvals, choose **Quit AckPulse** from its menu, and replace the app using the new DMG. Closing the window keeps the service running. Replacing the app does not intentionally remove pairing, projects, or language preferences. The app has no automatic updater.

If the integration points to an older copy of the app, use **Integrations → Review and Repair…**, inspect the old path, and confirm the repair. Keep the app in `/Applications`; connecting Claude Code is disabled while running from the disk image.

## Set up and test an approval

1. On Mac, open **Devices → Add iPhone**, select the local-network address, and generate a pairing code.
2. On iPhone, choose **Scan QR Code** and scan the code on Mac. Camera permission is optional: **Connect Manually** accepts the address, port, and six-digit code shown on Mac. Allow Local Network access when prompted, and Notifications after pairing.
3. Confirm that the iPhone is connected to the intended Mac. On Mac, open **Projects** and add a test folder; its subfolders are included.
4. In **Integrations**, enable **Connect Claude Code** and check **Remote permission approvals**. Enabling the connection initially enables its alert options too. AckPulse backs up the existing Claude settings before updating its hooks.
5. Start Claude Code in that folder using a mode that asks for permissions. Ask it to perform a harmless operation that actually requires permission, such as creating a disposable test file. An already allowed command may not produce an approval request.
6. Choose **Approve** or **Deny** in AckPulse on iPhone, or long-press its notification to choose an action. With iPhone locked and a paired Watch worn and unlocked, also test the mirrored notification on Watch.

AckPulse forwards Claude's own permission requests across tools. The terminal prompt remains answerable; whichever side answers first determines the result. Approving can execute the requested operation on Mac, and Claude's explicit deny rules still apply. If you answer in the terminal, the remote pending item may remain until Claude finishes that turn.

Waiting, question, plan, and completion alerts are also available. Answer questions and plans in Claude; these alerts do not return an answer from the phone or Watch. A separate waiting alert may arrive while a permission request is pending.

## Current limitations

- One iPhone installation keeps one active Mac pairing; a Mac can pair with multiple iPhones.
- Mac–iPhone local traffic uses unencrypted HTTP. Use a network you trust.
- Lock-screen and Watch alerts depend on the Mac's internet connection and notification services. A connected foreground iPhone can still receive local events when push delivery fails. Notification delivery and replay are not guaranteed.
- Approvals require a live request and a connection to the paired Mac. Old notifications and recent records do not create new approval opportunities.
- Recent records are kept locally for seven days; pending approvals are retained until resolved. Returning to the app can restore missed records, and cached records remain readable offline.
- Install updates manually and keep all apps on the same release version.

## Troubleshooting

**Cannot find or connect to Mac:** Check Local Network permission and network isolation, then use **Connect Manually** with the address and port shown on Mac. The default port is `37645`; use the displayed port if it differs. Generate a fresh pairing code if the previous one expired.

**Connected but no lock-screen notifications:** Allow Notifications in iPhone Settings, reopen AckPulse, and reconnect. Check **Settings → Diagnostics → Push registration** on iPhone and the notification registration count under **Devices** on Mac. A working local connection alone does not confirm push registration.

**No approval request:** Confirm the folder is under **Projects**, the integration and remote approvals are enabled, and Claude is actually asking for permission. Requests already allowed by Claude do not create a remote approval. If hooks point to an old app, inspect **Integrations → Review and Repair…**.

**Switching Macs:** Use **Settings → Mac → Change Mac** or **Remove pairing** on iPhone. If the previous Mac is unreachable, review the residual-notification notice before choosing **Forget Previous Mac and Continue**. Remove the old pairing from that Mac's **Devices** page when it becomes available.

## Diagnostics and privacy

Use **Copy Diagnostics** on Mac or **Settings → Diagnostics → Refresh and copy diagnostics** on iPhone. Diagnostics are not uploaded automatically. Review copied information before sharing; do not publish credentials or sensitive project and event content.

See the [AckPulse Privacy Policy](PRIVACY.md) for processing, storage, permissions, retention, and deletion details.
