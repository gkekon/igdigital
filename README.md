# IG Digital — Agency Site

**Live:** [igdigital.netlify.app](https://igdigital.netlify.app) (→ igdigital.gr μόλις αλλάξουν οι nameservers)  
**Stack:** Static HTML (no build step, no framework)  
**Languages:** Greek (primary) + English  
**AI Collaboration:** Claude Code + OpenAI Codex

---

## Δομή αρχείων

Το repo έχει **δύο επίπεδα**: τα εσωτερικά έγγραφα μένουν στη ρίζα και **δεν ανεβαίνουν**· ό,τι ανεβαίνει στο Netlify είναι μέσα στο `site/`.

```
design_handoff_ig_digital_site2/
├── README.md · CHANGELOG.md · PROMPT_START.md · CODEX-HANDOFF.md   ← εσωτερικά, ΔΕΝ ανεβαίνουν
├── netlify.toml                                                    ← publish = "site"
└── site/                                  ← ο φάκελος του deploy
    ├── index.html                         ← spiral intro (ρίζα /) · διαλέγει GR/EN για τον επισκέπτη
    ├── 404.html · _redirects              ← σελίδα 404 · 301 από τα παλιά URL στα νέα
    ├── support.js                         ← DC runtime (ΜΗΝ επεξεργαστείς)
    ├── vendor/                            ← React 18.3.1 · ReactDOM · Lenis (τοπικά, για ταχύτητα)
    ├── _headers                           ← cache: /vendor ένας χρόνος, assets μία εβδομάδα, σελίδες ποτέ
    ├── favicon.svg · og-image.png · og/   ← favicon + προεπισκοπήσεις 1200×630 (GR/EN)
    ├── robots.txt · sitemap.xml · llms.txt  ← τα γράφει το tools/seo_build.py
    │
    ├── el/index.html                      → /el/                        αρχική (GR)
    ├── en/index.html                      → /en/                        αρχική (EN)
    ├── el/ti-kanoume.html                 → /el/ti-kanoume              Υπηρεσίες (GR)
    ├── en/what-we-do.html                 → /en/what-we-do              Services (EN)
    ├── el/erga/apodosi-me-elegxo.html     → /el/erga/apodosi-me-elegxo  Έργο 01 (GR)
    ├── en/work/performance-under-control.html → /en/work/performance-under-control  Έργο 01 (EN)
    ├── el/erga/kerdoforia.html            → /el/erga/kerdoforia         Έργο 02 (GR)
    ├── en/work/profit-first.html          → /en/work/profit-first       Έργο 02 (EN)
    │
    ├── IG-Digital-Case-Study.dc.html      ← παλιά Aurelia (παρκαρισμένη, μένει ως έχει)
    ├── IG-Digital-Home v2.dc.html         ← παλιά εκδοχή (μένει ως έχει)
    ├── IG-Digital-Logo-Concepts.dc.html
    └── uploads/
        ├── clients-ordered/               ← 31 λογότυπα πελατών, με τη σειρά του πελάτη (τα ενεργά)
        ├── clients/                       ← παλιά λογότυπα (δεν χρησιμοποιούνται πια)
        └── case-studies/                  ← παλιά banners/mockups (δεν χρησιμοποιούνται πια)
```

**Διαδρομές:** όλοι οι σύνδεσμοι και τα assets είναι απόλυτα από τη ρίζα (`/el/ti-kanoume`, `/el/#contact`, `/uploads/…`, `/support.js`), γιατί οι σελίδες ζουν σε υποφακέλους. Το Netlify σερβίρει το `el/ti-kanoume.html` ως `/el/ti-kanoume` και το `el/index.html` ως `/el/`.

---

## Σημαντικές συμβάσεις (για Claude & Codex)

### 1. Οι σελίδες είναι DC αρχεία (production)
Από 22/9 έχουν κατάληξη `.html` (όχι `.dc.html`) για καθαρά URL — παραμένουν DC σελίδες (`<x-dc>` + `support.js`). Δεν είναι mockups. Ανοίγουν απευθείας στο browser ως κανονικά HTML. Το `support.js` runtime τα επεξεργάζεται — **μη τροποποιείς το `support.js`**.

### 2. Bilingual — πάντα και τα δύο
Κάθε αλλαγή στο `site/en/…` **πρέπει να αντικατοπτρίζεται** και στο αντίστοιχο `site/el/…`, και αντίστροφα.  
Μοναδική σκόπιμη διαφορά: το hero section (διαφορετικό περιεχόμενο σε EN vs GR).

### 3. Inline styles — όχι external CSS
Το layout χτίζεται αποκλειστικά με **inline `style=`** attributes. Δεν υπάρχει εξωτερικό CSS αρχείο. Responsive overrides γίνονται με `@media` κανόνες στο `<style>` block εντός κάθε αρχείου (lines ~30-78).

### 4. Data attributes για targeting
Χρησιμοποιούμε `data-*` attributes για responsive/behavioral targeting:

| Attribute | Χρήση |
|---|---|
| `data-desktop-nav` | Nav links — κρύβεται σε mobile (`display:none !important`) |
| `data-mobile-nav-right` | Lang switcher + Menu button wrapper — φαίνεται μόνο mobile |
| `data-mobile-toggle` | Το κουμπί «Menu» — `display:block !important` σε mobile |
| `data-overlay-lang` | Lang link μέσα στο overlay — κρύβεται σε mobile |
| `data-navlink` | Nav anchor links (active state JS) |
| `data-magnetic` | Magnetic hover effect |
| `data-cta-pill` | CTA pill buttons |
| `data-cta-primary` | Primary CTA button |
| `data-reveal` | Scroll reveal animation |
| `data-service` | Service list rows |
| `data-proc-card` | Process step cards |
| `data-clients` | Client logos grid |
| `data-clients-toggle` | «Show more» button για logos |
| `data-case-visual` | Case study visual block |

### 5. DC template syntax
Το `support.js` runtime επεξεργάζεται:
- `{{ variable }}` — template interpolation
- `<sc-if value="{{ condition }}">` — conditional render
- `onClick="{{ functionName }}"` — event binding

Παράδειγμα (mobile menu overlay):
```html
<sc-if value="{{ menuOpen }}" hint-placeholder-val="{{ false }}">
  <div>...menu content...</div>
</sc-if>
```

### 6. Mobile breakpoint: 760px
Όλα τα responsive overrides στο `@media (max-width:760px)` block. Nav padding αλλάζει σε `16px 20px`, desktop nav κρύβεται, mobile nav εμφανίζεται.

---

## Design System

| Token | Τιμή |
|---|---|
| Background | `#000000` |
| Text primary | `#f5f5f7` |
| Text muted | `rgba(245,245,247,0.45–0.62)` |
| Accent orange | `#fd672c` |
| Accent teal | `#53d6be` |
| Gradient (CTA/logo dot) | `linear-gradient(135deg, #fd672c, #53d6be)` |
| Font display/body | Sora (Google Fonts) — χωρίς ελληνικά· stack: `'Sora',-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,'Helvetica Neue',Arial,sans-serif` |
| Font mono/labels | JetBrains Mono (Google Fonts) |
| Border subtle | `rgba(255,255,255,0.06–0.22)` |
| Border radius pill | `100px` |
| Border radius card | `20–28px` |

---

## Nav structure (mobile)

```
[ ig digital logo ]        [ EN | ΕΛ   Menu ]
```

- `EN | ΕΛ` switcher εμφανίζεται στο nav bar (δίπλα στο Menu), **όχι** μέσα στο overlay menu
- Στο desktop: ο switcher είναι μέσα στο `data-desktop-nav` div μαζί με τα nav links
- Overlay menu: έχει μόνο τα navigation links + CTA — χωρίς lang switcher

---

## Deploy

Το site deployer μέσω **Netlify MCP** ή CLI:

```bash
netlify deploy --prod --dir=design_handoff_ig_digital_site2/site --site=7379477e-3068-446b-8fae-d5577a21d2e5
```

Κάθε αλλαγή → deploy χειροκίνητα (δεν υπάρχει auto-deploy από git). Τρέχει από τον φάκελο `Site design/`. Χρησιμοποίησε το εγκατεστημένο `netlify` (Homebrew) — το `npx netlify-cli` αποτυγχάνει σιωπηλά. Μετά το deploy έλεγξε το live με `curl`.

Πριν από οποιαδήποτε αλλαγή: δες τη λίστα ελέγχου ομοιομορφίας και τις «αποφάσεις του πελάτη» στο `.claude/skills/ig-digital/SKILL.md` (ένα επίπεδο πάνω).

---

## Επικοινωνία

| | |
|---|---|
| Email | info@igdigital.gr |
| Τηλέφωνο | +30 697 378 9466 |
| Διεύθυνση | Εδέσσης 23, Βέροια, ΤΚ 591 32 |
| Instagram | [@igdigitalgr](https://www.instagram.com/igdigitalgr/) |

---

## Ιστορικό αλλαγών

Δες το [CHANGELOG.md](CHANGELOG.md) για λεπτομερές ιστορικό αποφάσεων (τι, γιατί, πώς υλοποιήθηκε).
