# Uploading Palladius Bible Study to the App Store

**Signed build ready:** `PalladiusBibleStudy-1.0-b2-AppStore.ipa` (version 1.0, build 2)
Bundle ID: `com.eotc.bible.study` · Team: XH6M6A3MAJ

This build was signed with your **Apple Distribution** certificate and includes:
- All UI fixes (version picker, library headers, safe-area insets)
- The **device-lock bypass** so App Store reviewers can open the app (see note at bottom)

---

## Step 0 — One-time prerequisites (do these first)
1. **App Store Connect app record must exist.** Sign in at
   <https://appstoreconnect.apple.com> → **Apps → (+) → New App**:
   - Platform: iOS · Name: `Palladius Bible Study` · Primary language: English
   - Bundle ID: `com.eotc.bible.study` (must already be registered under your team's
     Identifiers at developer.apple.com; if it isn't, create it there first)
   - SKU: anything unique, e.g. `palladius-bible-study`
   > If this record doesn't exist, Transporter will reject the upload.
2. **Host the legal pages** and note their URLs (needed to submit to the App Store):
   - `appstore-pages/privacy.html`  → Privacy Policy URL (required)
   - `appstore-pages/support.html`  → Support URL (required)
   - `appstore-pages/terms.html`, `appstore-pages/attributions.html` → optional, but
     link them from your support page.
   - Free hosting: create a public GitHub repo, drop the HTML files in, enable
     Settings → Pages. URLs become `https://<user>.github.io/<repo>/privacy.html` etc.

---

## Step 1 — Upload the .ipa with Transporter
1. Install **Transporter** (free) from the Mac App Store if you don't have it.
2. Open Transporter and **sign in** with your Apple ID (the one on team XH6M6A3MAJ).
   - If you have 2FA, use an **app-specific password** from <https://account.apple.com> → Sign-In & Security → App-Specific Passwords.
3. Drag `PalladiusBibleStudy-1.0-b2-AppStore.ipa` into the Transporter window
   (or **Add App → choose the file**).
4. Click **Deliver**. Wait for "Delivered successfully."
5. In App Store Connect the build appears under **TestFlight** / the version's **Build**
   section after ~5–30 min of processing. Export-compliance is already declared in the
   app (`ITSAppUsesNonExemptEncryption = false`), so no encryption prompt.

*(CLI alternative to Transporter, if you prefer:*
`xcrun altool --upload-app -f "PalladiusBibleStudy-1.0-b2-AppStore.ipa" -t ios -u <appleid> -p <app-specific-password>`*)*

---

## Step 2 — Fill in the listing (App Store Connect)
Use the ready text in `APP-STORE-CONNECT-METADATA.md`:
- Name, Subtitle, Promotional text, Description, Keywords, Categories (Reference / Education)
- Support URL + Privacy Policy URL (from Step 0.2)
- **Screenshots** (required): 6.9" iPhone + 13" iPad — draft set in `appstore-screenshots/`
- **App Privacy**: "Data Not Collected"
- **Age Rating**: answer all "None" → 4+
- **Build**: select the uploaded 1.0 (2)
- **App Review Information → Notes**: paste the reviewer notes from
  `APP-STORE-CONNECT-METADATA.md §6a`. You can now say: *"The app opens directly to
  content; no login or activation is required for this build."*

## Step 3 — Submit & Release
- Click **Add for Review → Submit**.
- Apple review typically takes **~1–3 days**. It is NOT instant.
- After approval, the app goes live automatically or when you tap **Release**
  (depending on your release option). Only then is it findable on the App Store.

---

## ⚠️ Note on the device-lock bypass
There is no runtime "reviewer-only" flag available on iOS, so this store build ships
with the activation lock **effectively disabled for everyone** (the grace window was set
to ~1000 years). That is the correct behavior for a public App Store app. To build a
**locked** version for private/side-loaded distribution, rebuild from the web source with
the grace constant back at `0` (in minified terms, `pba_grace_v1",JS=0`). See the memory
note `devicelock-appstore-bypass`.
