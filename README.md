# Tiny Champ — Android game starter project

Tiny Champ is a touch-friendly, offline-first learning game for children ages 3–8. It includes six themed worlds and 100 short levels, local progress, stars, generated sound effects, speech prompts where supported, and a parent area.

## Important status

This is a playable first version of the game and a cloud build starter. It is **not yet a store-approved or signed release**. Test it with a parent/guardian before sharing. The age selector is currently a parent preference only; the question difficulty is not yet deeply adaptive. The visual style uses colourful 2D interface elements and emoji/character art to create a 3D-inspired feel; it does not contain a full 3D engine or custom animated 3D models.

## Build from an Android tablet (no Android Studio)

1. A parent/guardian should help create or use a GitHub account.
2. Create a new private GitHub repository named `tiny-champ`.
3. On the tablet, open the repository and choose **Add file → Upload files**.
4. Upload the contents of this ZIP (not the ZIP itself), keeping the folders such as `www` and `.github` intact. Commit to `main`.
5. Open the repository's **Actions** tab. Select **Tiny Champ Android build**, then **Run workflow** if it has not started automatically.
6. Wait for the workflow to finish. Open the completed run and download the `tiny-champ-debug-apk` artifact.
7. For testing, a parent/guardian can transfer the APK to an Android device and install it after reviewing Android's installation warning.

The workflow also creates an **unsigned AAB** for inspection. Google Play requires a properly signed AAB for publishing. Do not upload the unsigned AAB.

## Google Play release signing

Before public release, a parent/guardian should create and securely store a release signing key. Never put a keystore or passwords in this repository.

A safe next step is to configure GitHub Actions secrets and a release signing step, then rebuild a signed AAB. Keep a secure backup of the keystore and credentials. Losing the key can prevent updates to the app.

## Child safety and publishing checklist

- Have a parent/guardian own the Play Console developer account and handle publishing.
- Review the current Google Play Families Policy, target audience declarations, Data safety form, content rating, app access and privacy policy requirements.
- This starter has no ads, chat, login, analytics SDK or in-app purchases. Re-check dependencies and the final app behavior before declaring anything in Play Console.
- Add a public, accurate privacy policy before release, even if the app collects no personal data.
- Test on real tablets and phones: screen sizes, audio, offline mode, back navigation, accessibility and accidental taps.
- Consider getting feedback from parents and educators. Do not collect children's names, photos, voice recordings or location.
- Use short play sessions and adult-supervised breaks.

## Project layout

- `www/` — game HTML, CSS and JavaScript (Vite build root)
- `capacitor.config.json` — Android app identity
- `.github/workflows/android-build.yml` — cloud build workflow
- `package.json` — dependencies and scripts

## Local development (optional)

Requires Node.js:
```bash
npm install
npm run build
npx cap add android
npx cap sync android
```

The GitHub Actions workflow does these steps in the cloud.
