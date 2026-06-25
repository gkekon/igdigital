# Starter Prompt — IG Digital Site

Κάνε copy-paste αυτό στην αρχή κάθε νέας συζήτησης.

---

## Για Claude Code

```
Δουλεύουμε στο site της IG Digital. Το project βρίσκεται στο:
/Users/konstantinosgkekopoulos/Documents/Επιχειρηση/IG DIGITAL/Site design/design_handoff_ig_digital_site2/

Διάβασε πρώτα:
1. README.md — conventions, δομή, design system
2. CHANGELOG.md — ιστορικό αποφάσεων

Κύριοι κανόνες:
- Κάθε αλλαγή εφαρμόζεται και στα δύο: IG-Digital-Home.dc.html + IG-Digital-Home-GR.dc.html
- Μόνο inline styles — δεν υπάρχει external CSS
- Μη αγγίξεις το support.js
- Mobile breakpoint: 760px

Live site: https://igdigital.netlify.app

[Γράψε εδώ τι θέλεις να κάνουμε]
```

---

## Για Codex / ChatGPT

```
You are working on the IG Digital agency website. Static HTML project, no framework, no build step.

Project files are in: design_handoff_ig_digital_site2/

Start by reading:
1. README.md — conventions, file structure, design system
2. CHANGELOG.md — history of decisions and why they were made

Key rules:
- Every change must be mirrored to BOTH: IG-Digital-Home.dc.html (EN) and IG-Digital-Home-GR.dc.html (GR)
- Layout is built entirely with inline styles — no external CSS file
- Never edit support.js (it's the DC runtime)
- Responsive overrides live in the <style> block inside each file, @media (max-width:760px)
- Mobile breakpoint: 760px

Live site: https://igdigital.netlify.app
Deploy: npx netlify-cli deploy --prod --dir=design_handoff_ig_digital_site2 --site=7379477e-3068-446b-8fae-d5577a21d2e5

Task: [describe what you want to do]
```
