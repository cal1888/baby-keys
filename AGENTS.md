Project notes and decisions live in the vault. Read them first:
@~/VaultSync/Personal/projects/baby-keys.md

## Deploy

- Pushing to `main` auto-deploys the Vercel project **`rainbow-keys`** (old name) to https://babykeys.link.
- For a manual deploy: `npx vercel --prod --yes`. The Vercel CLI isn't installed globally, so use it through npx.

## Testing gotchas

- **Playwright:** the bundled browsers aren't installed. Launch with `chromium.launch({ channel: 'chrome' })`. Playwright is global, so import it from `$(npm root -g)/playwright/index.mjs`.
- **PostHog ignores automated browsers**: it treats `navigator.webdriver` as a bot and silently drops events.
  - To check that real events send, add an init script that makes `navigator.webdriver` false and use a normal desktop user agent.
  - For every other test, block PostHog (`page.route(/posthog/, r => r.abort())`) so no fake data lands in the project.
- **Touch behaviour** (big letter tiles) only switches on when the device reports `(hover: none) and (pointer: coarse)`. Emulate a real device (`devices['iPhone 15']`); a narrow desktop window still counts as a computer.
- Presses in the first 0.12s after a new bubble appears are ignored on purpose, so a test that presses too soon won't register.
- **Share image and icons** are rendered from the page itself with Playwright: hide `#gear`, set the title text, `burst()` some letters, screenshot, then `sips` to JPEG. The icons are rendered from `favicon.svg` embedded as a data URL, because pages can't load `file://` images.
- The browser pane in the Claude app can't run scripts on `file://` pages. Serve over `python3 -m http.server` or use Playwright.
