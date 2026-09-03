# Privacy Policy — Refqa (رِفقة)

**Last updated:** 5 August 2026

---

## The short version

Refqa has no user accounts, no sign-in, and no server of its own. It does not
build a profile of you, does not show ads, and contains no advertising or
analytics trackers.

One thing does leave your device, and you should know about it: **your location**
is sent to the prayer-times service (AlAdhan) to calculate accurate times for
where you are. You are told this, in the app, before it ever asks for the
permission.

Your **voice is only ever sent anywhere if you explicitly say yes.** The
recitation check runs on your device by default; on phones that cannot do that,
the app asks — once, in plain words — whether you want to use Google's speech
service instead, and you can change that answer at any time in Settings.

If the app **crashes**, a technical report of the failure is sent to our error
tracker (Sentry) so it can be fixed. Your location is stripped out of those
reports before they leave the device, and they carry no identifier for you.

Everything else — your bookmarks, streaks, dhikr counts, and settings — stays on
your phone.

---

## Who we are

Refqa is an Islamic companion app offering prayer times, qibla direction, the
Qur'an, Hadith, du'as, dhikr counting, and recitation practice.

**Contact:** <hussein.mohamed.software@gmail.com>

## No accounts, no backend

Refqa has no registration, no login, and no Refqa-operated server. We do not
have a database of users, because there are no users to have. Nothing you do in
the app is associated with an identity, because the app never establishes one.

## Location

**What:** Your device's approximate or precise coordinates (latitude and
longitude), and altitude where your device reports it.

**Why:** To calculate prayer times for your position and to point the qibla
compass toward the Kaaba. Both are meaningless without knowing where you are.

**When:** Only while you are using a feature that needs it — the prayer times
screen or the qibla compass. Refqa does not track your location in the
background, and does not request "always" location access.

**Stored?** No. Your coordinates are used to make the calculation and then
discarded; they are never written to your device's storage. What *is* saved on
your device is the resulting prayer *timetable* — the times themselves — so the
app still works offline. The prayer-times service echoes your coordinates back
in its reply, and Refqa removes them before saving that reply, which an
automated test enforces. A saved timetable does imply a general area, but your
coordinates themselves are not kept.

**Shared?** **Yes — with one service.** Your latitude and longitude are sent to
the AlAdhan prayer-times API (`api.aladhan.com`) with each request, because that
is how the service calculates times for your position. AlAdhan is operated by a
third party under its own privacy policy — see
<https://aladhan.com/privacy-policy>. Your coordinates are not sent to anyone
else.

When your device is offline, or the service is unreachable, Refqa calculates
prayer times **entirely on your device** and your location is not transmitted at
all.

**Your control:** Location permission is optional and requested only when you
first open a feature that needs it. You can decline or revoke it in your device
settings at any time. If you do, prayer times and qibla will not work, but the
rest of the app is unaffected.

## Microphone and speech recognition (تسميع)

**What:** Audio from your microphone, while you are actively recording a
recitation in the Tasmee (recitation-check) feature.

**Why:** To transcribe what you recited so it can be compared against the text
of the verse and marked correct or incorrect.

**When:** Only while you have deliberately started listening by tapping the
microphone button on that screen. The microphone is not accessed anywhere else
in the app, and never in the background.

**Shared?** **Only if you have explicitly allowed it.** By default, no.

Refqa does not perform speech recognition itself; it asks your operating
system's built-in recognizer to do it. Every attempt is made in **on-device
mode** first, which keeps the audio on your phone.

Many phones cannot recognise Arabic on-device — the attempt simply fails. When
that happens, Refqa asks you, in a dialog, whether it may instead send that
recording to **Google's speech service** to transcribe it. The dialog says so in
those words. If you decline, nothing is sent and the feature reports that it is
unavailable on your device. If you allow it, the recording is sent — and only
then — for that attempt and future ones.

**Your control:** the answer is remembered and is fully revocable at
**Settings › Recitation check mode**, which offers three choices:

- **Ask me first** (the default) — try on-device, ask before anything is sent.
- **Allow online checking** — try on-device, fall back to Google without asking
  again.
- **This device only** — never send audio anywhere, accepting that the feature
  will not work on phones without offline Arabic.

Microphone permission is separate, optional, and requested only when you first
use Tasmee. Decline it and every other part of the app works normally.

**Stored?** No. The audio is never recorded to a file and never saved by Refqa,
and only the resulting text is held briefly in memory to grade the verse, then
discarded when you leave the screen. Where you have allowed online checking, what
Google does with the audio it receives is governed by Google's own privacy
policy, not this one.

## Notifications

Refqa sends you the adhan at prayer times, optional salawat reminders, and an
optional streak reminder.

All notifications are **generated locally on your device**. Refqa has no push
notification service: there is no Firebase Cloud Messaging, no push token, and
no server that can send you anything. Your device schedules them from times it
calculated itself, and they work with no internet connection.

Refqa uses exact alarms so the adhan sounds at the true prayer time rather than
being delayed by battery optimisation. This is a scheduling permission; it
collects nothing.

Notification permission is optional and revocable in your device settings.

## Crash reporting

Refqa uses **Sentry** (<https://sentry.io>) to report crashes and errors so they
can be fixed. What is sent is a technical description of the failure: the error,
a stack trace, and device/OS details such as model, OS version, and app version.

Deliberately **not** sent:

- **Your location.** Coordinates are stripped from every report before it
  leaves the device, including from network URLs and error messages that would
  otherwise contain them. This is enforced in code and covered by automated
  tests.
- **Your IP address**, which Sentry is explicitly configured not to collect.
- **Screenshots or screen contents**, which are disabled.
- **Any identifier for you**, since the app has none to send.
- **Your voice or any audio.**

Routine network failures (being offline, a timeout) are not reported at all.

Sentry processes this data on our behalf under its own privacy policy —
<https://sentry.io/privacy/>.

## What is stored on your device

All of this stays on your phone, is never uploaded, and is not visible to us:

- Bookmarks and reading position
- Streaks, daily goals, challenges, and achievement progress
- Dhikr (tasbih) counts
- Settings: language, chosen reciter, font size, adhan and reminder preferences
- Cached content: Qur'an text, hadith, du'as, tafsir, and the prayer timetable,
  so the app works offline

**Deleting it:** Uninstalling Refqa deletes all of it permanently. There is no
copy anywhere else, so there is nothing for you to request from us and nothing
for us to delete on your behalf.

## Third-party services Refqa contacts

Refqa fetches content from these services. As with any internet request, each
necessarily sees your **IP address** and the content you requested. Only AlAdhan
receives your coordinates.

| Service | Purpose | Receives your location? |
|---|---|---|
| AlAdhan (`api.aladhan.com`) | Prayer times, qibla, hijri dates | **Yes** |
| AlQuran.cloud (`api.alquran.cloud`) | Qur'an text and verse audio | No |
| MP3Quran (`mp3quran.net`) | Reciter catalogue and audio | No |
| Qurango (`backup.qurango.net`) | Live radio station audio | No |
| RadioJar (`stream.radiojar.com`) | Live radio station audio | No |
| quran.com (`api.quran.com`) | Tafsir and verse text | No |
| jsDelivr (`cdn.jsdelivr.net`) | Hadith collections | No |
| Sunnah.com (`api.sunnah.com`) | Hadith (when configured) | No |
| Google / Apple speech services | Recitation transcription — **only** after on-device recognition fails *and* you allow it | No (receives the recording, not your location) |
| Sentry (`sentry.io`) | Crash reports, when enabled | No (stripped) |

## Advertising and analytics

Refqa contains **no advertising** and **no analytics or tracking SDKs**. We do
not measure your usage, do not build a profile, and do not sell or share data
with anyone for advertising. There is no data broker relationship of any kind.

## Children

Refqa is suitable for all ages and is not directed at children specifically. It
does not knowingly collect personal information from anyone, of any age, because
it does not collect personal information at all.

## Your rights

Because Refqa holds no personal data on any server, most data-protection rights
(access, correction, deletion, portability) have nothing to act on. Your data is
already, and only, in your hands: it is on your device, and uninstalling the app
erases it.

For data held by the third parties listed above, contact them directly under
their own policies.

## Changes to this policy

If this policy changes materially, the updated version will be published here
with a new "last updated" date, at its permanent home:
<https://husseinmohamed99.github.io/refqa-privacy/>

## Contact

Questions about this policy, or about your data, go to
<hussein.mohamed.software@gmail.com>.
