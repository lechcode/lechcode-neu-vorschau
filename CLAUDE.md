# Lechcode — Agentur-Website, NEUER ENTWURF (Kontext für Claude Code)

Die Single-File-Website der Web-Agentur **Lechcode** aus Landsberg am Lech.
Eine Datei pro Seite, **kein Build** (kein npm/Vite). Einfach `index.html` im Browser öffnen.

> ⚠️ **Dieses Repo ist die Vorschau, nicht die Live-Seite.**
> `lechcode/lechcode-neu-vorschau` → https://lechcode.github.io/lechcode-neu-vorschau/
> Die echte **lechcode.de** liegt in einem **anderen** Repo (`lechcode/lechcode`) und wird
> ausschließlich von **Lenny** umgeschaltet. Ein Push hier ändert an lechcode.de **nichts**.

## Dateien
- **`index.html`** — die komplette Landingpage (HTML + CSS + JS inline). Kurz-Version fürs Netzwerk: Hero mit Video-Bühne → Startangebot (790 €, alles inkl.) → Ablauf (4 Schritte) + „Alles auf uns"-Banner (0 €/Monat, Dashboard) → Warum Lechcode (3-Wege-Vergleich) → Über uns (KI-Werkstatt-Organigramm) → Stimmen (Slider) → Formular.
- **`impressum.html` · `datenschutz.html` · `agb.html`** — Rechtsseiten (gemeinsames `assets/legal.css`). **Preis in der AGB muss = Preis auf der Seite sein** (aktuell 790 €).
- **`assets/team-*.jpg`** — die sieben Porträts des Organigramms. **Michael und Lenny sind echte Fotos** (400 px, seit 31.07.); Klaus · Aldo · Mona · Leonardo · Andrea sind **Illustrationen** (384 px). Die fünf KI-Rollen tragen ein goldenes **KI**-Schildchen am Bild, die Gründer keins. Der Medium-Bruch Foto/Zeichnung ist gewollt (ehrliche Unterscheidung Mensch/Maschine) — ⚠ noch nicht gestaltet sind Hintergrund und Aufnahmedistanz, siehe „Offene Punkte".
- **`assets/lenis.js`** — weiches Scrollen, lokal mitgeliefert (kein externer Request).
- **`assets/og.jpg`** — Teilen-Vorschaubild (WhatsApp/Social, 1200×630).
- **`robots.txt` · `sitemap.xml`** — SEO-Fundament für den Cutover (beide mit Anleitung im Kopf; solange `noindex` gilt, sperrt robots.txt bewusst).
- **Hosting:** GitHub Pages, Repo `lechcode/lechcode-neu-vorschau`. `git push` auf `main` → nach ~1 Min sichtbar unter **https://lechcode.github.io/lechcode-neu-vorschau/**. Kein CNAME, keine Live-Domain.
- **Cutover** (wenn der Entwurf die echte Seite werden soll): Der fertige Stand wandert ins Live-Repo `lechcode/lechcode` → lechcode.de. **Das macht Lenny**, nicht automatisch und nicht aus diesem Repo heraus.

## Zusammenarbeit — Michi (Windows) & Lenny (MacBook) arbeiten parallel
Beide nutzen dasselbe GitHub-Konto **`lechcode`** und arbeiten gleichzeitig an diesem Repo.
Damit sich niemand die Arbeit überschreibt:
- **Vor dem Arbeiten:** `git pull --rebase` — immer, auch für eine Kleinigkeit.
- **Vor dem Push nochmal:** `git pull --rebase`, dann `git push`.
- **Niemals** `git push --force` auf `main`.
- **Größere Umbauten** (Sektion verschieben, Datei umbenennen, Design-System ändern) vorher kurz ansagen — die ganze Seite steckt in **einer** Datei, da kollidiert man schnell.
- Git-Identität lokal setzen, falls der Klon frisch ist:
  `git config user.name "…"` · `git config user.email "info@lechcode.de"`
- Unter Windows/PowerShell: Commit-Nachrichten **ohne doppelte Anführungszeichen** schreiben, sonst zerlegt PowerShell 5.1 das `-m`-Argument.

## Marke, Ton & Look (bitte einhalten)
- **Team: Lenny & Michael** (Schönbach & Storz GbR). Kontakt: **info@lechcode.de**.
- **Tagline:** „Code mit Seele." · **Ton:** warm, auf Augenhöhe, Wert zuerst, kein Druck. Anrede durchgehend **Du**.
- **Look „Lagerfeuer":** warm-dunkel (`--night #16130c`) + Bernstein/Gold-Akzente, warme Creme-/Sand-„Lichtungen". **Kein kaltes Türkis.**
- **Fonts (lokal!):** Space Grotesk (Headlines), Inter (Fließtext), JetBrains Mono (Logo/„code", Eyebrows), Caveat (Handschrift-Akzente).
- **Logo:** Lech-Welle im Kreis (Gold). Lokale Motive: Bayertor („Wer wir sind"), Footer-Skyline, fließende Lech-Welle als Trenner.
- Voll responsive, sanfte Animationen, `prefers-reduced-motion` respektiert. **Keine externen Requests** (cookiefrei — kein Banner nötig).

## Das Angebot auf der Seite (Stand Juli 2026)
- **Startangebot:** komplette Website für einmalig **790 € — wirklich alles inklusive**. Kein Plätze-Zähler (bewusst keine Knappheit).
- **Versprechen:** erster Entwurf **in 24 h** (privater Vorschau-Link) → **30-Min-Gespräch mit Michael** → finale Version in weiteren 24 h → Umzug (MX/E-Mail nie anfassen).
- **Danach keine laufenden Kosten (Modellwechsel 23.07.):** Das 19-€-Abo ist gestrichen. Hosting **und** Domain trägt Lechcode (→ „0 € laufend" als No-Brainer-Argument). Änderungen unbegrenzt selbst übers **Dashboard** oder per Nachricht, ohne Aufpreis. ⚠ Reale Domain-Kosten (~10–15 €/Jahr/Kunde) trägt damit Lechcode — bewusste Entscheidung. AGB §4/§5/§8/§9 entsprechend angepasst, **mit `von Lenny prüfen`-Marker** (u. a. offen: wem gehört die Domain, was passiert bei Vertragsende).

## Texte — drei Stellen, die zusammenhängen (leicht zu übersehen)
- **Headline** (seit 31.07.): „Deine neue Website. **Morgen schon fertig.**" Die drei Meta-Beschreibungen (`description`, `og:description`, `twitter:description`) **und** die JSON-LD-Beschreibung sagen denselben Satz. Ändert sich die Headline, müssen alle vier mit — das ist der Text im Google-Snippet und in der WhatsApp-Vorschau.
- **Video-Laufzeit** steht doppelt: in der Bildunterschrift und im `aria-label` des `<video>`. Aktuell „dreieinhalb Minuten".
- **Stimmen-Lead nennt die Namen einzeln** („Emily, Anna, C. M. und Sibylle"). Kommt eine Bewertung dazu oder fällt eine weg, muss der Lead mit — sonst stimmt die Aufzählung nicht mehr. Die `aria-label`s der Karten („Bewertung 3 von 4") ebenfalls.
- **Team-Karten:** Höchstens die zwei Gründer-Absätze dürfen mit dem Eigennamen beginnen. Wenn alle sieben so anfangen — und der Name steht zwei Zeilen darüber schon im `<h3>` — klingt die ganze Reihe nach Maschine. Das war der Hauptbefund der Überarbeitung vom 31.07.

## Formular (Sektion `#eintragen`)
- Felder: Name, E-Mail, Domain (Pflicht) + Wünsche (optional) + **Pflicht-Checkbox** (AGB + Datenschutz + Erlaubnis, Inhalte der Altseite für die Vorschau zu nutzen).
- Versand via **Web3Forms** (`fetch`, Inline-Erfolg/Fehler). **Solange der Key fehlt** (Suche `PLATZHALTER-FORM`), öffnet das Formular stattdessen automatisch eine **fertige E-Mail an info@lechcode.de** — es geht also nichts verloren.
- Eingehende Anfragen abarbeiten: siehe `landsberg-web-agentur/playbooks/auftragseingang.md` (Workspace, nicht in diesem Repo).

## ⚠ Offene Punkte
1. **`noindex` bleibt drin**, solange diese Fassung unter der Vorschau-URL liegt — sonst stünde sie als zweite, fast gleiche Seite neben lechcode.de in Google. Raus kommt es erst beim Cutover, zusammen mit `robots.txt` (siehe Kommentar im Kopf von `index.html`).
2. ✓ **Video erledigt (31.07.):** neues Video, 58 MB statt 87, Laufzeit 3:34. Rezept und Begründung stehen in der `README.md`. Lädt dank `preload="none"` weiterhin erst beim Klick.
3. **Porträt-Familie angleichen.** Michaels und Lennys echte Fotos haben hellen Hintergrund und werden auf dem dunklen Panel zu leuchtenden Scheiben, während die fünf KI-Porträts in die Sektion hineinschmelzen; dazu sind die echten Gesichter im selben Kreis rund doppelt so groß (KI-Bilder sind Halbfiguren, deren Requisiten der Kreis anschneidet). **Bruch Foto/Zeichnung behalten, Hintergrund + Distanz angleichen.**
4. **Gründer-Ebene ohne Querbalken:** Die Linie zu Klaus startet im Leerraum zwischen den beiden Karten. Die Werkstatt-Ebene darunter hat einen echten Verteiler — zwei Grammatiken in einem Diagramm.
5. **Vor dem Cutover:** OG-Tags auf den drei Rechtsseiten ergänzen · `ASSETS-LIZENZEN.md` anlegen (Foto-Rechte) · Lighthouse neu messen.
6. ⚠️ **`lc-qa` meldet auf dieser Seite 4× ROT „Externer Request"** — das sind die vier `rel="canonical"`-Links auf lechcode.de. Ein Canonical-Tag löst nie einen Request aus; das Gate liest das `rel`-Attribut nicht ein. **Fehlalarm, nicht auf der Seite fixen.** Die Seite hat weiterhin 0 externe Requests.

✓ Video ist eingebaut (lokal, cookiefrei, mit Poster) — der Vermerk `PLATZHALTER-VIDEO` in der CSS ist nur noch ein Kommentar-Rest.

✓ Erledigt (12.06.): **Formular komplett scharf** — Web3Forms-Form „Lechcode Landingpage" (in Lennys Web3Forms-Konto, Free-Plan: 250 Subm./Monat geteilt mit Coming-Home-Form, Submissions 30 Tage im Dashboard einsehbar), Empfänger **info@lechcode.de** (verifiziert), zweifach end-to-end getestet · Postfach existiert · AGB freigegeben.

## Bewegung & Leistung — bitte nicht versehentlich zurückdrehen
Die Seite hat bewusst viel Bewegung, aber jede davon ist gedeckelt. Diese Entscheidungen
sehen nach „Kleinkram" aus und sind es nicht:
- **Funkenfeld (`canvas.funken`, 4 Stück):** zeichnet **nur das Band, das gerade im Bild ist**.
  Der Über-uns-Abschnitt ist ~4000 px hoch — die volle Fläche pro Bild zu löschen hat auf
  dem Handy sichtbar geruckelt. Ebenso gedeckelt: Puffer-Auflösung (Handy 1,4 MP / Desktop 3,2 MP)
  und Partikelzahl (Handy 56 / Desktop 96).
- **Ab 900 px aufwärts** (auf dem Handy bewusst aus): Filmkorn (`body::after`, Vollbild-Mischung),
  Schweben der sieben Porträts, weiches Scrollen (Lenis). Auf Touch bleibt natives Scrollen.
- **Aufbau-Sequenzen** (Organigramm, Eyebrow-Tippeffekt) hängen an Klassen, die **das Skript
  selbst setzt und wieder abräumt**. Grundsatz: **Inhalt darf nie an einer Animation hängen** —
  ohne JavaScript oder ohne laufende Animation muss alles sofort lesbar dastehen.
- `prefers-reduced-motion` schaltet alles ab. Bitte bei jeder neuen Animation mitdenken.

## Arbeitsweise & QA
- Änderungen direkt in den HTML-Dateien; im Browser hart neu laden (Cmd+Shift+R).
- **`?foto`** an die URL hängen = alle Reveal-Animationen aus → saubere Full-Page-Screenshots.
- Erstes Laden ≈ **630 KB** (davon ~490 KB lokale Schriften), Porträts ~140 KB kommen lazy dazu,
  Video nur auf Klick. **0 externe Requests** — bitte so lassen (cookiefrei, kein Banner nötig).
- Qualitäts-Gates zuletzt am 12.06.2026 gemessen (Lighthouse mobil Perf 92 lokal · A11y 100 · BP 100);
  seither sind Porträts, Lenis und die Animationen dazugekommen — **vor dem Cutover neu messen**.
- Akquise-Haltung: **kein Kalt-E-Mail** (§ 7 UWG). Die Seite geht nur per Link ans eigene Netzwerk, solange noindex aktiv ist.
