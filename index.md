# Privacy Policy — Rifqa (رِفقة)

**Last updated:** 16 July 2026

> **DRAFT — for the developer's review, not yet published.**
> This is a good-faith description of what the app actually does, written by
> reading its source. It is **not legal advice.** App-store privacy requirements
> are strict and change often, and a lawyer should review this before it is
> published. Items marked **[TO CONFIRM]** need a decision before publishing.

---

## The short version

Rifqa has no user accounts, no sign-in, and no server of its own. It does not
build a profile of you, does not show ads, and contains no advertising or
analytics trackers.

One thing does leave your device, and you should know about it: **your location**
is sent to the prayer-times service (AlAdhan) to calculate accurate times for
where you are.

Your **voice never leaves your device**. Everything else — your bookmarks,
streaks, dhikr counts, and settings — stays on your phone too.

---

## Who we are

Rifqa is an Islamic companion app offering prayer times, qibla direction, the
Qur'an, Hadith, du'as, dhikr counting, and recitation practice.

**Contact:** **[TO CONFIRM — insert the support email address you want published]**

## No accounts, no backend

Rifqa has no registration, no login, and no Rifqa-operated server. We do not
have a database of users, because there are no users to have. Nothing you do in
the app is associated with an identity, because the app never establishes one.

## Location

**What:** Your device's approximate or precise coordinates (latitude and
longitude), and altitude where your device reports it.

**Why:** To calculate prayer times for your position and to point the qibla
compass toward the Kaaba. Both are meaningless without knowing where you are.

**When:** Only while you are using a feature that needs it — the prayer times
screen or the qibla compass. Rifqa does not track your location in the
background, and does not request "always" location access.

**Stored?** No. Your coordinates are used to make the calculation and then
discarded; they are never written to your device's storage. What *is* saved on
your device is the resulting prayer *timetable* — the times themselves — so the
app still works offline. The prayer-times service echoes your coordinates back
in its reply, and Rifqa removes them before saving that reply, which an
automated test enforces. A saved timetable does imply a general area, but your
coordinates themselves are not kept.

**Shared?** **Yes — with one service.** Your latitude and longitude are sent to
the AlAdhan prayer-times API (`api.aladhan.com`) with each request, because that
is how the service calculates times for your position. AlAdhan is operated by a
third party under its own privacy policy — see
<https://aladhan.com/privacy-policy>. Your coordinates are not sent to anyone
else.

When your device is offline, or the service is unreachable, Rifqa calculates
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

**Shared?** **No. Your voice never leaves your device.**

Rifqa does not perform speech recognition itself; it asks your operating
system's built-in recognizer to do it. That recognizer is capable of sending
audio to Google's or Apple's servers, and Rifqa deliberately does not allow it
to. Recognition is requested in **on-device-only mode**, and — because that
request alone is not reliably honoured on every Android version — the app also
checks first whether your device can genuinely recognise Arabic locally.

**If it cannot, the recitation-check feature is switched off on that device and
tells you so.** It does not quietly fall back to sending your voice away. This
means Tasmee is unavailable on some older devices; that is a deliberate choice
in your favour.

**Stored?** No. The audio is never recorded to a file and never saved, by us or
in transit anywhere. Only the resulting text is held briefly in memory to grade
the verse, and it is discarded when you leave the screen.

**Your control:** Microphone permission is optional and requested only when you
first use Tasmee. Decline it and every other part of the app works normally.

## Notifications

Rifqa sends you the adhan at prayer times, optional salawat reminders, and an
optional streak reminder.

All notifications are **generated locally on your device**. Rifqa has no push
notification service: there is no Firebase Cloud Messaging, no push token, and
no server that can send you anything. Your device schedules them from times it
calculated itself, and they work with no internet connection.

Rifqa uses exact alarms so the adhan sounds at the true prayer time rather than
being delayed by battery optimisation. This is a scheduling permission; it
collects nothing.

Notification permission is optional and revocable in your device settings.

## Crash reporting

**[TO CONFIRM — this section describes the app as built. It is only accurate if
you ship with a Sentry DSN configured. If you ship without one, no crash
reporting occurs at all and this section should say so instead.]**

When enabled, Rifqa uses **Sentry** (<https://sentry.io>) to report crashes and
errors so they can be fixed. What is sent is a technical description of the
failure: the error, a stack trace, and device/OS details such as model, OS
version, and app version.

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

**Deleting it:** Uninstalling Rifqa deletes all of it permanently. There is no
copy anywhere else, so there is nothing for you to request from us and nothing
for us to delete on your behalf.

## Third-party services Rifqa contacts

Rifqa fetches content from these services. As with any internet request, each
necessarily sees your **IP address** and the content you requested. Only AlAdhan
receives your coordinates.

| Service | Purpose | Receives your location? |
|---|---|---|
| AlAdhan (`api.aladhan.com`) | Prayer times, qibla, hijri dates | **Yes** |
| AlQuran.cloud (`api.alquran.cloud`) | Qur'an text and verse audio | No |
| MP3Quran (`mp3quran.net`) | Reciter catalogue and audio | No |
| quran.com (`api.quran.com`) | Tafsir and verse text | No |
| jsDelivr (`cdn.jsdelivr.net`) | Hadith collections | No |
| Sunnah.com (`api.sunnah.com`) | Hadith (when configured) | No |
| Google / Apple speech services | Not contacted — recognition is on-device only | No (receives nothing) |
| Sentry (`sentry.io`) | Crash reports, when enabled | No (stripped) |

## Advertising and analytics

Rifqa contains **no advertising** and **no analytics or tracking SDKs**. We do
not measure your usage, do not build a profile, and do not sell or share data
with anyone for advertising. There is no data broker relationship of any kind.

## Children

Rifqa is suitable for all ages and is not directed at children specifically. It
does not knowingly collect personal information from anyone, of any age, because
it does not collect personal information at all.

## Your rights

Because Rifqa holds no personal data on any server, most data-protection rights
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

**[TO CONFIRM — insert the support email address you want published.]**
