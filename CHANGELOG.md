# CHANGELOG — IG Digital Site

Αρχείο αποφάσεων και αλλαγών. Κάθε entry γράφει **τι**, **γιατί**, και **τυχόν παρατηρήσεις** ώστε ο επόμενος (άνθρωπος ή AI) να μην ξαναρωτήσει τα ίδια.

---

## 2026-06-25

### Mobile nav: lang switcher μετακινήθηκε δίπλα στο Menu button
**Τι:** Το EN/ΕΛ switcher αφαιρέθηκε από το overlay menu και εμφανίζεται τώρα στο nav bar δίπλα στο «Menu» button σε mobile (≤760px).

**Γιατί:** Στο overlay, το switcher ήταν κρυμμένο στο κάτω μέρος και ο χρήστης έπρεπε να ανοίξει το menu για να αλλάξει γλώσσα — κακό UX. Στο nav bar είναι πάντα ορατό.

**Πώς υλοποιήθηκε:**
- Νέο wrapper `data-mobile-nav-right` (display:none desktop, display:flex mobile) που περιέχει lang switcher + Menu button
- CSS: `[data-mobile-nav-right]{ display:flex !important; }` στο `@media (max-width:760px)`
- Ο overlay lang link πήρε `data-overlay-lang` και κρύβεται με `[data-overlay-lang]{ display:none !important; }`
- Εφαρμογή και στα δύο: `IG-Digital-Home.dc.html` + `IG-Digital-Home-GR.dc.html`

**Παρατήρηση:** Το GR overlay δεν είχε lang link από πριν — μόνο το EN. Άρα το `data-overlay-lang` χρησιμοποιείται μόνο στο EN.

---

### OG image + favicon
**Τι:** Δημιουργήθηκαν `favicon.svg` και `og-image.svg` (+ PNG export 1200×630).

**Γιατί:** Το site δεν είχε social preview ούτε favicon — κακή εμφάνιση σε shares και browser tabs.

**Design:** Dark background (#070707), monogram tile «ig» με gradient dot (πορτοκαλί→teal), wordmark «ig digital», tagline «DIGITAL GROWTH STUDIO».

---

### Greek homepage
**Τι:** Δημιουργήθηκε `IG-Digital-Home-GR.dc.html` — πλήρης ελληνική έκδοση του site.

**Γιατί:** Το κοινό είναι κυρίως ελληνόφωνο. Η GR είναι η primary σελίδα (το `index.html` κάνει redirect εκεί).

**Αποφάσεις:**
- Hero: διαφορετικό από EN — «Δεν είναι τυχαίο που είστε εδώ. Κάποιος σχεδίασε τη διαδρομή.» (πιο emotional, narrative-driven)
- Όλα τα άλλα sections (services, process, work, voices, contact) είναι μεταφρασμένα αλλά δομικά πανομοιότυπα με το EN
- Κανόνας: κάθε layout/CSS/JS αλλαγή εφαρμόζεται και στα δύο αρχεία

---

### Αρχική δομή + Netlify deploy
**Τι:** Static HTML site με DC runtime, deploy σε Netlify (igdigital.netlify.app).

**Stack:** Κανένα framework, κανένα build step. `.dc.html` αρχεία + `support.js` runtime. Responsive με inline styles + `@media` block στο `<style>` κάθε αρχείου.

**Site ID Netlify:** `7379477e-3068-446b-8fae-d5577a21d2e5`

**Deploy command:**
```bash
npx netlify-cli deploy --prod --dir=design_handoff_ig_digital_site2 --site=7379477e-3068-446b-8fae-d5577a21d2e5
```

---

## Template για νέες entries

```
### [Τίτλος αλλαγής]
**Τι:** ...
**Γιατί:** ...
**Πώς υλοποιήθηκε:** ...
**Παρατήρηση:** ... (προαιρετικό)
```
