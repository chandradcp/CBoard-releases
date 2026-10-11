# CalBoard Privacy Policy

_Last updated: 11 October 2026_

CalBoard is a keyboard and input utility for Android. This policy explains how it accesses,
uses, stores and transmits information, including through optional features and third-party
components. CalBoard does not require a CalBoard online account. For privacy questions,
contact **chandradcp@gmail.com**.

The updated controls described below apply to **version 1.0.51 and subsequent releases that
retain them**. This does not mean that version 1.0.51 is already available to every user.
Earlier versions differ as explained under “Earlier versions.” Check your version in About
and use the latest version available to you.

## Overview

- Ordinary typing, prediction and Smart Reply message processing take place on your device.
  CalBoard does not upload ordinary typing or Smart Reply message context to the developer.
- Saved passwords and card numbers are encrypted in CalBoard's private database. Other saved
  fields are not individually encrypted by CalBoard. Selecting a fill, paste or reply delivers
  that content to the app and field you choose.
- Voice typing uses your device's speech service. Translation sends the text you submit to
  MyMemory. Versions containing Google ML Kit send operational data to Google, including when
  Smart Reply is off.
- Google Play handles supported purchase and entitlement requests. Android may back up eligible
  app data as explained below. These are separate from local keyboard processing.

## Keyboard data and local processing

**Typing and predictions.** Prediction and autocorrect run on the device. Learned words and
word pairs can be saved in CalBoard's local database to improve suggestions. Clear learned
words in Settings → Dictionary. Words suppressed from suggestions are stored separately and
can be included in Android backup.

**Contacts, if permitted.** CalBoard reads contact names to suggest and spell them correctly.
It processes the contact list on the device rather than uploading it. You can deny or revoke
the Contacts permission in Android settings.

**Clipboard.** Recent text clips can be held in the keyboard service's memory for reuse in the
clipboard panel. The history is not a persistent database of your clips. You can delete clips,
clear history or enable automatic clearing through the clipboard controls. The Android system
clipboard and content pasted into another app are controlled separately.

**Settings.** CalBoard stores preferences such as themes, layout and feature switches on the
device. The backup section explains which other preferences and records Android can copy.

### Smart Reply and Notification Access

In versions offering Smart Reply, it is off by default. It reads message context and requests
suggestions only after you tap its toolbar button. Its two sources have separate controls:

- Clipboard context reads the current plain-text clipboard item. It does not open clipboard
  files or links, or add the item to CalBoard's clipboard history.
- Notification context requires Android Notification Access and a separate Smart Reply switch.
  CalBoard first filters active notifications to the app owning the current text field. You
  must confirm the notification conversation before it generates a reply.

English replies use Google's on-device ML Kit Smart Reply model; Indonesian replies use a
local rule-based model. Message context and replies are not uploaded, logged or backed up.
They are discarded when you leave Smart Reply, change fields or close the keyboard. Smart
Reply is disabled in sensitive fields. Selecting a reply inserts editable text; it does not
send the message. SDK initialization and metrics are separate, as explained below.

Notification Access can also support OTP detection. Revoking it in Android settings stops both
notification-based OTP detection and Smart Reply notification context. Clipboard-based Smart
Reply does not require it. In version 1.0.51, these controls are in Settings → Experimental →
Smart Reply.

### Pointer Mode and Accessibility: updated controls

In version 1.0.51, Pointer Mode is an Experimental feature that is off by default. Android
Accessibility carries out the taps, long presses and drags you request. On Android 13 and
newer, Pointer + Scroll also uses temporary screen structure to choose a supported scroll
target. It requires its own in-app disclosure, agreement and Android service permission.
An earlier gesture-only agreement does not authorize the new screen access. You activate
the pointer separately after permission.

For scrolling, CalBoard examines window and element bounds, window identity/type/focus, child
relationships, visibility, enabled/editable state, available scroll actions and password or
sensitivity flags. Android may supply objects containing content, but this Pointer path does
not read element text or descriptions, capture screenshots, log or store the structure, or send
it off the device. Element references are released after each scroll attempt; the framework's
node cache is disabled before retrieval. Sensitive, ambiguous or unsupported targets are blocked.

On Android 7–12, the legacy service provides gesture-only Pointer actions and does not request
screen-content retrieval or offer this scroll wheel. Turn Pointer Mode off in Settings →
Experimental → Pointer Mode, or revoke the service permission in Android Accessibility settings.

## Saved logins, cards, profiles and one-time codes

CalBoard can store information you choose to use for autofill in its private local database:

- Saved logins contain a site or app association, username and encrypted password. The username
  and site are not individually encrypted.
- Saved cards contain an encrypted card number, cardholder name, expiry date and optional label.
  The last four digits are unencrypted for identification. There is no stored CVV/CVC field.
- Optional profiles can contain your name, email, phone number and postal address.

Passwords and card numbers use AES-GCM encryption with a key in Android Keystore. CalBoard does
not provide cloud synchronization for this database. The updated version's backup exclusions
are explained below. When you choose to fill information, the destination app receives it and
handles it under its own policies.

### Saved-password authentication: updated controls

In version 1.0.51, when the Autofill lock is enabled, keyboard password fills require fingerprint,
face or device screen-lock authentication, unless a successful unlock is still within its
60-second grace period. If usable authentication is unavailable, filling is blocked. Turning
the Autofill lock off removes that authentication requirement.

On Android 12 and newer, supported native-app password suggestions require fresh authentication
when the lock is enabled. Android then fills the original field directly without copying the
password to the clipboard. You must associate the login with that app; CalBoard stores its
package name and signing-certificate fingerprint locally and checks them before filling.
Missing or mismatched identity, cancelled or expired authentication, and unsupported targets
including browsers and WebViews block this locked system-fill path. These safeguards must not
be assumed for earlier versions.

### OTP and imported files

CalBoard can detect OTPs from the clipboard, permitted notifications, or a single SMS delivered
through Android's SMS User Consent prompt. It does not request permission to read your SMS
inbox. You approve each SMS message provided through that prompt. OTP suggestions are held
temporarily in memory rather than written to permanent storage.

For login imports, Android's file picker gives CalBoard the CSV file you select. CalBoard reads
it and saves imported entries in its local database. It does not retain another copy of the CSV
or log its contents. Your original export remains wherever you saved it and can contain plaintext
passwords; delete that file separately when you no longer need it.

## Services that receive information

### Voice typing

When you tap the microphone, CalBoard uses Android's speech-recognition service. The selected
provider processes the audio, on the device or remotely depending on that service and its
settings. CalBoard does not store the audio. The provider's controls and policy govern its
processing. An offline preference is only a request to the provider, not a guarantee of local
processing. Disable voice typing in Settings → Voice Typing or revoke the microphone permission.

### Translation

When you request a translation, text in the translation panel and the selected language pair
are sent over HTTPS to MyMemory at `api.mymemory.translated.net`. Ordinary typing into other
apps is not sent through this feature. MyMemory processes the request under its own
[privacy policy](https://mymemory.translated.net/doc/privacy.php). CalBoard has no control for
deleting requests already received by MyMemory. Earlier versions' local diagnostic logging
is described below.

### Google ML Kit operational data

Versions 1.0.49 and 1.0.51 include Google's on-device Smart Reply and language-identification
components. Google states that their input text and output replies remain on the device,
while performance and usage metrics go to Google to operate, diagnose and improve the APIs
and detect misuse. See [ML Kit Terms & Privacy](https://developers.google.com/ml-kit/terms).

Google's [Android SDK disclosure](https://developers.google.com/ml-kit/android-data-disclosure)
describes device and app information, installation identifiers, latency, configuration and
versions, input/output sizes, events, errors and identified languages. Google documents HTTPS
protection and no onward sharing of the listed SDK data with third parties. These metrics are
separate from message text.

CalBoard initializes the ML Kit client when its keyboard service starts, including when Smart
Reply is off. Smart Reply switches control requests and context sources; they do not provide
an opt-out from ML Kit initialization or its operational metrics.

### Google Play purchases

Versions with the Billing integration connect to Google Play to retrieve products, check and
restore purchases, acknowledge purchases and determine feature access. CalBoard processes
returned product identifiers, purchase state and purchase tokens for these purposes, and
stores entitlement information locally.

Google Play handles its payment interface and payment details entered there. CalBoard does
not receive those payment-card details. This is separate from cards saved locally for autofill.
See Google's [Privacy Policy](https://policies.google.com/privacy) and
[Payments Privacy Notice](https://payments.google.com/payments/apis-secure/get_legal_document?ldo=0&ldt=privacynotice).

### Android backup and device transfer

In version 1.0.51, if your device settings allow it, Android can copy eligible app and SDK
preferences, words suppressed from suggestions, and CalBoard's entitlement record to your
configured backup provider or another device. The backup service controls those copies;
they are not stored in a CalBoard cloud account.

This version excludes CalBoard's database, including learned words and word pairs, logins,
cards and profiles, from its backup and transfer rules. Pointer disclosure consent is also
excluded and must be obtained again after restoration. Clipboard history and Smart Reply
context are temporary and are not included in these backups.

Inspect or manage backups using the system controls. See
[Android backup guidance](https://support.google.com/android/answer/2819582?hl=en) or your
device manufacturer's instructions.

### Support messages

Bug-report and feature-request buttons open an editable email draft addressed to
**chandradcp26@gmail.com**. It includes the app version, Android version/API level, device
manufacturer/model and app package name. CalBoard does not send it automatically.
If you send it, your email provider delivers the message, sender address and any content or
attachments you include to the support mailbox. Inspect and edit the draft before sending.
Removing CalBoard's local data does not remove an email you sent.

The developer manages both support addresses listed in this policy. We use support email to
handle your request and delete our copies no later than 90 days after the case is closed, or
in response to a verifiable deletion request, unless retention is required by law. This
commitment applies to support messages under our control, not to separate Google, MyMemory,
speech-service or mail-provider records.

## Earlier versions

Feature availability and protections depend on the version you installed:

- Version 1.0.37 does not include Smart Reply or the purchase-entitlement integration described
  above. Purchases made through the Play Store are still handled by Google Play.
- Versions 1.0.37 and 1.0.49 can write short excerpts of translation input and output, and
  diagnostic errors, to Android's local logs. The updated translation implementation omits
  those text excerpts. This is separate from MyMemory's processing of submitted translations.
- In versions 1.0.37 and 1.0.49, dictionary learning does not have the newer checks for sensitive fields
  and an app's request not to learn. Learned words may therefore include text from those fields.
  Clear learned words in Settings → Dictionary if needed.
- Earlier system Autofill suggestions can supply a saved password directly without the fresh
  authentication required by the updated native-app flow. The updated authentication and
  Pointer disclosure controls above describe version 1.0.51.
- Version 1.0.37 allows Android to back up or transfer SharedPreferences; version 1.0.49 also
  includes the entitlement record. Both omit the database. The updated version additionally
  excludes Pointer disclosure consent; older backups must not be assumed to have that exclusion.

## Retention and deletion

Local logins, cards, profiles and learned dictionary entries remain until you remove them,
clear CalBoard's storage or uninstall the app. Delete selected entries in Settings → Autofill
& OTP and clear learned words in Settings → Dictionary. Clipboard history can be cleared
through its controls and ends when its service memory is discarded. Smart Reply context
ends with its session; OTP suggestions are temporary.

To remove local app data, use Android Settings → Apps → CalBoard → Storage & cache → Clear
storage, or uninstall CalBoard. Menu names vary by device. Imported CSV files, Android system
logs and content already pasted or filled into other apps must be managed separately.

These actions do not themselves delete Android backups, Google Play purchase records, support
emails or information already processed by Google, MyMemory or your speech provider. Use the
backup provider's controls for backups and the relevant provider's controls for its records.
Google's [retention policy](https://policies.google.com/technologies/retention) describes retention
according to data and purpose, including longer retention for financial records, security and
legal obligations. CalBoard does not provide per-installation deletion of ML Kit metrics or
set these external services' retention periods.

For help with local deletion or a privacy request about information you sent to the developer,
contact **chandradcp@gmail.com**. See also our [Data Deletion page](https://chandradcp.github.io/CBoard-releases/data-deletion.html).

## Advertising, children and policy changes

CalBoard does not sell your data or use advertising SDKs. The external processing described
above includes operational usage analytics.

CalBoard is a general-purpose utility and is not directed at children. Policy changes will be
posted on this page with an updated date.
