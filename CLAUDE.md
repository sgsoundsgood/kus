# Website Kühnert & Schroeder – Anweisungen für Claude

Du betreust die Website des Podcasts „Kühnert & Schroeder“ (www.kuehnertundschroeder.de) für sounds good. Wir (Constantin und Alicia) sind Laien: Erkläre alles in einfachem Deutsch, ohne Fachjargon, und sag nach jeder Änderung kurz, was du geändert hast und wo man es ansehen kann.

## Technik
- Reines statisches HTML/CSS/JS, kein Framework, kein Build-Schritt, keine Pakete.
- Repo: github.com/sgsoundsgood/kus (öffentlich, Branch `main`). Hosting: Vercel-Team „soundsgood-3d557e16“, Projekt „kuehnertundschroeder“. Jeder Push auf `main` geht automatisch live; andere Branches bekommen automatisch einen Vercel-Vorschaulink.
- Seiten: `index.html` (Start), `presse.html`, `vorab.html`, `impressum.html`, `datenschutz.html`, `404.html`. Styles in `css/style.css`, Skripte in `js/site.js`. Plattform-Links stehen in `js/config.js` UND direkt in `index.html` – bei Änderungen beide Stellen anpassen.
- `vercel.json`: cleanUrls (Adressen ohne `.html`). `/vorab` ist absichtlich nirgends verlinkt und für Suchmaschinen gesperrt (`noindex` im HTML und `X-Robots-Tag` in `vercel.json`) – das muss so bleiben.
- `.vercelignore` hält `CLAUDE.md` und `README.md` von der Live-Seite fern.
- Domain bei IONOS (A-Eintrag + CNAME auf Vercel). Daran nichts ändern.

## Design (kein Redesign ohne ausdrücklichen Auftrag)
- Einzige Schrift: Anton (lokal in `/fonts`), Wortmarke kursiv geneigt.
- Violette Verläufe, orange Akzente, pillenförmige Buttons. Farben stehen als Variablen oben in `css/style.css` (`--ks-…`).
- Plattform-Logos sind einfarbig weiß und gleich aufgebaut (Icon links, Name, Pfeil). Neue Logos genauso.
- Ansprache überall per Du.
- Jede Änderung auf Handybreite (375 px) und Desktop prüfen, kein seitliches Scrollen.

## Inhalte & Rechtliches
- Downloads (Presse, Vorab) laufen nur über Tresorit-Freigabelinks; keine Dateien ins Repo legen. Passwörter niemals in Code, Commits oder Chat schreiben.
- Kontakt: nur E-Mail-Link an team@kuehnertundschroeder.de plus Button „Adresse kopieren“. Kein Kontaktformular einbauen.
- Besucherstatistik: Simple Analytics (ohne Cookies). Klicks zählen über `data-track`-Attribute. Kein Cookie-Banner, keine weiteren Tracker, keine Einbettungen (kein YouTube-Embed, keine Google Fonts, kein reCAPTCHA) – sonst wäre ein Cookie-Banner nötig.
- Impressum und Datenschutz nur ändern, wenn wir es ausdrücklich sagen; nur belegbare Tatsachen hineinschreiben.

## Arbeitsweise
1. Änderung auf einem neuen Branch machen, pushen und uns den Vercel-Vorschaulink geben.
2. Erst wenn wir „hochladen“ sagen, in `main` übernehmen (mergen) und danach prüfen, ob die Live-Seite den neuen Stand zeigt.
3. Nie direkt auf `main` pushen ohne unser „hochladen“. Nichts an Vercel-, GitHub- oder Domain-Einstellungen ändern, ohne zu fragen.
