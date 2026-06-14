# Track Sets Website

Static GitHub Pages site for `trackset.net`.

## Store submission URLs

- Marketing URL: `https://trackset.net/`
- Accessibility URL: `https://trackset.net/#accessibility`
- Privacy Policy URL: `https://trackset.net/#privacy-policy`
- Support URL: `https://trackset.net/#support`
- Data Deletion URL: `https://trackset.net/#data-deletion`
- Terms URL: `https://trackset.net/#terms`

## GitHub Pages setup

After this PR is merged:

1. In GitHub, open **Settings > Pages** for this repository.
2. Set **Build and deployment** to deploy from a branch.
3. Select the `main` branch and `/ (root)` folder.
4. Confirm the custom domain is `trackset.net`.

The `CNAME` file is already included for the custom domain. The site is intentionally one long page; app store URLs use in-page anchors on the same root URL.

## HTTPS certificate gate

Before submitting to app stores, confirm the custom domain serves a valid HTTPS certificate:

```powershell
curl.exe -I https://trackset.net/
```

The current DNS apex records point at GitHub Pages (`185.199.108.153` through `185.199.111.153`, plus the matching `2606:50c0:*::153` IPv6 records), but the certificate must also be provisioned for `trackset.net`. If `curl` reports `SEC_E_WRONG_PRINCIPAL` or a hostname mismatch, open the repository's GitHub Pages settings, wait for the custom-domain certificate to finish provisioning, and enable Enforce HTTPS before using the Store submission URLs.

## Store notes

The privacy and data deletion copy matches the current app state:

- No account system.
- No ads or in-app purchases.
- No analytics SDKs.
- No network features.
- No developer-side collection, sharing, or sale of user data.
- Exercise data and settings are stored locally on the user's device.

Before submitting to app stores, make sure the support email shown on the published site is routed to a monitored inbox.
