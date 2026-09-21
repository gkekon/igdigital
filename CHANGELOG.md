# CHANGELOG — IG Digital Site

Αρχείο αποφάσεων και αλλαγών. Κάθε entry γράφει **τι**, **γιατί**, και **τυχόν παρατηρήσεις** ώστε ο επόμενος (άνθρωπος ή AI) να μην ξαναρωτήσει τα ίδια.

---

## 2026-09-22

### SEO / GEO / AEO — έλεγχος και διορθώσεις
**Βρέθηκαν:** κανένα canonical, κανένα structured data, χωρίς robots.txt / sitemap.xml / llms.txt / σελίδα 404· τίτλοι αρχικής χωρίς «digital marketing agency»· περιγραφή Υπηρεσιών 198 χαρακτήρες· `og:url`/`hreflang` σε διευθύνσεις που κάνουν 301· το intro (ρίζα του site) χωρίς περιγραφή και χωρίς συνδέσμους για crawlers που δεν τρέχουν JS.
**Τι:** Νέοι τίτλοι/περιγραφές (αρχική, Υπηρεσίες). Script `tools/seo_build.py` που γράφει canonical, hreflang (x-default = ρίζα), og:url στις τελικές διευθύνσεις, JSON-LD (ProfessionalService με τις 7 υπηρεσίες, WebSite, WebPage· Article + BreadcrumbList στα case studies) και παράγει `robots.txt` (ανοιχτό σε μηχανές και AI crawlers, κλειστό για .md και παρκαρισμένες σελίδες), `sitemap.xml` (με hreflang) και `llms.txt`. Intro: περιγραφή, noindex/follow, noscript σύνδεσμοι· index: noscript σύνδεσμοι. Νέα δίγλωσση `404.html` (για τα παλιά URL του WordPress). Footer: «Σχεδιάστηκε από την ig digital». «Κλιμάκωση/Scaling» χωρίς θαυμαστικό.
**Εκκρεμεί:** (1) καθαρά URL (π.χ. /el/ti-kanoume) μαζί με το domain· (2) στο Google Business Profile ο ΤΚ είναι **591 32**, στο site **59131** — να επιβεβαιωθεί ο σωστός (NAP consistency)· (3) για AEO: ενότητα «Συχνές ερωτήσεις» με ορατό περιεχόμενο + FAQ schema· (4) αριθμοί/χώρες για το Strategy design.

### Sentence case σε όλους τους τίτλους υπηρεσιών
**Τι:** Κεφαλαίο μόνο στο πρώτο γράμμα (Strategy design, Branding & identity, Performance & targeting, Content & film, Digital experience · Branding & ταυτότητα, Περιεχόμενο & film, Ψηφιακή εμπειρία) στην αρχική και στη σελίδα Υπηρεσιών· και στις κάρτες «Η ειδικότητά μας» (Performance campaigns / Performance καμπάνιες).
**Γιατί:** Ήταν ανακατεμένα. Sentence case = Apple-style, ίδιο με όλους τους μεγάλους τίτλους του site, και το σωστό για τα ελληνικά.

### Υπηρεσίες: τελικοί τίτλοι
**Τι:** «Branding & Identity» / «Branding & Ταυτότητα» και «Performance & Targeting» / «Performance & στόχευση» (πιο σύντομα). Τελική λίστα: We start with you · Strategy Design · Branding & Identity · Performance & Targeting · Content & Film · Digital Experience · Scaling!

### Υπηρεσίες: 7 αντί για 9 · «What we do»
**Τι:** EN μενού/footer: «What we do» (αντί «We do What?», που στα αγγλικά διαβάζεται σαν ειρωνεία). Ενώθηκαν Targeting + Performance → «Performance Campaigns & Targeting» / «Performance καμπάνιες & στόχευση», και AI Search + Digital Experience → ενιαία υπηρεσία με τίτλο «Digital Experience» / «Ψηφιακή Εμπειρία» (επιλογή πελάτη, πιο κομψό)· η περιγραφή λέει sites & landing pages που τα βρίσκουν Google και AI (SEO · GEO · AEO), e-shops μέσω συνεργάτη. Πρώτη υπηρεσία EN: «We start with you» (GR μένει «Γινόμαστε ένα με εσάς»). Kicker σελίδας: «Services»/«Υπηρεσίες». Νέες εικόνες προεπισκόπησης.
**Γιατί:** Απόφαση πελάτη — πιο σφιχτή λίστα, χωρίς ακρωνύμια ως τίτλους.

### Υπηρεσίες: νέοι τίτλοι και ειλικρινές εύρος
**Τι:** «Understanding & Becoming One With You» · «Brand Design & Identity» / «Brand Design & Ταυτότητα» · το Search έγινε «AI Search Optimization» / «Ορατότητα σε Google & AI» (SEO · GEO · AEO) · Digital Experience: sites και landing pages από εμάς, **e-shops μέσω έμπιστου συνεργάτη** · Κλιμάκωση: «όταν κάτι πετυχαίνει, δεν επαναπαυόμαστε — το κλιμακώνουμε». Αρχική + σελίδα Υπηρεσιών, GR + EN.
**Γιατί:** Ο πελάτης δεν φτιάχνει e-shops in-house και θέλει να προσφέρει SEO/GEO/AEO ως νέα υπηρεσία· το προηγούμενο κείμενο υποσχόταν «Web & commerce».

### Αρχική: η λίστα «Τι κάνουμε» στις 9 νέες · footer · «βασικά βήματα»
**Τι:** Η λίστα της αρχικής (GR+EN) έχει πια τις ίδιες 9 υπηρεσίες με τη σελίδα, με σύντομες φράσεις (όσες υπήρχαν κρατήθηκαν). Footer: «We do What?» / «Τι κάνουμε;». Η εισαγωγή της σελίδας δεν μετράει πια υπηρεσίες: «Every essential step, one senior team.» / «Όλα τα βασικά βήματα, μία έμπειρη ομάδα.»
**Γιατί:** Αίτημα πελάτη — ίδια λίστα παντού, χωρίς αριθμό που θα αλλάζει.

### Υπηρεσίες → «We do What?» / «Τι κάνουμε;» με 9 ενότητες
**Τι:** Στο μενού (υπολογιστής + κινητό) το «Services»/«Υπηρεσίες» έγινε «We do What?»/«Τι κάνουμε;». Η σελίδα έχει τίτλο «What we do.»/«Τι κάνουμε.» και 9 ενότητες με τη σειρά του πελάτη: Understanding & becoming one with you · Strategy Design · Branding & Identity · Detailed Targeting · Performance Campaigns · Search & Discovery · Content & Film · Digital Experience · Scaling! Τα υπάρχοντα κείμενα κρατήθηκαν αυτούσια· Targeting και Scaling πήραν τις περιγραφές που ήδη υπήρχαν στην αρχική· νέα κείμενα για Understanding (από το κείμενο του πελάτη) και Strategy Design (εμπειρία ΕΕ & ΗΠΑ). Βγήκε το Lifecycle & CRM. Νέες εικόνες προεπισκόπησης, τίτλοι και περιγραφές.
**Γιατί:** Αίτημα πελάτη.
**Παρατήρηση:** Η λίστα «01 — Τι κάνουμε» στην αρχική έχει ακόμα τις 6 παλιές υπηρεσίες (με Lifecycle & CRM) — να ευθυγραμμιστεί; Το footer γράφει ακόμα «Services»/«Υπηρεσίες».

### Φόρμα επικοινωνίας: στέλνει πραγματικά (Netlify Forms)
**Τι:** Η φόρμα δεν έστελνε τίποτα — απλώς έδειχνε «Ευχαριστούμε». Τώρα: πεδία με όνομα, `data-netlify` + honeypot κατά του spam, αποστολή με fetch, «Αποστολή…» / «Ευχαριστούμε» μόνο αν πέτυχε / «Δεν στάλθηκε» αν αποτύχει. Ενεργοποιήθηκε η αναγνώριση φορμών στο Netlify (ήταν κλειστή) και ειδοποίηση email στο **info@igdigital.gr**. Δοκιμή από το live αποθηκεύτηκε κανονικά (όχι spam).

### Domain igdigital.gr — προετοιμασία στο Netlify
**Τι:** Δημιουργήθηκε ζώνη DNS igdigital.gr στο Netlify (nameservers dns1–dns4.p01.nsone.net) με **όλες** τις εγγραφές του email που ζει στον cPanel server της intechs (46.62.175.92, srv25.intechs.gr): MX → mail.igdigital.gr, mail/webmail/autodiscover/autoconfig/cpanel/whm/webdisk/ftp/cpcalendars/cpcontacts A, SPF, DKIM (default._domainkey), DMARC, SRV για autodiscover/caldav/carddav. Το site έχει igdigital.gr (κύριο) + www.igdigital.gr.
**Γιατί:** Ο developer που έχει το domain στην intechs ζήτησε DNS servers. Αν άλλαζαν χωρίς αυτές τις εγγραφές, θα σταματούσαν τα email (και οι ειδοποιήσεις της φόρμας).
**Εκκρεμεί:** η intechs αλλάζει nameservers → μετά: έλεγχος SSL, ενημέρωση `og:url`/`hreflang`/canonical από igdigital.netlify.app σε https://igdigital.gr, redirects για τα παλιά URL του WordPress. Ο hosting λογαριασμός στην intechs πρέπει να μείνει ενεργός (εκεί είναι τα email). Τα email apps πρέπει να χρησιμοποιούν **mail.igdigital.gr** ως server, όχι σκέτο igdigital.gr.

### Backup
Πλήρες αντίγραφο (με git) + full-page screenshots desktop/κινητό όλων των σελίδων στο `IG DIGITAL/backup/igdigital-site-2026-09-22/`, πριν από τις αλλαγές της 22/9.

## 2026-09-21

### Κουμπί «Δωρεάν strategy call · 30′» σε όλες τις σελίδες · Μενού/Κλείσιμο · πελάτης Έργου 01
**Τι:** Το κουμπί πάνω δεξιά με την κίνηση «αναπνοής» (όπως στην αρχική) μπήκε σε Έργο 01, Έργο 02 και Υπηρεσίες, GR+EN — αντικατέστησε το «Ξεκινήστε ένα project» στο nav και στο μενού κινητού. Ελληνικό site: «Μενού / Κλείσιμο». Έργο 01: πελάτης «Ανώνυμο ελληνικό e-commerce brand» / «Anonymous Greek e-commerce brand», ίδια διατύπωση με το Έργο 02.
**Γιατί:** Απόφαση πελάτη — ίδιο κύριο CTA σε όλο το site.

### Deploy 21/9 — όλα τα παραπάνω live
**Τι:** Commit `b34d12c` και deploy στο production (igdigital.netlify.app). Επαληθεύτηκε live: GR Υπηρεσίες, πραγματικές κριτικές (χωρίς ψεύτικες), 31 λογότυπα, font stack με Segoe UI, `lang`, OG images στο `<head>`.
**Παρατήρηση:** Το `npx netlify-cli deploy` απέτυχε σιωπηλά (exit 1, χωρίς μήνυμα). Το deploy έγινε με το εγκατεστημένο `netlify` (Homebrew, v26). Μετά από κάθε deploy επαληθεύουμε με `curl` στο live — το «δεν έβγαλε σφάλμα» δεν αρκεί. Το GitHub (`origin`) **δεν** έχει γίνει push.

### Γραμματοσειρά: σωστό fallback για τα ελληνικά σε κάθε πλατφόρμα
**Τι:** Το font stack έγινε `'Sora',-apple-system,BlinkMacSystemFont,'Segoe UI',Roboto,'Helvetica Neue',Arial,sans-serif` σε 9 σελίδες (25 σημεία). Τα λατινικά μένουν Sora. Τα ελληνικά: SF Pro σε Apple (και στον Chrome σε Mac, που πριν έβγαζε Helvetica), Roboto σε Android, **Segoe UI στα Windows (πριν: Arial)**.
**Γιατί:** Η Sora δεν έχει ελληνικά· στα Windows τα ελληνικά έβγαιναν σε Arial. Ο πελάτης κράτησε τη λύση «γραμματοσειρά συστήματος» (του αρέσει σε iPhone/Android) αντί για ελληνικό webfont.
**Παρατήρηση:** Aurelia, Home v2 και Logo Concepts δεν άλλαξαν (εκτός scope).

### Μεγάλο πέρασμα: μαρτυρίες, λογότυπα, GR Υπηρεσίες, γλώσσα επισκέπτη, animation, προεπισκοπήσεις
**Τι:**
- **Μαρτυρίες:** αφαιρέθηκαν οι ψεύτικες (Dana Reyes, Idris Bello, Sofia Lind). Μπήκαν οι 4 πραγματικές κριτικές Google με κείμενο (NagaCommerce πρώτη, Pesmatzoglou Ilias, Giota Spiridou, Nikos Kotsalidis) + ένδειξη «5,0 στο Google · 5 κριτικές». EN μεταφρασμένες.
- **Λογότυπα:** 31 λογότυπα με τη σειρά του φακέλου `logo πελατων με σειρα`, λευκά/διάφανα, ίσο οπτικό βάρος, στο `uploads/clients-ordered/`. Desktop: όλα ανοιχτά. Κινητό: μένει όπως στο live — λίγα + «Δείτε όλα» (απόφαση πελάτη, μινιμαλιστικό look). Αφαιρέθηκαν όσα δεν είναι στη νέα λίστα (U wash, Linea Strom, elvi, Kate, Free Shop, Flame, Quinta, Americana) — τα αρχεία τους έμειναν στο `uploads/clients/`.
- **Νέα σελίδα `IG-Digital-Services-GR.dc.html`**· όλες οι ελληνικές σελίδες (14 σύνδεσμοι) δείχνουν εκεί.
- **Γλώσσα επισκέπτη:** το `intro.html` διαλέγει GR/EN (προηγούμενη επιλογή → ζώνη ώρας Ελλάδας/Κύπρου → γλώσσα συσκευής).
- **Animation:** τα SVG visuals (2 κάρτες αρχικής + 4 σελίδες case) σχηματίζονται στο scroll προς τα κάτω και μαζεύονται όταν φεύγουν, ξαναπαίζοντας στο scroll προς τα πάνω. Αλλαγή μηχανισμού από CSS `width` σε `transform:scaleX` για συμβατότητα με Safari.
- **Διαδικασία:** οι 4 τίτλοι (Ακούμε/Εστιάζουμε/Χτίζουμε/Κλιμακώνουμε) στοιχισμένοι στην ίδια ευθεία.
- **«spend» → «δαπάνη»** σε όλες τις ελληνικές σελίδες.
- **Προεπισκοπήσεις:** 6 εικόνες 1200×630 στο `og/` (case 01/02 + Υπηρεσίες, GR/EN) + `hreflang` σε όλα τα ζεύγη σελίδων. Όλα τα SEO/OG tags (και της αρχικής) μεταφέρθηκαν από το `<helmet>` στο πραγματικό `<head>`, για να τα διαβάζουν WhatsApp/Viber/LinkedIn.
**Γιατί:** Αιτήματα πελάτη (12 σημεία, 21/9).
**Παρατήρηση:** Η Sora δεν έχει ελληνικά — τα ελληνικά αποδίδονται με τη γραμματοσειρά του συστήματος. Δεν άλλαξε ακόμα, εκκρεμεί απόφαση.

## 2026-08-29

### Έργο 01 (Έλεγχος): νέο SVG visual στο ύφος του site, GR+EN, home & landing
**Τι:** Το PNG banner του Έργου 01 αντικαταστάθηκε από SVG «Από τον θόρυβο στη γραμμή»: μπλεγμένες λεπτές γραμμές (θολά σήματα ενός σύνθετου account) συγκλίνουν σε έναν κόμβο ελέγχου και βγαίνουν δύο καθαρές παράλληλες κορδέλες που ανεβαίνουν (πορτοκαλί = Meta, τιρκουάζ = Google). Landing: σχηματίζεται στο scroll (`initSvgAnim`, ίδιο μοτίβο με το Έργο 02). Αρχική: split κάρτα ίδια με του Έργου 02, νέο σύντομο copy, 4 metrics. Και οι δύο κάρτες πήραν κοινό ελάχιστο ύψος· στο κινητό τα metrics μπαίνουν 2×2 (`.case-metrics`) και το visual χρησιμοποιεί τον υπάρχοντα κανόνα `data-case-visual` (240px).
**Γιατί:** Ενιαία οπτική γλώσσα στα case studies, χωρίς βαριά AI-generated banners.
**Παρατήρηση:** `uploads/case-studies/elegxos-banner.png` δεν αναφέρεται πουθενά πια· δεν διαγράφηκε.

### Audit GR/EN — διορθώσεις κειμένου
**Τι:** Ορθογραφικό «ΚΥΛΗΣΗ»→«ΚΥΛΙΣΗ»· «Δες όλα»→«Δείτε όλα» (ενιαίος πληθυντικός ευγενείας)· Elegxos GR: αμετάφραστο «PAID MEDIA INVESTMENT», ενοποίηση «Μ.Ο./ΜΕΣΗ ΑΞΙΑ ΚΑΛΑΘΙΟΥ», «7,37x»→«7,37×», ελληνικό alt· Elegxos EN: «One more controlled» (διαβαζόταν «άλλο ένα»)→«A more controlled», curly apostrophes, «catalogue» (UK spelling όπως το υπόλοιπο site)· Kerdoforia GR: αγγλικές ετικέτες στο strip→ελληνικές· κάρτα αρχικής GR ευθυγραμμίστηκε με το νέο lede· `lang="el"/"en"` σε όλες τις σελίδες· Services: έλειπε εντελώς `<title>` και meta description.
**Γιατί:** Audit συνέπειας GR↔EN πριν το deploy.

### Έργο 02 (Κερδοφορία): νέο copy + hand-drawn SVG visual, GR+EN, home & landing
**Τι:** Ξαναγράφτηκε ολόκληρο το κείμενο του case study «Κερδοφορία» (Έργο 02) με βάση διορθώσεις του ιδρυτή, και το banner PNG (1.7MB) αντικαταστάθηκε από hand-authored SVG σε όλα τα σημεία που εμφανίζεται: την κάρτα `#work` στο home (GR+EN) και το hero visual της landing σελίδας (GR+EN).
- Νέος τίτλος: «Δεν χρειαζόταν περισσότερες πωλήσεις. Χρειαζόταν καλύτερες.» (πριν: «Από τον τζίρο στην κερδοφορία»).
- Landing σελίδα αναδιαρθρώθηκε σε 8 sections: hero, SVG visual, πρόκληση+στοιχεία, αποτέλεσμα (2 ομάδες: εμπορικά / paid media, 8 metrics), «το πιο δυνατό αποτέλεσμα», προσέγγιση (3 κάρτες: Profit before ROAS / Product mix before discount / Efficiency before scale), εμπορική αλλαγή (7-metric strip + safe profitability framing), νέο statement.
- Το SVG visual («η ψαλίδα» — δύο κορδέλες που ανοίγουν, τζίρος↑ vs εκπτώσεις↓) έχει 3 στρώματα βάθους, σχηματίζεται μπαίνοντας στο κάδρο (`initSvgAnim` στο DC script της landing σελίδας), και honoreί `prefers-reduced-motion`.
- Η κάρτα `#work` στο home έγινε split-layout (visual SVG αριστερά, copy+metrics δεξιά) αντί για μονολιθικό banner· ίδιο SVG concept σε στατική μορφή, με δικά της gradient ids (`wk-*`, χωρίς σύγκρουση με τα `k-*` της landing).

**Γιατί:** Ο ιδρυτής έστειλε νέο, πιο ακριβές κείμενο (7 metrics αντί για 4, νέο framing γύρω από profit-first vs revenue-first, εναλλακτικό «safe» profitability paragraph αντί για μοντελοποιημένο +44%). Παράλληλα ζητήθηκε πιο minimal/premium/αφαιρετικό visual στο ύφος του site, με βάθος (dark-light 3D) και κίνηση στο scroll — το PNG banner δεν κάλυπτε κανένα από τα δύο.

**Πώς υλοποιήθηκε:** SVG χτισμένο από το μηδέν (χωρίς εξωτερικές βιβλιοθήκες), 3 layers (`.far`/`.mid`/`.near`) με ξεχωριστό parallax μέσω `--p` custom property ενημερωμένο σε scroll (rAF-throttled). Entrance μέσω CSS class toggle (`.svg-in`) που πυροδοτείται από IntersectionObserver. Το EN mirror μεταφράστηκε πλήρως (φυσικά αγγλικά, όχι literal), με δεκαδικά σε τελεία. Διορθώθηκε en route ένα προϋπάρχον bug στο language switcher του EN case-study αρχείου (ο σύνδεσμος προς το GR έγραφε «EN» αντί για «ΕΛ» — προέκυψε επειδή το EN χτίστηκε πάνω στη δομή του GR).

**Παρατήρηση:** Το `uploads/case-studies/kerdoforia-banner.png` έμεινε στον δίσκο αλλά δεν αναφέρεται πουθενά πια — δεν διαγράφηκε (ίδια λογική με το ορφανό Aurelia page: αναμονή επιβεβαίωσης πριν διαγραφεί τίποτα). Το Έργο 01 (Elegxos) παραμένει ανέγγιχτο, ίδιο PNG banner όπως πριν — καθαρά επιλογή του ιδρυτή να ξεκινήσουμε από το Έργο 02. **Deploy GR + EN μαζί, μετά την έγκριση του πελάτη.**

---

## 2026-07-24

### EN mirror των case studies + mobile Services
**Τι:** Ολοκληρώθηκε το αγγλικό mirror των δύο πραγματικών case studies και διορθώθηκε η mobile συμπεριφορά της σελίδας Services.
- Το `#work` του `IG-Digital-Home.dc.html` χρησιμοποιεί πλέον τα δύο πραγματικά banner cards αντί για τα placeholders Aurelia / Fintech / Hospitality.
- Δημιουργήθηκαν τα `IG-Digital-Case-Elegxos-EN.dc.html` και `IG-Digital-Case-Kerdoforia-EN.dc.html` με φυσική αγγλική απόδοση, ίδια δομή/assets/metrics και αγγλική μορφή δεκαδικών.
- Τα language switches των τεσσάρων case pages συνδέουν πλέον απευθείας τη σωστή GR/EN εκδοχή.
- Το `IG-Digital-Services.dc.html` απέκτησε mobile breakpoint 760px, responsive single-column grids και hamburger navigation με overlay.

**Γιατί:** Το EN site έδειχνε ακόμη ψεύτικα placeholder έργα, ενώ η Services σελίδα παρουσίαζε horizontal overflow και μη λειτουργικό desktop nav σε μικρές οθόνες.

**Πώς υλοποιήθηκε:** Έγινε mirror του εγκεκριμένου GR `#work`, μετάφραση πάνω στα υπάρχοντα GR case templates χωρίς αλλαγή σε layout, colors, data attributes ή DC scripts, και αντιγραφή του καθιερωμένου `menuOpen` / mobile-nav μοτίβου από το Elegxos case study στη Services.

**Παρατήρηση:** Το `support.js` έμεινε ανέγγιχτο. Το CTA της Services που έδειχνε στην παλιά Aurelia σελίδα επαναδρομολογήθηκε σε `IG-Digital-Home.dc.html#work` («View case studies →»), ώστε κανένα link να μη στέλνει σε ψεύτικο περιεχόμενο. Η Aurelia (`IG-Digital-Case-Study.dc.html`) κρατήθηκε ως έχει (απόφαση πελάτη) — orphaned πλέον. Ο hamburger κώδικας είναι πανομοιότυπος με το production home· δεν είναι click-testable μέσα από το preview automation (το DC synthetic-event δεν πυροδοτείται — ίδια συμπεριφορά και στο live home), χρειάζεται tap-test σε πραγματική συσκευή. **Deploy GR + EN μαζί.** Εκκρεμούν πραγματικές μαρτυρίες (#voices) από τον πελάτη.

### Δύο πραγματικά case studies + banner cards στο #work
**Τι:** Δημιουργήθηκαν 2 νέες GR case study σελίδες και το `#work` section του GR home δείχνει τώρα σε αυτές με τα banners του πελάτη.
- `IG-Digital-Case-Elegxos.dc.html` — «Απόδοση με έλεγχο» (Έργο 01, φυσικά προϊόντα / performance· +13,3% τζίρος, 7,37× Meta ROAS, 4,47× Google ROAS)
- `IG-Digital-Case-Kerdoforia.dc.html` — «Από τον τζίρο στην κερδοφορία» (Έργο 02, αθλητικό e-shop / profit-first· +11,3% τζίρος, −31,5% εκπτώσεις, +31,9% Meta ROAS)

**Γιατί:** Ο ιδρυτής (αδερφός του πελάτη) έστειλε 2 πραγματικά case studies (κείμενο .docx + banner + full-page mockup). Αντικατέστησαν τα placeholder «Έργα 01/02/03» (Aurelia/Fintech/Hospitality).

**Πώς υλοποιήθηκε:**
- Χτισμένες από το μηδέν σε responsive HTML (όχι embedded εικόνες κειμένου), ίδια design tokens / cursor / reveal / tilt / scrollbar με το υπόλοιπο site.
- Δομή: hero (breadcrumb + τίτλος + hero-stats) → banner ως visual poster → πρόκληση + στοιχεία συνεργασίας → grid αποτελεσμάτων (6–7 metrics) → «Η προσέγγιση» (3 κινήσεις) → statement → τελικό CTA → footer.
- **Mobile-first:** hamburger nav + overlay + `@media (max-width:760px)` block. Grids καταρρέουν 3-4→2→1 στήλες, μηδέν horizontal overflow (ελέγχθηκε 402px iPhone 17 Pro + 1280px desktop).
- `#work` (GR): 2 banner cards (`uploads/case-studies/*-banner.png`), self-contained, χωρίς footer (το banner περιέχει τα πάντα). Κρατούν `data-case` για tilt/hover.
- Πεδίο ΠΕΛΑΤΗΣ: **χωρίς** «Ανώνυμο» (πιο confident· η ανωνυμία δηλώνεται στη σημείωση μέτρησης).

**Παρατήρηση:** EN mirror (home #work + 2 EN case pages) και mobile fix σε Services/παλιά Aurelia σελίδα → μηχανική δουλειά, spec στο `CODEX-HANDOFF.md`. Εκκρεμεί: οι Μαρτυρίες (#voices) έχουν ψεύτικα ονόματα αποδιδόμενα σε «Έργο 01/02/03» — θέλουν πραγματικό περιεχόμενο.

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
