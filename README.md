# radish-site

Public site for the Radish iOS app ("Radish: Recipes & Planning" on the App Store): a landing page, the support page, and the
privacy policy. The support and privacy URLs go on the App Store listing.

Plain static HTML, no build step. `.nojekyll` tells GitHub Pages to serve the files as they
are. All links are relative, so the site works both under `/<repo>/` on `github.io` and at
the root of a custom domain.

```
index.html           landing page
support/index.html   support page   → <site>/support/
privacy/index.html   privacy policy → <site>/privacy/
style.css            shared styles (light + dark)
```

Preview locally: `python3 -m http.server 8000` in this folder, then open
<http://localhost:8000>.

## Publishing


## Keeping the privacy policy true

The policy describes what the app does today. Update it in the same change when any of
these move in the app repo (`radish`):

- collected data types in `Radish/PrivacyInfo.xcprivacy` (and the App Privacy labels)
- what account deletion keeps or removes (`docs/account-deletion.md`)
- what is sent to OpenAI (`supabase/functions/openai-proxy/`)
- any new third-party service or SDK

## Hosting

GitHub Pages from `main` (root), custom domain `getradishrecipes.com` (the `CNAME` file).
The domain is registered at Squarespace; DNS records there point at GitHub Pages. Pushing to
`main` publishes within a minute or two. Contact address on the pages:
`support@getradishrecipes.com`.
