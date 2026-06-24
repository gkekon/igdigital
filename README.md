# Handoff: IG Digital — Premium Agency Site

## Overview
Αυτό είναι το production-ready site της **IG Digital** (igdigital.gr). Είναι ένα **στατικό HTML site** — δεν χρειάζεται build process, framework, ή server-side rendering. Τα αρχεία τρέχουν απευθείας στο browser.

Στόχος: push σε GitHub repo → auto-deploy μέσω Netlify.

---

## Σχετικά με τα αρχεία
Τα `.dc.html` αρχεία **ΕΙΝΑΙ τα production αρχεία** — όχι mockups. Δουλεύουν ως κανονικά HTML αρχεία στον browser, χρησιμοποιώντας το `support.js` runtime που βρίσκεται στο ίδιο directory. Το `support.js` δεν πρέπει ποτέ να επεξεργαστεί χειροκίνητα.

---

## Αρχεία & Δομή

```
/
├── index.html                        ← redirect → IG-Digital-Home-GR.dc.html
├── support.js                        ← DC runtime (μη επεξεργαστείς)
├── netlify.toml                      ← Netlify config (cache headers κλπ)
├── IG-Digital-Home-GR.dc.html        ← 🔴 Κύρια σελίδα (Greek homepage)
├── IG-Digital-Home.dc.html           ← English homepage (v1 baseline)
├── IG-Digital-Services.dc.html       ← Services subpage (EN)
├── IG-Digital-Case-Study.dc.html     ← Aurelia case study (EN)
└── uploads/
    ├── clients/                      ← Processed client logos (λευκά PNG)
    │   ├── kate.png
    │   ├── filtrato.png
    │   ├── herbstore.png
    │   ├── linea.png
    │   ├── elvi.png
    │   ├── uwash.png
    │   ├── papillon.png
    │   ├── pythagoras.png
    │   ├── vero.png
    │   ├── freeshop.png
    │   ├── pigikids.png
    │   ├── flame.png
    │   ├── quinta.png
    │   └── americana_mono.png
    └── [πρωτότυπα logos...]          ← Originals (δεν χρησιμοποιούνται live)
```

---

## Deploy σε GitHub + Netlify

### Βήμα 1 — Git init & push

```bash
cd design_handoff_ig_digital_site

git init
git add .
git commit -m "initial: IG Digital site"

# Δημιούργησε νέο repo στο github.com με όνομα π.χ. "ig-digital-site"
# μετά:
git remote add origin https://github.com/YOUR_USERNAME/ig-digital-site.git
git branch -M main
git push -u origin main
```

### Βήμα 2 — Netlify

1. Πήγαινε στο [app.netlify.com](https://app.netlify.com)
2. **«Add new site»** → **«Import from Git»** → GitHub
3. Επίλεξε το `ig-digital-site` repo
4. **Build settings:**
   - Build command: *(άδειο)*
   - Publish directory: `.`
5. **«Deploy site»**

Netlify subdomain: από Site settings → Domain management → άλλαξε σε `igdigital.netlify.app`

### Βήμα 3 — Auto-deploy από Claude
Κάθε φορά που γίνονται αλλαγές στο design (από Claude/Designcompiler):
```bash
# copy updated files → git commit → push
git add .
git commit -m "update: [περιγραφή αλλαγής]"
git push
# Netlify auto-deploys σε ~20 δευτ.
```

---

## Brand & Design System

| Token | Τιμή |
|---|---|
| Background | `#000000` |
| Text primary | `#f5f5f7` |
| Accent orange | `#fd672c` |
| Accent teal | `#53d6be` |
| Font display/body | Sora (Google Fonts) |
| Font mono/labels | JetBrains Mono (Google Fonts) |

---

## Επικοινωνία & Links
- Email: info@igdigital.gr
- Τηλέφωνο: +30 697 378 9466
- Διεύθυνση: Εδέσσης 23, Βέροια, ΤΚ 59131
- Instagram: https://www.instagram.com/igdigitalgr/

---

## Σημειώσεις
- Το site είναι **bilingual** — Greek homepage (`IG-Digital-Home-GR.dc.html`) είναι η κύρια.
- Το `index.html` κάνει redirect εκεί αυτόματα.
- Τα 3D objects (Three.js), Lenis smooth scroll, magnetic CTAs, scroll reveals φορτώνουν από CDN — χρειάζεται internet connection.
- Client logos είναι στο `uploads/clients/` ως λευκά transparent PNG.
