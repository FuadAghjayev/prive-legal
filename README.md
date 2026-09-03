# PRIVE — Legal pages

Public legal documents for the PRIVE mobile app, served via GitHub Pages.

| Page | File | Used in Play Console as |
|---|---|---|
| Privacy Policy | `privacy-policy.html` | App content → Privacy policy URL |
| Account deletion | `delete-account.html` | App content → Data safety → Account deletion URL |

Static HTML, no build step, no dependencies. Edit the files and push; Pages redeploys automatically.

## Publishing

1. Create a **public** repository named `prive-legal` on GitHub.
2. Push this directory to it.
3. Repository → Settings → Pages → Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)`.
4. Wait for the first deploy, then verify both URLs load in a private browser window.

## Keeping it accurate

The privacy policy describes what the app actually does. Re-check it whenever any of these change:

- new permission in `AndroidManifest.xml` or `ios/Runner/Info.plist`
- new third-party SDK in `pubspec.yaml`
- new field collected at registration
- change in how payments are handled

Two items are deliberately worded conservatively and should be revisited:

- **Security (section 9)** does not claim encryption in transit. Once the backend serves HTTPS
  everywhere, add an explicit statement that traffic is encrypted with TLS.
- **Account deletion** is handled by email because the backend has no account-deletion endpoint.
  When `DELETE /users/me` exists and the app has an in-app delete button, update
  `delete-account.html` to describe the in-app path first.
