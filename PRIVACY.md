# AckPulse Privacy Policy

[简体中文](PRIVACY.zh-CN.md)

**Effective date: September 12, 2026**

This policy describes the current AckPulse beta for iPhone, Apple Watch, and Mac. AckPulse does not require an AckPulse account.

## Information on your devices and local network

AckPulse keeps its working data primarily on your devices. This includes routed project paths, commands and event details, approval state and decisions, pairing information, device labels and technical identifiers, settings, and diagnostics.

After pairing, the iPhone communicates directly with the Mac over the local network to receive event details and return approval decisions. This traffic is not automatically uploaded to AckPulse. The local connection uses unencrypted HTTP, so pair and use AckPulse only on a trusted network.

## Notifications and service providers

To deliver system notifications, including lock-screen and Apple Watch alerts, AckPulse sends the minimum technical identifiers and event-routing information needed for delivery to a cloud infrastructure provider over HTTPS. That provider passes a generic notification to Apple Push Notification service (APNs).

Commands, project and file paths, file contents, approval details, and approval decisions are not included in this cloud notification flow. When possible, the iPhone retrieves those details directly from the paired Mac over the local network.

The cloud infrastructure may derive country-level information from connection metadata and process limited delivery diagnostics for reliability, security, troubleshooting, and abuse prevention. This country-level information is the coarse location disclosed for AckPulse; AckPulse does not request GPS or device Location Services permission.

AckPulse uses a cloud infrastructure provider and [Apple](https://www.apple.com/legal/privacy/) to provide notification delivery. Service providers processing information on behalf of AckPulse are required to protect it consistently with this policy and applicable requirements.

## How information is used

Technical device identifiers, country-level information, and delivery diagnostics are used only to provide pairing, notifications, approval actions, reliability, security, and troubleshooting. They may be associated with a device but are not used for tracking.

AckPulse does not use data for advertising or analytics, does not sell data, and does not track people across apps or websites.

## Permissions

- **Camera (optional):** scans the pairing QR code displayed by your Mac. Scanning happens on the iPhone; AckPulse does not save or upload camera images. You can pair manually without camera permission.
- **Local Network:** discovers and connects to AckPulse for Mac, receives event details, and returns decisions.
- **Notifications:** displays alerts and actions on iPhone and, through Apple's notification mirroring, Apple Watch.

You can revoke any of these permissions in iPhone Settings. Features that depend on that permission will stop working.

## Diagnostics

Diagnostics are stored locally and are not automatically uploaded. The iPhone provides **Clear logs** under **Settings → Diagnostics → Technical details**. Use **Copy Diagnostics** on Mac or **Refresh and copy diagnostics** in iPhone diagnostics; copied information leaves your device only if you choose to share it. Review it before sharing and do not publish credentials or sensitive project or event content.

## Retention and deletion

- Recent event records and their details are retained locally for seven days. Pending approvals are not removed by this age limit; the retention window for resolved requests starts when they end. iPhone record caches use device file protection and are excluded from cloud backup. Removing or changing the iPhone pairing clears its local record cache; the Mac history is retained independently.
- Other local information, such as pairing and settings, remains until you remove it using AckPulse controls or delete the relevant app data.
- **Remove pairing** on the iPhone asks a reachable Mac to revoke the pairing and its notification registration, then clears the iPhone's current pairing. You can also remove an iPhone under **Devices** on the Mac.
- If an old Mac is unreachable and you choose **Forget previous Mac and continue**, only the iPhone's local pairing is cleared. Remove the iPhone from the old Mac when it becomes available; until then, residual generic notifications may continue.
- Removing a pairing does not erase Mac approval history or all other local app data. To remove the remaining Mac data, first disable the AckPulse Claude Code integration, quit AckPulse, and delete AckPulse's local app data and the app if desired.
- Some device-local pairing and installation information kept in secure device storage may remain after uninstalling the iPhone app. Remove the pairing before uninstalling when possible. If retained, the installation identifier remains only on that iPhone, is not synchronized through iCloud, and is used only for AckPulse functionality.
- AckPulse currently retains its cloud delivery logs for up to 3 days. Service providers may separately retain connection or platform metadata under their own terms. AckPulse does not maintain a user account or cloud user profile.

For beta privacy questions or help deleting local data, use **Send Beta Feedback** for AckPulse in TestFlight.

## Changes to this policy

This policy may change as AckPulse changes. Material changes to data handling will be published here with a new effective date before they apply to a distributed build.
