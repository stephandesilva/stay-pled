# Staypled

Groceries and pet food subscriptions, delivered across Colombo. A single-page static site (HTML, CSS and JavaScript in `index.html`) with no build step.

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole site |
| `assets/` | Hero videos (`hero-1.mp4`, `hero-2.mp4`) and their poster images |
| `.gitignore` | Files Git should not track |
| `.nojekyll` | Tells GitHub Pages to serve files as they are |

## Preview locally

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Publish with GitHub Pages

1. Create a new repository on GitHub (for example `staypled`).
2. Upload everything in this folder, or push it:
   ```
   git init
   git add .
   git commit -m "Staypled site"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/staypled.git
   git push -u origin main
   ```
3. In the repository go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
4. After a minute the site is live at `https://YOUR-USERNAME.github.io/staypled/`.
5. Optional: add a custom domain under **Settings → Pages → Custom domain**.

## Things to set before launch

Open `index.html` and edit the settings near the top of the `<script>`:

- `FORM_ENDPOINT`: where order requests are sent. Create a free form at https://formspree.io, copy its URL (`https://formspree.io/f/xxxx`) and paste it here. Requests then arrive in your email, with a readable summary. Until you set this, customers see a "copy these details" screen instead.
- `CONTACT`: your WhatsApp number (digits only, with country code) and email. They power the "Send on WhatsApp" and "Send by email" buttons if a request can't be sent.
- `CAT`: product names, sizes and prices (the prices are placeholders).
- `RATES`: currency rates (LKR per 1 unit). They are fixed numbers, not live, so update them regularly.
- `PLANS`, `AREAS`, `LEAD_DAYS`: ready-made plans, delivery areas, minimum days before first delivery.
- Delivery hours: `T0` and `T1` (currently 8 and 20, meaning 8 am to 8 pm).

## Good to know

- The moderator review page that worked inside Claude does not work here. With `FORM_ENDPOINT` set, you review and confirm custom requests from the emails you receive.
- Check you have the right to use the two hero videos on a public website.
- The site is static: no payments, accounts or order history. Payment is arranged after you confirm a plan.
