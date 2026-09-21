# IG Digital — Agency Site

**Live:** [igdigital.netlify.app](https://igdigital.netlify.app)  
**Stack:** Static HTML (no build step, no framework)  
**Languages:** Greek (primary) + English  
**AI Collaboration:** Claude Code + OpenAI Codex

---

## Δομή αρχείων

```
/
├── index.html                     ← redirect → intro.html
├── intro.html                     ← spiral intro · διαλέγει GR/EN για τον επισκέπτη
├── support.js                     ← DC runtime (ΜΗΝ επεξεργαστείς)
├── netlify.toml                   ← cache headers
├── favicon.svg · og-image.png     ← favicon + προεπισκόπηση αρχικής
├── og/                            ← προεπισκοπήσεις 1200×630 ανά σελίδα (GR/EN)
│
├── IG-Digital-Home-GR.dc.html     ← αρχική (GR)
├── IG-Digital-Home.dc.html        ← αρχική (EN)
├── IG-Digital-Services-GR.dc.html ← Υπηρεσίες (GR)
├── IG-Digital-Services.dc.html    ← Services (EN)
├── IG-Digital-Case-Elegxos.dc.html / -EN      ← Έργο 01 «Απόδοση με έλεγχο»
├── IG-Digital-Case-Kerdoforia.dc.html / -EN   ← Έργο 02 «Κερδοφορία»
├── IG-Digital-Case-Study.dc.html  ← παλιά Aurelia (orphaned, μένει ως έχει)
├── IG-Digital-Home v2.dc.html     ← παλιά εκδοχή (μένει ως έχει)
├── IG-Digital-Logo-Concepts.dc.html
└── uploads/
    ├── clients-ordered/           ← 31 λογότυπα πελατών, με τη σειρά του πελάτη (τα ενεργά)
    ├── clients/                   ← παλιά λογότυπα (δεν χρησιμοποιούνται πια)
    └── case-studies/              ← παλιά banners/mockups (δεν χρησιμοποιούνται πια)
```

---

## Σημαντικές συμβάσεις (για Claude & Codex)

### 1. Τα `.dc.html` είναι τα production αρχεία
Δεν είναι mockups. Ανοίγουν απευθείας στο browser ως κανονικά HTML. Το `support.js` runtime τα επεξεργάζεται — **μη τροποποιείς το `support.js`**.

### 2. Bilingual — πάντα και τα δύο
Κάθε αλλαγή στο `IG-Digital-Home.dc.html` **πρέπει να αντικατοπτρίζεται** και στο `IG-Digital-Home-GR.dc.html`, και αντίστροφα.  
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
netlify deploy --prod --dir=design_handoff_ig_digital_site2 --site=7379477e-3068-446b-8fae-d5577a21d2e5
```

Κάθε αλλαγή → deploy χειροκίνητα (δεν υπάρχει auto-deploy από git). Τρέχει από τον φάκελο `Site design/`. Χρησιμοποίησε το εγκατεστημένο `netlify` (Homebrew) — το `npx netlify-cli` αποτυγχάνει σιωπηλά. Μετά το deploy έλεγξε το live με `curl`.

Πριν από οποιαδήποτε αλλαγή: δες τη λίστα ελέγχου ομοιομορφίας και τις «αποφάσεις του πελάτη» στο `.claude/skills/ig-digital/SKILL.md` (ένα επίπεδο πάνω).

---

## Επικοινωνία

| | |
|---|---|
| Email | info@igdigital.gr |
| Τηλέφωνο | +30 697 378 9466 |
| Διεύθυνση | Εδέσσης 23, Βέροια, ΤΚ 59131 |
| Instagram | [@igdigitalgr](https://www.instagram.com/igdigitalgr/) |

---

## Ιστορικό αλλαγών

Δες το [CHANGELOG.md](CHANGELOG.md) για λεπτομερές ιστορικό αποφάσεων (τι, γιατί, πώς υλοποιήθηκε).
