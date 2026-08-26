# App Store Connect Metadata — Palladius Bible Study

Bundle ID: `com.eotc.bible.study`  ·  Version `1.0`  ·  Build `2`
Copy each field into App Store Connect. Character limits are noted; every field below is within limit.

---

## 1. App Information (Apps → your app → App Information)

| Field | Value |
|-------|-------|
| **Name** (max 30) | `Palladius Bible Study` |
| **Subtitle** (max 30) | `Ethiopian Orthodox Bible` |
| **Primary Category** | Reference |
| **Secondary Category** | Education |
| **Content Rights** | The app contains third-party content (public-domain / free & open-source Scripture texts, Strongʼs, fonts). When prompted, confirm you have the rights to use it — all bundled texts are public-domain or free/open-source. See `appstore-pages/attributions.html`. |

---

## 2. Pricing & Availability
- **Price:** Free (recommended for private testing).
- **Availability:** You can limit to specific countries. For TestFlight-only private use, App Store availability doesn't matter yet.

---

## 3. Version Information (the "1.0 Prepare for Submission" page)

### Promotional Text (max 170) — editable anytime without review
```
A complete Ethiopian Orthodox Tewahedo Bible in Amharic, Geʽez, Tigrinya, Oromo and English — with commentaries, dictionary, Strongʼs numbers and cross-references.
```

### Description (max 4000)
```
Palladius Bible Study is a comprehensive Bible study companion for the Ethiopian Orthodox Tewahedo Church (EOTC) tradition. It brings the full canon together with the study tools you need to read deeply, compare translations, and understand the text in its original languages.

MULTILINGUAL SCRIPTURE
• Amharic (standard and traditional)
• Geʽez (classical liturgical language)
• Tigrinya
• Afaan Oromo
• English (King James Version)
Read side by side and switch languages instantly.

STUDY TOOLS
• Cross-references that connect related passages across the whole Bible
• Verse-by-verse commentaries
• Bible dictionary for people, places and terms
• Strongʼs numbers for Hebrew and Greek word study
• A reference library of supporting texts
• Apologetics and polemics engine for deeper theological study

BUILT FOR READING
• Beautiful Ethiopic typography (Noto Sans & Serif Ethiopic)
• Fast, fully offline — all content is on your device, no internet required
• Clean, distraction-free reading experience
• Works on iPhone and iPad

Whether you are studying at home, teaching, or following along in the liturgy, Palladius Bible Study keeps Scripture, commentary, and reference tools together in one place.
```

### Keywords (max 100 chars total, comma-separated, no spaces after commas)
```
ethiopian,orthodox,tewahedo,bible,geez,amharic,tigrinya,oromo,kjv,commentary,strongs,eotc
```
(97 characters)

### What's New in This Version (max 4000) — for version 1.0 you can use:
```
Initial release of Palladius Bible Study.
```

### URLs
Ready-to-host pages are provided in `appstore-pages/` (`privacy.html`, `support.html`).
Host them anywhere static (GitHub Pages, Netlify, your own domain) and paste the URLs here.

| Field | Value / Action |
|-------|----------------|
| **Support URL** (required) | URL where you host `appstore-pages/support.html`, e.g. `https://<your-site>/support` |
| **Marketing URL** (optional) | Your homepage, if any. |
| **Privacy Policy URL** (required to submit to App Store) | URL where you host `appstore-pages/privacy.html`, e.g. `https://<your-site>/privacy` |

> **Fastest free hosting (GitHub Pages):** create a public repo, drop `privacy.html` and
> `support.html` in it, enable Pages in Settings → Pages, and your URLs become
> `https://<user>.github.io/<repo>/privacy.html` and `.../support.html`.

---

## 4. App Privacy (Apps → App Privacy) — REQUIRED

This app ships all content on-device and appears to have no accounts, ads, or analytics.
Recommended answer: **"Data Not Collected."**

⚠️ Confirm this yourself: if any embedded SDK, web view endpoint, or the apologetics engine sends anything off-device (analytics, crash reporting, remote content), you must declare it. If it is truly 100% offline with no tracking, "Data Not Collected" is correct.

Privacy Policy (if you must host one) minimal content:
> "Palladius Bible Study does not collect, store, or share any personal data. All Scripture and study content is stored on your device and the app functions entirely offline."

---

## 5. Age Rating (set via the questionnaire)
- Answer all categories "None."
- Religious/theological content (including apologetics) does not by itself raise the rating.
- Expected result: **4+**.

---

## 6. TestFlight Metadata (TestFlight tab) — this is what your private testers see

### Test Information
| Field | Value |
|-------|-------|
| **Beta App Description** | `Study the Bible in the Ethiopian Orthodox Tewahedo tradition across Amharic, Geʽez, Tigrinya, Oromo and English, with commentaries, dictionary, Strongʼs numbers and cross-references.` |
| **Feedback Email** | `palladiustik@gmail.com` |
| **Marketing URL** | (optional) |
| **Privacy Policy URL** | same as above |

### What to Test (shown in each tester's invite)
```
Thanks for testing Palladius Bible Study!

Please try:
• Opening and reading in each language (Amharic, Geʽez, Tigrinya, Oromo, English KJV)
• Switching languages and comparing translations
• Tapping cross-references and following them between passages
• Opening commentaries, the dictionary, and Strongʼs entries
• Searching for a book, chapter, or word
• Using the app fully offline (turn on Airplane Mode)

Report anything that looks wrong, is missing, crashes, or renders incorrectly (especially Ethiopic text). Thank you!
```

### Beta App Review Information (required only for EXTERNAL testers, first build)
| Field | Value |
|-------|-------|
| **Sign-in required?** | No accounts — but see the device-unlock note below. |
| **Contact First/Last Name** | Your name |
| **Contact Email / Phone** | `palladiustik@gmail.com` / your number |
| **Notes** | Use the "Reviewer notes" block below (⚠️ the app has a device-lock gate — reviewers are blocked without a key). |

---

## ⚠️ 6a. CRITICAL — Device-Lock & Reviewer Access

On first launch the app shows an **activation screen**: it displays a device code and
requires an **unlock key** before any content is accessible. Apple's reviewer runs the
app on **their own device**, so they will see a device code you have never seen and will
be **unable to proceed** — this is an automatic rejection (Guideline 2.1) unless you
handle it. Pick ONE approach before submitting:

1. **Reviewer bypass build (recommended):** ship a build that skips the lock when a
   review flag is set, or auto-unlocks in a way only you can trigger. Cleanest for review.
2. **On-demand key:** tell the reviewer in the notes to email/that you will generate a key
   for whatever device code they report — but Apple reviewers generally will NOT wait for a
   back-and-forth, so this often fails.
3. **Remove the gate for the App Store build** and control access another way (e.g.
   TestFlight-only, or server-side).

**Reviewer notes to paste (adapt to the approach you choose):**
```
This app is a fully offline Ethiopian Orthodox Bible study reference. No account or login.

IMPORTANT — the app opens to a device activation screen that requires an unlock key tied
to the device's code. For review, please use the following:
  • Unlock key: <PASTE A KEY VALID FOR THE REVIEW DEVICE, or describe the bypass>
  • Or: this build auto-unlocks for review (no action needed).

After unlocking, you can read Scripture in Amharic, Geʽez, Tigrinya, Afaan Oromo and
English, and use commentaries, dictionary, Strongʼs numbers, cross-references and search.
Everything works offline.
```

> Because the device code changes per device (it is generated on the reviewer's hardware),
> a key you pre-generate will NOT match theirs. Option 1 (a review bypass) is the only
> reliably-approvable path. This is the same reason screenshots require a bypass/seeded key.

---

## 7. How to control WHO can use it (your main goal)
- **Internal Testers** (up to 100): App Store Connect Users with a role. Instant, no review. Best for you + close collaborators.
- **External Testers** (up to 10,000): create a **Group**, then **add testers by email**. First external build gets a quick Beta App Review (usually ~1 day). This is your "invite only the people I choose."
- Testers install the free **TestFlight** app, tap the emailed invite, and get the app. Remove someone anytime to revoke their access.

---

## 8. Screenshots (needed for App Store submission, NOT for TestFlight)
TestFlight does not require screenshots. If you later submit to the App Store, you need at least:
- 6.9" iPhone (1320 × 2868) — required
- 13" iPad (2064 × 2752) — required if you keep iPad support
Capture these from the app running on device/simulator.

---

### Quick reference — what's required for each path
| | TestFlight (private) | App Store (public/unlisted) |
|---|---|---|
| App record + agreement | ✅ | ✅ |
| Description/keywords | Optional | ✅ |
| Screenshots | ❌ | ✅ |
| Privacy answers | Recommended | ✅ |
| Age rating | ❌ | ✅ |
| App Review | External only, light | Full review |
