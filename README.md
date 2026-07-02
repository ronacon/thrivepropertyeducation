# Thrive Property Education — Landing Page

The marketing landing page for Thrive Property Education, Simon Bawden's renovation advisory business. Deployed as a static site to GitHub Pages behind the custom domain `thrivepropertyeducation.co.uk`.

Live: https://thrivepropertyeducation.co.uk/

## Stack

Plain HTML/CSS/JS — no build step, no dependencies. Fonts are loaded from Google Fonts (`Oswald` + `DM Sans`); everything else is a single `index.html`.

## Structure

```
index.html          Page markup, styles, and interaction JS (all inline)
assets/images/       Logo and photo assets referenced by index.html
calculator/          Built output of the thrive-budget-calculator app, served at /calculator
robots.txt           Crawler rules
sitemap.xml          Sitemap for search engines
CNAME                Custom domain config for GitHub Pages
```

## Local development

Open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8000
```

## Deployment

GitHub Pages serves directly from the `main` branch (Settings → Pages). Pushing to `main` publishes immediately — there's no build or CI step.

## Tracking

Google Tag Manager container `GTM-PZRPPTD5` is wired in `index.html` (`<head>` script + `<body>` noscript fallback).

## Notes

- The "Check Your Readiness" CTA and footer "Readiness Check" link now point to `/calculator/`, which serves the built output of the [thrive-budget-calculator](https://github.com/ronacon/thrive-budget-calculator) app. That repo's `dist/` output is copied into `calculator/` here manually after each build — there's no automated sync yet, so re-copy and commit after any calculator update.
- The email signup form (`#newsletter`) only does a client-side success message — it doesn't actually submit anywhere yet. Needs wiring to an email provider (Kajabi, Mailchimp, etc.) before relying on it to capture leads.
