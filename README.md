# Isadore Films — website source

Plain HTML/CSS, no build step, no dependencies. Two pages: `index.html` and `contact.html`, sharing `styles.css` and the `images/` folder (your original beach and skyline photos, pulled straight from the current site).

## 1. Put it on GitHub Pages (free hosting)

1. Create a new GitHub repository (public is fine — a static site has no secrets in it). Name doesn't matter.
2. Upload these files to it (drag-and-drop on github.com works, or `git push` if you're comfortable with git).
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Still on that Pages settings screen, under **Custom domain**, type `isadorefilms.com` and save. GitHub will create a `CNAME` file in your repo automatically — leave it there.

## 2. Point your domain at it

In your domain's DNS settings (wherever you manage isadorefilms.com — not GitHub), add:

- Four **A** records for the root domain (`@`), pointing to:
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- One **CNAME** record for `www`, pointing to `<your-github-username>.github.io`

DNS changes usually take effect within a couple of hours (can take up to 24-48). Once it resolves, GitHub auto-issues a free HTTPS certificate for the domain — no action needed, just wait for the padlock to show up.

## 3. Turn on the contact form

The form in `contact.html` posts to Formspree, which is free for up to 50 submissions/month and needs no backend:

1. Go to formspree.io and create a free account with **isadorefilms@gmail.com**.
2. Click **New Form**, name it anything (e.g. "Isadore Films Contact").
3. Formspree gives you a URL like `https://formspree.io/f/abcd1234`.
4. Open `contact.html`, find the line `action="https://formspree.io/f/YOUR_FORM_ID"`, and replace `YOUR_FORM_ID` with your real ID. Re-upload the file (or push the change) to your repo.

Until you do that, the form will just fail silently — the phone and email links on the contact page work immediately either way.

## 4. Cancel Weebly

Only after isadorefilms.com is loading the new site correctly (check from a phone on cell data too, not just a browser that might be caching the old one) — then cancel the Weebly subscription. Nothing else depends on it once DNS has switched over.

---

**Total ongoing cost: $0/month** for hosting, vs. $20/month on Weebly. You keep paying only for whatever you already pay to keep the domain itself registered, wherever that is.
