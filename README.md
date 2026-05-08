# EveryLastMile

**Mileage tracking that respects your time, your battery, and your data.**

EveryLastMile is a privacy-first iOS mileage tracker for self-employed professionals — freelancers, contractors, real-estate agents, gig workers, and anyone else who claims business miles at tax time.

We log drives accurately, classify them as business or personal, and generate IRS-compliant reports. Trip routes never leave your device.

**[Download on the App Store →](https://apps.apple.com/us/app/everylastmile-mileage-tracker/id6754286338)** &nbsp;·&nbsp; **[everylastmile.app](https://everylastmile.app)**

---

## Why we exist

Mileage trackers today usually fail in one of three ways:

- **They miss drives** — short trips get dropped, two trips merged into one, tax report wrong.
- **They drain the battery** — always-on GPS makes the phone hot and the user mad.
- **They trade privacy for convenience** — your full driving history sits on someone else's server.

We don't think you should have to pick. EveryLastMile combines accurate automatic drive detection with an architecture that keeps your trip data on your device.

---

## What you get

- **Manual & automatic drive recording.** Tap "Start Drive," or let the app detect that you've started driving. The auto-detection state machine combines motion and GPS to start within ~15–30 m of where you actually got in the car and to stop cleanly when you park.
- **Business / personal classification.** Swipe to classify, with gentle reminders for unclassified trips.
- **IRS-compliant reports.** Date, start/end addresses, distance, purpose, totals — exportable as PDF, CSV, or JSON.
- **Live Activity & Dynamic Island.** Distance and duration on the lock screen and in the Dynamic Island during a drive — no need to unlock the phone.
- **iCloud sync (optional).** Sync across your devices through your own private iCloud — never our servers.
- **Citrus Greens dark theme.** Designed to be readable at a glance in a parked car at night.

**Free tier:** unlimited manual drives, plus up to 30 auto-detected drives per calendar month.
**Premium:** unlimited auto-detection and full PDF / CSV / JSON exports.

See [features](https://everylastmile.app/features) and [pricing](https://everylastmile.app/pricing).

---

## Our privacy stance — concrete commitments

The full [Privacy Policy](https://everylastmile.app/legal/privacy) has the details. The headlines:

- **No backend servers.** We don't operate any servers that store your trip data. Your routes, addresses, and classifications live on your device, optionally synced to your own iCloud.
- **On-device encryption.** Trip data is stored in an encrypted SQLite database protected by iOS Data Protection (AES-256, tied to your device passcode). Authentication credentials live in the iOS Keychain (hardware-backed encryption).
- **Routing providers see coordinates only.** Apple MapKit handles addresses and routing. Mapbox receives a small number of GPS coordinates *only at the start of a trip*, while the GPS signal is still acquiring accuracy. Neither receives your name, email, classifications, or any trip metadata.
- **Analytics are anonymized and opt-out.** We use PostHog to understand which features get used. Events are tied to a random installation ID, not to you; we discard IP addresses at ingestion and disable PostHog's GeoIP enrichment. PostHog never receives GPS coordinates, street addresses, or trip notes. You can turn analytics off in **Profile → Share analytics**.
- **No selling, no sharing, no ad networks.** We don't sell personal information. We don't share it for cross-context behavioral advertising. There are no advertising SDKs, data brokers, or social-platform pixels in the app.
- **AI stays on your device.** Any machine-learning processing runs locally (including via Apple's Foundation Models framework). We don't pool your trips to train shared models, and we don't use your content to train ours.
- **Your data, your choice.** Export everything as JSON or CSV from inside the app. Delete your account and all associated data with one tap.
- **GPC respected.** We honor Global Privacy Control browser signals on our website.

Read the full text: [privacy](https://everylastmile.app/legal/privacy) · [terms](https://everylastmile.app/legal/terms)

---

## Tech, briefly

| Area | Stack |
|---|---|
| Platform | iOS 26+ |
| UI | SwiftUI (with Combine where it makes sense) |
| Language | Swift 6.2, strict concurrency, `@MainActor` by default |
| On-device storage | Encrypted SQLite (iOS Data Protection) |
| Auth | Apple Sign In via Firebase Authentication |
| Routing | Apple MapKit (primary), Mapbox Map Matching (initial GPS only) |
| Analytics | PostHog (anonymized, opt-out, IP discarded, no GeoIP) |
| Crash reporting | Firebase Crashlytics |
| Sync | Apple CloudKit (optional, your iCloud) |
| CI/CD | Xcode Cloud → TestFlight on tag push |

---

## Status

- ✅ Live on the App Store
- 🔜 Android (post-MVP)

---

## Repositories

- [`ios`](https://github.com/EveryLastMile/ios) — iOS app, Live Activity widget, CI
- [`website`](https://github.com/EveryLastMile/website) — marketing site at [everylastmile.app](https://everylastmile.app)

---

## Get in touch

| | |
|---|---|
| 🌐 Website | [everylastmile.app](https://everylastmile.app) |
| ✉️ Support | support@everylastmile.app |
| 🔒 Privacy | privacy@everylastmile.app |
| ⚖️ Legal | legal@everylastmile.app |

---

<sub>© 2026 EveryLastMile.</sub>
