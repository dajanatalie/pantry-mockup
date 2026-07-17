# Pantry Automation Mock-up — Deploy auf Cloudflare Pages

Statische Single-Page-App (`index.html`, kein Build, keine Abhängigkeiten).

## Weg A: GitHub → Cloudflare Pages (empfohlen, mit Auto-Deploy)
1. Neues GitHub-Repo anlegen (z. B. `pantry-mockup`, public oder private).
2. `index.html` ins Repo-Root pushen:
   ```
   git init
   git add index.html README.md
   git commit -m "Pantry mockup"
   git branch -M main
   git remote add origin https://github.com/<dein-user>/pantry-mockup.git
   git push -u origin main
   ```
3. Cloudflare Dashboard → **Workers & Pages → Create → Pages → Connect to Git** → Repo wählen.
4. Build settings: Framework preset **None**, Build command **leer lassen**, Output directory **/** (Root).
5. Deploy → URL im Format `https://pantry-mockup.pages.dev`. Jeder Push deployt automatisch neu.

## Weg B: Direct Upload (ohne GitHub, 2 Minuten)
Cloudflare Dashboard → Workers & Pages → Create → Pages → **Direct Upload** → Ordner mit `index.html` hochladen. Fertig.

## Für die Präsentation
- Die `pages.dev`-URL auf Slide 13 eintragen (Platzhalter im Gamma-Prompt).
- Demo-Pfad (ca. 3–4 Min): Request anlegen (kleine Menge → Auto-Approval + Lieferanten-Mail; große Menge → Approval-Queue) → Order genehmigen → Mail-Preview zeigen → Copilot-Chip "Low stock items?" klicken → kurz Architecture- und Prioritization-Tab zeigen.
- Fallback: `index.html` läuft auch lokal per Doppelklick im Browser (kein Server nötig).
