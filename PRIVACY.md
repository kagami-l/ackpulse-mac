# AckPulse Privacy Policy

[简体中文](PRIVACY.zh-CN.md)

> This is a copy of the privacy policy published at [ackpulse.cc/privacy](https://ackpulse.cc/privacy/). If the two differ, the website version applies.

**Last updated: November 3, 2026**

This policy covers the AckPulse apps for Mac, iPhone and Apple Watch. “We” means the developer of AckPulse, the seller shown for AckPulse on the App Store. Contact: [hi@ackpulse.cc](mailto:hi@ackpulse.cc).

AckPulse is built to keep your work on your own devices:

- There is no AckPulse account, and we keep no cloud user profile.
- Event details, commands and approvals are stored on your devices and travel directly between your iPhone and Mac over your local network.
- Cloud notifications carry only technical identifiers, never your commands, paths, prompts or decisions. Delivery logs are deleted within three days.
- We do not sell data or use it for advertising, analytics or tracking.

## 1. On your devices and local network

AckPulse stores project paths, commands and event details, approval decisions, pairing information, device identifiers, settings and diagnostics on your devices. When active sessions are enabled, your Mac reads session titles, short prompt summaries, project paths and status from your Agents, keeps them in memory and shares them only with paired devices. They are not saved to history.

Your iPhone retrieves details from your Mac and returns approval decisions over the local network; this traffic does not pass through our servers. The local connection uses unencrypted HTTP, so pair and use AckPulse only on a trusted network.

## 2. Notifications and service providers

To alert you while you are away, your Mac sends a minimal request over HTTPS to our notification relay, hosted by a cloud infrastructure provider, which passes a generic alert to Apple Push Notification service (APNs). The request contains only the Apple push token, limited device and event identifiers, the alert type and a pairing identifier. It never includes commands, session titles, prompt summaries, project or file paths, file contents, approval details or decisions.

The relay can see your Mac's IP address and the approximate location derived from it, and keeps limited delivery logs for operation, security and troubleshooting. We do not request device location permission.

We use a cloud infrastructure provider, [Apple](https://www.apple.com/legal/privacy/) and an email provider, and only choose providers that protect the information they receive to a standard equivalent to this policy. They may process information outside your country or region.

## 3. Permissions and diagnostics

- **Local Network:** connects to your Mac, retrieves details and returns decisions.
- **Notifications:** shows alerts on iPhone and Apple Watch; the system decides where they appear.
- **Camera (optional):** scans the pairing QR code on your iPhone. Images are not saved or uploaded, and manual pairing is available.

You can revoke permissions in iPhone Settings; features that depend on them will stop working. Diagnostics stay on your devices and are never uploaded automatically. They leave your device only if you copy and share them; review them and remove credentials first. You can clear iPhone logs with **Clear logs** in diagnostics.

## 4. Retention and deletion

- Event records are kept on your devices for seven days. For approval requests, this period starts when the request ends; pending approvals are not removed by age. iPhone record caches use file protection and are excluded from cloud backup.
- Removing pairing on iPhone asks a reachable Mac to revoke its access and push registration, and clears the iPhone record cache. You can also remove an iPhone under **Devices** on Mac. Mac history is kept separately. **Forget Previous Mac and Continue** clears only the iPhone side; remove that iPhone on the old Mac when it is available, or generic alerts may continue.
- Pairing, settings and Mac history remain until you remove them or delete the app data. Before deleting Mac app data, disable the Agent integrations and quit AckPulse. A small amount of secure-storage information, such as an installation identifier, may remain on the iPhone after the app is deleted; it stays on that iPhone, is not synced through iCloud and is used only for AckPulse.
- Cloud delivery logs are kept for up to three days. Providers may separately keep connection or platform metadata under their own policies.

See [support](https://ackpulse.cc/support/) for step-by-step help.

## 5. Legal basis and your rights

We process this information to perform our agreement with you by delivering the notifications you request, and, based on our legitimate interests, to keep the service secure and answer support requests. If you email us, we use your address, messages and attachments only to respond and follow up, and keep them only as long as needed or required by law. Do not send passwords or pairing codes.

Depending on where you live, you may ask us to access, correct, delete, restrict or port your personal information, or object to processing based on legitimate interests. Because AckPulse has no accounts and we cannot access your devices, requests mainly concern support emails and delivery logs we can link to you; we will tell you if we hold nothing. Email [hi@ackpulse.cc](mailto:hi@ackpulse.cc) to make a request. If you are not satisfied with our response, you may also complain to your local data protection authority.

## 6. Changes

We will update the date above when this policy changes, and publish material changes to data handling before they apply to a distributed build.
