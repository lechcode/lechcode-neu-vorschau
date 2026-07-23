# Lechcode — Agentur-Website (Kontext für Claude Code)

Die Single-File-Website der Web-Agentur **Lechcode** aus Landsberg am Lech.
Eine Datei pro Seite, **kein Build** (kein npm/Vite). Einfach `index.html` im Browser öffnen.

## Dateien
- **`index.html`** — die komplette Landingpage (HTML + CSS + JS inline). Kurz-Version fürs Netzwerk: Hero mit Video-Bühne → Startangebot (790 €) → Ablauf (4 Schritte) + Pflege-Banner (19 €/M, inkl. Kundenportal) → Über uns (KI-Werkstatt-Organigramm) → Stimmen → Formular.
- **`impressum.html` · `datenschutz.html` · `agb.html`** — Rechtsseiten (gemeinsames `assets/legal.css`).
- **`assets/og.jpg`** — Teilen-Vorschaubild (WhatsApp/Social, 1200×630).
- **Hosting:** GitHub Pages, Repo `ComingHomeMira/lechcode`. `git push` auf `main` → in ~1 Min live unter **https://lechcode.de** (CNAME; IONOS-DNS zeigt auf GitHub Pages).
  ⚠ Push braucht den Account **ComingHomeMira** (`gh auth switch -u ComingHomeMira`), der `lechcode`-Account hat keine Schreibrechte.

## Marke, Ton & Look (bitte einhalten)
- **Team: Lenny & Michael** (Schönbach & Storz GbR). Kontakt: **info@lechcode.de**.
- **Tagline:** „Code mit Seele." · **Ton:** warm, auf Augenhöhe, Wert zuerst, kein Druck. Anrede durchgehend **Du**.
- **Look „Lagerfeuer":** warm-dunkel (`--night #16130c`) + Bernstein/Gold-Akzente, warme Creme-/Sand-„Lichtungen". **Kein kaltes Türkis.**
- **Fonts (lokal!):** Space Grotesk (Headlines), Inter (Fließtext), JetBrains Mono (Logo/„code", Eyebrows), Caveat (Handschrift-Akzente).
- **Logo:** Lech-Welle im Kreis (Gold). Lokale Motive: Bayertor („Wer wir sind"), Footer-Skyline, fließende Lech-Welle als Trenner.
- Voll responsive, sanfte Animationen, `prefers-reduced-motion` respektiert. **Keine externen Requests** (cookiefrei — kein Banner nötig).

## Das Angebot auf der Seite (Stand Juni 2026)
- **Startangebot:** komplette Website für einmalig **790 €** (komplett inkl. Umzug). Kein Plätze-Zähler mehr (bewusst keine Knappheit).
- **Versprechen:** erster Entwurf **in 24 h** (privater Vorschau-Link) → **30-Min-Gespräch mit Michael** → finale Version in weiteren 24 h → Umzug (MX/E-Mail nie anfassen).
- **Pflege:** 19 €/Monat (Startpreis) — Änderungen per E-Mail/WhatsApp-Sprachnachricht, monatlich kündbar.

## Formular (Sektion `#eintragen`)
- Felder: Name, E-Mail, Domain (Pflicht) + Wünsche (optional) + **Pflicht-Checkbox** (AGB + Datenschutz + Erlaubnis, Inhalte der Altseite für die Vorschau zu nutzen).
- Versand via **Web3Forms** (`fetch`, Inline-Erfolg/Fehler). **Solange der Key fehlt** (Suche `PLATZHALTER-FORM`), öffnet das Formular stattdessen automatisch eine **fertige E-Mail an info@lechcode.de** — es geht also nichts verloren.
- Eingehende Anfragen abarbeiten: siehe `landsberg-web-agentur/playbooks/auftragseingang.md` (Workspace, nicht in diesem Repo).

## ⚠ Offene Punkte (vor Versand ins Netzwerk)
1. **Video einsetzen** — Suche `PLATZHALTER-VIDEO` (lokales MP4 ≤ 15 MB, cookiefrei; kein YouTube-Embed ohne Zwei-Klick). Drehbuch: `landsberg-web-agentur/marketing/video-skript-landingpage.md`.
2. Erst danach: `noindex` auf allen Seiten gleichzeitig raus (Google-Go-Live).

✓ Erledigt (12.06.): **Formular komplett scharf** — Web3Forms-Form „Lechcode Landingpage" (in Lennys Web3Forms-Konto, Free-Plan: 250 Subm./Monat geteilt mit Coming-Home-Form, Submissions 30 Tage im Dashboard einsehbar), Empfänger **info@lechcode.de** (verifiziert), zweifach end-to-end getestet · Postfach existiert · AGB freigegeben.

## Arbeitsweise & QA
- Änderungen direkt in den HTML-Dateien; im Browser hart neu laden (Cmd+Shift+R).
- **`?foto`** an die URL hängen = alle Reveal-Animationen aus → saubere Full-Page-Screenshots.
- Qualitäts-Gates (zuletzt 12.06.2026): Lighthouse mobil **Perf 92 (lokal) · A11y 100 · BP 100** · SEO 60 = gewolltes noindex · 260 KiB · 0 externe Requests.
- Akquise-Haltung: **kein Kalt-E-Mail** (§ 7 UWG). Die Seite geht nur per Link ans eigene Netzwerk, solange noindex aktiv ist.
