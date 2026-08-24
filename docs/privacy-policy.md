# CalBoard Privacy Policy

_Last updated: 20 August 2026_

CalBoard is a keyboard (input method) for Android. This policy explains what the app does
with your information. **This is a technical description of how the app behaves; the app
owner is responsible for reviewing and publishing the final policy.**

## The short version

- What you type is used to draw the keyboard and to offer predictions **on your device**. It is not collected by CalBoard or sent to us.
- CalBoard contains **no advertising and no analytics or tracking SDKs**. We do not build a profile of you.
- Your saved passwords, payment cards, personal details and one-time codes **never leave your device**. They are encrypted on the device and are not backed up to us or to anyone else.
- Smart Reply processes message context **on your device**, only after you tap its toolbar button. It never sends a reply automatically.
- Two features send information off your device, and only when you choose to use them: **voice typing** (handled by your device's own speech service) and **translation** (sent to a third‑party translation service). Both are described below. Smart Reply does not send its context to either service.

## What stays on your device

- **Your typing.** Text prediction and autocorrect run locally, using on‑device dictionaries. Words you type may be saved to a personal dictionary **on your device** to improve future suggestions. You can clear it in Settings → Dictionary.
- **Contacts (optional).** If you grant the Contacts permission, CalBoard reads your contact **names** so it can suggest and correctly spell them. This happens on your device; contact data is not uploaded. If you deny or revoke the permission, the feature turns off.
- **Clipboard history.** If you use the clipboard panel, recent clips are kept on your device so you can paste them again. You can delete individual clips, clear the history, or turn on automatic clearing in Settings → Clipboard.
- **Smart Reply context (optional).** After you tap Smart Reply, CalBoard can read the current plain-text clipboard item and, if you separately enable notification context, active message notifications from the app whose text field currently owns the keyboard. Context and generated replies are processed on-device, kept only for the current Smart Reply session, and are not written to history, logs, backups, or a server. CalBoard does not read context in password, payment-card, OTP, or other sensitive fields. English and Indonesian are supported.
- **Settings.** Your preferences (theme, layout, toggles) are stored locally on your device.

### Smart Reply

Smart Reply is off by default. It runs only when you tap its dedicated keyboard toolbar button.
It can use two independently controlled sources:

- **Clipboard context** reads only the current plain-text clipboard item at that moment. It does not open clipboard URIs or intents, and it does not add the item to CalBoard's clipboard history.
- **Notification context** requires Android Notification Access and a separate Smart Reply toggle. Before extracting message text, CalBoard filters active notifications to the exact package name of the app that owns the current text field. Because Android does not tell a keyboard which conversation is open, you must confirm the notification conversation before a reply is generated.

Up to three replies are generated locally with Google's on-device ML Kit Smart Reply model for
English or a local rule-based model for Indonesian. CalBoard does not upload the context or the
generated replies. Selecting a suggestion only inserts editable text into the current field; it
does not press Send. Context is discarded when you leave Smart Reply, change fields, or close the
keyboard.

## Passwords, cards and one-time codes

CalBoard can act as an autofill provider so you can fill logins and payment details from the
keyboard. Everything in this section is stored **only on your device**, in the app's private
storage. None of it is transmitted to us or to any third party, and there is no cloud sync,
account, or backup feature for it.

### What is stored

- **Saved logins** — the site or app the login belongs to, the username, and the password. The password is encrypted; the username and site are not.
- **Payment cards** — the card number (encrypted), the cardholder name, and the expiry month and year. You may also give a card your own label. **The security code (CVV/CVC) is never stored** — there is no field for it in the app's database at all. The last four digits are kept unencrypted so the picker can tell two cards apart without decrypting them.
- **Personal details (optional)** — name, email, phone number and postal address, if you choose to save them for filling forms.

### How it is protected

- Passwords and card numbers are encrypted with **AES‑GCM**, using a key held in the **Android Keystore**. The key does not leave the device and is not included in any backup of the app.
- Before a saved password is filled, CalBoard asks you to confirm with your **fingerprint, face, or device screen lock**. If your device has no screen lock set up, this step is skipped — otherwise you would be locked out of your own data.
- A saved login is tied to the site or app it was saved on. A login saved on one website is not offered on a different one.

### One-time codes (OTP)

CalBoard can offer a verification code so you do not have to switch apps to read it. It can
find codes in three places, all on your device:

- **SMS** — through Android's **SMS User Consent** system. CalBoard does not have permission to read your messages. Android shows you a prompt and passes CalBoard a single message only if you agree to it, one message at a time.
- **Notifications** — only if you explicitly grant CalBoard notification access in your device's system settings. This access can support OTP detection and, only when its separate toggle is enabled, Smart Reply notification context as described above. Notification contents are not transmitted or permanently stored. You can revoke access at any time in Android Settings → Notifications → Device & app notifications.
- **Clipboard** — if a code is copied to the clipboard.

Codes are held briefly in memory so they can be offered to you, and are not written to
permanent storage.

### Importing saved logins

You can import logins from a password manager export file (the CSV format produced by Google
Password Manager). When you do:

- The file is read through Android's file picker, which you control. CalBoard is given access to the one file you select and nothing else.
- The file is **read once and never copied** into the app's storage.
- Its contents are **never written to logs**, including when an error occurs. Error messages refer to line numbers only.

Your export file remains wherever you saved it and contains every password in plain text.
CalBoard cannot delete it for you — you should delete it yourself after importing.

**There is no export feature.** Writing your passwords back out to a plain file would defeat
the point of storing them encrypted.

## Information that leaves your device

CalBoard only sends data off your device for the two features below, and only when you actively
use them. Nothing described in the section above is ever included.

### Voice typing (microphone)

When you tap the microphone, CalBoard uses **Android's built‑in speech recognition service** to
convert speech to text. The audio is processed by that system service (on many devices this is
provided by Google), not by CalBoard, and CalBoard does not store your audio. Whether recognition
happens on‑device or in the cloud is determined by your device's speech service and its own
privacy policy. If you never use voice typing, the microphone is never used.

### Translation

The translation feature has its own separate input box. Text you type **into that box** is sent
over the internet to **MyMemory** (`api.mymemory.translated.net`), a third‑party translation
service, to return a translation. This only happens for text you enter in the translation panel
and only when you request a translation — your normal typing into other apps is never sent there.
MyMemory processes that text under its own privacy policy
(<https://mymemory.translated.net/doc/privacy.php>).

## Children

CalBoard is a general‑purpose utility and is not directed at children.

## Data sharing and selling

CalBoard does not sell your data and does not share it with third parties for advertising. The
only third parties that receive any data are the device speech service (for voice typing) and the
translation service (for translation), as described above, and only to provide those features.
Your saved logins, payment cards, personal details, one-time codes, Smart Reply context, and
generated replies are never shared with anyone.

## Your controls

- Turn voice typing on or off in Settings → Voice Typing.
- Turn the Contacts feature on or off by granting or revoking the Contacts permission.
- Clear your personal dictionary in Settings → Dictionary.
- Delete individual clips, or clear your clipboard history, in Settings → Clipboard.
- Turn Smart Reply, clipboard context, or notification context on or off independently in Settings → Smart Reply.
- Open Android's Notification Access settings from Settings → Smart Reply to grant, inspect, or revoke access. Revoking it disables both notification-based Smart Reply context and OTP detection from notifications; clipboard Smart Reply does not require it.
- View and delete individual saved logins, payment cards, and your personal details in Settings → Autofill & OTP.
- Turn the fingerprint/screen lock requirement on or off in Settings → Autofill & OTP.
- Uninstalling CalBoard removes all of its locally stored data from your device, including all saved logins and cards.

## Contact

Questions about this policy: chandradcp@gmail.com
