# Solstice Thirteen Calendar — iOS source preparation

This is the existing HTML calendar packaged as a **Capacitor 8 starter source project**. It is **not** a compiled `.ipa` and **not submitted** to Apple. It retains the existing 13-month calendar, Gregorian view, local events, world clock, natural rhythms and Cosmic Match promotion at the bottom. Added: Today button, remove event, JSON export, iOS safe-area padding and focus indicators.

## Current readiness
- Works as an offline-first local HTML app (system time and device storage); no account or backend.
- No ads or payment processing; Cosmic Match is a clearly labeled preview.
- No push alerts or iOS calendar sync; event backup requires manually exporting JSON.
- App Store screenshots are drafts; capture from the finished, installed app.
- **Apple review is not guaranteed.** Guideline 4.2 requires meaningful functionality beyond a website wrapper. Additional native value and user testing may be necessary.

## Build from a Mac or macOS cloud runner
1. Install Node.js 22+ and Xcode 26+ (Capacitor 8 iOS requirements); use a macOS CI runner if you own no Mac.
2. `npm install`
3. `npx cap add ios`
4. `npx cap sync ios`
5. Open `ios/App/App.xcworkspace` in Xcode for signing, icons, testing and archive.

The web assets are in `www/index.html`; the illustrative icon artwork is `www/app-icon.png`. **The icon is not yet wired into an Xcode asset catalog**; that is a final build step. App ID `com.solsticethirteen.calendar` is a placeholder and must be checked for availability before enrolling/signing.

## For iPad/iPhone-only developer
Upload this source ZIP to a private GitHub repository (through Safari) and engage a macOS-hosted build workflow/developer to configure Apple signing and TestFlight. Free Apple Developer profile alone does not provide App Store distribution certificates or TestFlight. Never put signing passwords/certificates in this ZIP or a public repository.

## Before App Store submission
- Add meaningful iOS functionality and validate app-review fit; remove unfinished sponsored placeholder if needed.
- Set finalized unique bundle identifier, seller details, privacy policy and support URL.
- Configure app icons/assets, distribution signing, age rating, analytics/privacy declarations.
- Test date conversions, leap years, local timezone changes, event persistence and backups on actual iPhone.
- Prepare final genuine screenshots from installed build.
- Enroll in Apple Developer Program when you are ready to sign/distribute via TestFlight/App Store.

Source: https://capacitorjs.com/docs/ios and https://developer.apple.com/app-store/review/guidelines/
