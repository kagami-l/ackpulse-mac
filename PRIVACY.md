# AckPulse Privacy Policy

[简体中文](PRIVACY.zh-CN.md)

> This is a copy of the privacy policy published at [ackpulse.cc/privacy](https://ackpulse.cc/privacy/). If the two differ, the website version applies.

**Last updated: November 13, 2026**

This policy covers the AckPulse apps for Mac, iPhone and Apple Watch. “We” means the developer of AckPulse, the seller shown for AckPulse on the App Store. Contact: [hi@ackpulse.cc](mailto:hi@ackpulse.cc).

AckPulse is built to keep your work on your own devices:

- There is no AckPulse account, and we keep no cloud user profile.
- Event details, commands, approvals and the messages you send to sessions are stored on your devices and travel directly between your iPhone and Mac over your local network.
- Cloud notifications carry only technical identifiers, never your commands, paths, prompts, messages or decisions. Delivery logs are deleted within three days.
- We do not sell data or use it for advertising, analytics or tracking.

## 1. On your devices and local network

AckPulse stores project paths, commands and event details (including Agent replies), approval decisions, the messages you send to sessions, pairing information, device identifiers, settings and diagnostics on your devices.

When **Active sessions and messages** is turned on in the Mac's **Integrations** page, your Mac reads session titles, short prompt summaries, project paths and status from your Agents to show active sessions and to tell which sessions can take a message. This list is kept only in memory and shared only with paired devices. When your Mac saves a record, such as an approval or a reply, it also stores the session's title at that moment, which may be a prompt summary, with the record.

After an Agent replies, you can send one message to that session from your iPhone or Apple Watch. The message goes over your local network to your Mac, which passes it to the Agent session on that Mac; messages from Apple Watch go through your iPhone. Messages never appear in push or system notifications. Dictation on Apple Watch is handled by watchOS; AckPulse receives only the text and does not request microphone permission. Once a message reaches the session, the Agent handles it like anything you type in the terminal, under its own rules and privacy policy.

Your iPhone retrieves details from your Mac and sends it approval decisions and messages over the local network; this traffic does not pass through our servers. The local connection uses unencrypted HTTP, so pair and use AckPulse only on a trusted network.

## 2. Notifications and service providers

To alert you while you are away, your Mac sends a minimal request over HTTPS to our notification relay, hosted by a cloud infrastructure provider, which passes a generic alert to Apple Push Notification service (APNs). The request contains only the Apple push token, limited device and event identifiers, the alert type and a pairing identifier. It never includes commands, session titles, prompt summaries, Agent replies, your messages, project or file paths, file contents, approval details or decisions.

The relay can see your Mac's IP address and the approximate location derived from it, and keeps limited delivery logs for operation, security and troubleshooting. We do not request device location permission.

We use a cloud infrastructure provider, [Apple](https://www.apple.com/legal/privacy/) and an email provider, and only choose providers that protect the information they receive to a standard equivalent to this policy. They may process information outside your country or region.

## 3. Permissions and diagnostics

- **Local Network:** connects to your Mac, retrieves details, and sends decisions and messages.
- **Notifications:** shows alerts on iPhone and Apple Watch; the system decides where they appear.
- **Camera (optional):** scans the pairing QR code on your iPhone. Images are not saved or uploaded, and manual pairing is available.

You can revoke permissions in iPhone Settings; features that depend on them will stop working. Diagnostics stay on your devices and are never uploaded automatically. They leave your device only if you copy and share them; review them and remove credentials first. You can clear iPhone logs with **Clear logs** in diagnostics.

## 4. Retention and deletion

- Event records, including the messages you send and the session titles saved with records, are kept on your devices for seven days. For approval requests, this period starts when the request ends; pending approvals are not removed by age. iPhone record caches use file protection and are excluded from cloud backup.
- Messages to Codex first go into Codex's own queue on your Mac. If the session does not pick one up, AckPulse withdraws it; if that fails, the message may stay in that queue.
- Removing pairing on iPhone asks a reachable Mac to revoke its access and push registration, and clears the iPhone record cache. You can also remove an iPhone under **Devices** on Mac. Mac history is kept separately. **Forget Previous Mac and Continue** clears only the iPhone side; remove that iPhone on the old Mac when it is available, or generic alerts may continue.
- Pairing, settings and Mac history remain until you remove them or delete the app data. Before deleting Mac app data, disable the Agent integrations and quit AckPulse. A small amount of secure-storage information, such as an installation identifier, may remain on the iPhone after the app is deleted; it stays on that iPhone, is not synced through iCloud and is used only for AckPulse.
- Cloud delivery logs are kept for up to three days. Providers may separately keep connection or platform metadata under their own policies.

See [support](https://ackpulse.cc/support/) for step-by-step help.

## 5. Legal basis and your rights

We process this information to perform our agreement with you by delivering the notifications you request, and, based on our legitimate interests, to keep the service secure and answer support requests. If you email us, we use your address, messages and attachments only to respond and follow up, and keep them only as long as needed or required by law. Do not send passwords or pairing codes.

Depending on where you live, you may ask us to access, correct, delete, restrict or port your personal information, or object to processing based on legitimate interests. Because AckPulse has no accounts and we cannot access your devices, requests mainly concern support emails and delivery logs we can link to you; we will tell you if we hold nothing. Email [hi@ackpulse.cc](mailto:hi@ackpulse.cc) to make a request. If you are not satisfied with our response, you may also complain to your local data protection authority.

## 6. Changes

We will update the date above when this policy changes, and publish material changes to data handling before they apply to a distributed build.
