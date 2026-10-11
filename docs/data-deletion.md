---
title: CalBoard Data Deletion
---

# CalBoard Data Deletion

_Last updated: 11 October 2026_

CalBoard does not require a CalBoard online account. It stores keyboard and autofill data on
your Android device, while the services described in our [Privacy Policy](https://chandradcp.github.io/CBoard-releases/privacy-policy.html)
can process information separately. Deleting local app data does not delete all provider-held
records. Feature and menu availability depend on your installed version.

## Delete selected local data

- Delete saved logins, payment cards and profiles in **Settings → Autofill & OTP**.
- Clear learned dictionary entries in **Settings → Dictionary**. Versions 1.0.37 and 1.0.49 can learn text
  from sensitive fields; clearing the dictionary removes those learned entries too.
- Delete individual clipboard items or clear history through the clipboard controls.
  CalBoard's clipboard history is held in the keyboard service's memory.
- Leave Smart Reply to discard its current context and replies. In version 1.0.51, its switches
  are in **Settings → Experimental → Smart Reply**. Version 1.0.37 does not have this feature.
- Revoke Notification Access in Android settings to stop notification-based OTP and Smart Reply
  access. This does not delete notifications from the originating app.

## Delete all local CalBoard app data

Use either of these Android controls:

1. **Settings → Apps → CalBoard → Storage & cache → Clear storage**, or
2. Uninstall CalBoard.

Menu names vary by device. This removes CalBoard's local app data from that device, including
saved logins, cards, profiles, learned words, suppressed suggestion words and preferences.
It does not delete an original CSV file selected for import, the Android system clipboard,
system diagnostic logs, or content already filled or pasted into another app. Manage those
copies separately.

Versions 1.0.37 and 1.0.49 can write short translation input/output excerpts and diagnostic
errors to Android's local logs. Those logs are managed by Android and are not CalBoard's
database. Updating does not itself erase earlier system logs.

## Android backups and device transfers

Version 1.0.51 allows Android to back up eligible app and SDK preferences, suppressed suggestion
words and the entitlement record when your device settings allow it. Clear storage or
uninstalling is not a request to delete those backups, and restoration can bring eligible
data back.

This version excludes its database of learned words, logins, cards and profiles from backup
and transfer. It also excludes Pointer disclosure consent, which must be obtained again after
restoration. These are the updated version's rules; do not assume they describe every older
backup.

Inspect or manage backups using your device's backup-provider controls. Consult
[Android backup guidance](https://support.google.com/android/answer/2819582?hl=en) or your
device manufacturer's instructions. Backup deletion can affect data beyond CalBoard; review
the scope shown by the provider before confirming it.

## Information processed by other services

Removing CalBoard does not itself delete Google Play purchase records, ML Kit operational
metrics, MyMemory translation requests, speech-service records or support emails you sent.
Retention and deletion depend on the relevant service and its policies.

- **Google:** see its [Privacy Policy](https://policies.google.com/privacy) and
  [retention policy](https://policies.google.com/technologies/retention). Payment records may
  be retained for financial or legal purposes. CalBoard has no per-installation control for
  deleting ML Kit operational metrics.
- **MyMemory:** see its [privacy policy](https://mymemory.translated.net/doc/privacy.php).
  CalBoard has no control for deleting requests already received by this service.
- **Speech recognition:** use the controls and support offered by the speech provider selected
  on your device.
- **Email:** sent messages are held separately by the mail providers and recipient. Clearing
  CalBoard does not remove them.

## Privacy and deletion inquiries

For help with local deletion or a privacy request about information you sent to the developer,
contact **chandradcp@gmail.com**. If your request concerns an in-app feedback email, mention
that it was sent to **chandradcp26@gmail.com** and provide enough information to identify the
message. Do not send passwords, card numbers or OTPs.

The developer manages both mailboxes and uses support email to handle your request. We delete
our copies no later than 90 days after the case is closed, or in response to a verifiable
deletion request, unless retention is required by law. We may ask for limited information
needed to verify that a request concerns your own messages. This commitment covers support
messages under our control, not independent Google, MyMemory, speech-service or mail-provider
records. We cannot delete those providers' records on your behalf.
