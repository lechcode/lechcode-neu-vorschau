# Lechcode — neuer Website-Entwurf 👋

Der neue Stand unserer Agentur-Seite. Für **Michi und Lenny** — wir arbeiten hier beide dran.
Jede Seite ist **eine HTML-Datei**, kein Build, kein npm. Datei öffnen, ändern, fertig.

## 👀 Anschauen

- **Vorschau-Link** (aktualisiert sich ~1 Minute nach jedem Push):
  **https://lechcode.github.io/lechcode-neu-vorschau/**
- Oder lokal: `index.html` doppelklicken.

> Diese Vorschau ist **noindex** — bei Google unsichtbar, über den Link aber für jeden erreichbar.
> Sie ist **nicht** lechcode.de. An der Live-Seite ändert sich hier nichts.

## ✏️ Ändern — zwei Wege

Wir sind beide im selben **`lechcode`-GitHub-Konto**, also hat jeder von uns vollen Zugriff.

### Weg A · Direkt im Browser (für Texte, schnell)
Auf GitHub die Datei öffnen → Stift-Symbol → ändern → unten „Commit changes".
Nach ~1 Minute steht es in der Vorschau. Gut für Tippfehler, Preise, einzelne Sätze.
Praktisch: Im Repo einfach **`.`** drücken — dann öffnet sich ein vollwertiger Editor im Browser.

### Weg B · Lokal mit Claude Code (für alles Größere)
```bash
git clone https://github.com/lechcode/lechcode-neu-vorschau.git
cd lechcode-neu-vorschau
```
Ordner in Claude Code öffnen und sagen, was du willst. Die `CLAUDE.md` erklärt ihm den Aufbau,
die Marke und die Technik-Regeln automatisch. Danach:
```bash
git add -A
git commit -m "kurz was geändert wurde"
git push
```

## 🎬 Das Video — ✅ ausgetauscht am 31.07.2026

Das neue Landingpage-Video ist drin. **87 MB → 58 MB**, Laufzeit jetzt **3:34** statt 6:18.
Poster-Standbild (`assets/video-poster.jpg`) passend dazu erneuert.

**Michi, zu deinem 10–15-MB-Wunsch — ehrlich gerechnet:** Das ist bei 1080p und 3:34 nicht
drin. 15 MB wären ~0,56 Mbit/s, da matscht jedes Gesicht. Was tatsächlich den Unterschied
gemacht hat, ist **Entrauschen vor dem Encoden**: Bei fester Kamera frisst das feine
Sensorrauschen unverhältnismäßig viel Bitrate. Ohne Entrauschen landete dasselbe Material
bei ~114 MB und riss GitHubs 100-MB-Grenze; mit landet es bei 58 MB, und im 1:1-Ausschnitt
ist kein Unterschied zum Original zu sehen.

Das Rezept für nächste Mal (ffmpeg):
```bash
ffmpeg -i "Neues Landingpage Video.mov" \
  -c:v libx264 -profile:v high -preset slow -crf 26 -maxrate 2600k -bufsize 5200k \
  -pix_fmt yuv420p -vf "hqdn3d=2:1.5:6:6,scale=1920:-2" \
  -c:a aac -b:a 112k -ac 2 -movflags +faststart assets/lechcode-video.mp4
```
Willst du wirklich unter ~30 MB, geht das nur über **720p** (`scale=1280:-2`) — halbiert es
etwa. Auf einer Seite mit `preload="none"` lädt das Video ohnehin erst beim Klick, deshalb
haben wir die Qualität behalten.

⚠️ **Video-Tausch geht NICHT über die GitHub-Weboberfläche** (Uploader nimmt max. 25 MB).
Immer über Weg B:
```bash
git pull --rebase
# neue Datei nach assets/lechcode-video.mp4 kopieren (gleicher Name = sonst nichts zu tun)
git add assets/lechcode-video.mp4 assets/video-poster.jpg
git commit -m "Neues Video"
git push
```
GitHub warnt beim Push ab 50 MB — das ist nur eine Warnung, hart blockt es erst ab 100 MB.

- **Untertitel:** Einbaustelle steht als Kommentar direkt am `<video>`-Element. Wenn eine
  deutsche `.vtt` vorliegt, dort die `<track>`-Zeile einkommentieren. Das ist weiterhin die
  einzige bekannte Barrierefreiheits-Lücke der Seite.
- ⚠️ **Laufzeit steht an zwei Stellen im Text** (Bildunterschrift + `aria-label` am `<video>`).
  Bei einem neuen Schnitt beide mitziehen — aktuell „dreieinhalb Minuten".

## 🤝 Damit wir uns nicht überschreiben

- **Vor dem Arbeiten:** `git pull --rebase` — immer, auch für eine Kleinigkeit.
- **Vor dem Push nochmal:** `git pull --rebase`, dann `git push`.
- **Niemals** `git push --force` auf `main`.
- **Größere Umbauten vorher kurz ansagen** — die ganze Seite steckt in *einer* Datei,
  da kollidiert man schnell.
- Wer über die Weboberfläche ändert, arbeitet immer auf dem neuesten Stand. Der andere muss
  danach `git pull --rebase` machen, bevor er weitermacht.

## 🚀 Live gehen
Der fertige Stand wandert ins Live-Repo (`lechcode/lechcode`) → lechcode.de.
**Das macht Lenny**, in einem eigenen Schritt. Aus diesem Repo heraus passiert es nicht.

Beim Cutover sind es genau zwei Handgriffe (beide im Code kommentiert):
1. In allen vier HTML-Dateien `noindex, nofollow` → `index, follow`
2. In `robots.txt` `Disallow: /` → `Allow: /` plus Sitemap-Zeile

## 📄 Was drinsteht (Stand 31.07.2026)

- **Angebot:** komplette Website einmalig **790 €**, wirklich alles inklusive.
  **Kein 19-€-Abo mehr** — danach null laufende Kosten, Hosting und Domain tragen wir.
  Änderungen unbegrenzt über das Dashboard oder per Nachricht.
- **Headline neu (31.07.):** „Deine neue Website. **Morgen schon fertig.**" (vorher „…zum
  Ansehen."). Die drei Meta-Beschreibungen und die JSON-LD-Beschreibung sind mitgezogen —
  das ist der Text im Google-Snippet und in der WhatsApp-Vorschau.
- **Über uns** als KI-Werkstatt-Organigramm: wir beide plus fünf klar gekennzeichnete KI-Rollen.
  Auf Desktop aufgeklappt, am Handy zugeklappt.
- **Stimmen** als Slider mit vier echten Bewertungen (Emily und Anna von Trustpilot,
  C. M. und Sibylle von Google). ⚠️ Der Lead nennt die Namen einzeln — **bei einer fünften
  Stimme den Lead mitziehen**, sonst stimmt die Aufzählung nicht mehr.
- **Sprach-Runde 28.07.:** Texte komplett auf „menschlich statt KI" überarbeitet, vom KI-Team
  in vier Runden durchlaufen und abgenommen.

## 🔧 Was am 31.07. passiert ist (Lenny + KI-Team)

- **Video** neu, siehe oben.
- **Echte Fotos** von Michael und Lenny im Organigramm — vorher standen dort KI-illustrierte
  Versionen im Stil der fünf KI-Rollen.
- **Team-Texte komplett neu.** Der Auslöser: alle sieben Absätze fingen mit dem Eigennamen an,
  zwei Zeilen unter der Überschrift, in der derselbe Name steht — die klassische KI-Signatur.
  Jetzt tut das nur noch Michaels Karte. Dazu: Leonardos Karte sagte „wird selten schnell
  fertig" und arbeitete damit gegen unser 24-Stunden-Versprechen; Michaels Rollenzeile brauchte
  302 px bei 292 px Platz und brach dadurch in *jeder* Bildschirmbreite um.
- **Neuer Satz unter der Über-uns-Überschrift**, der beantwortet, wo der Mensch die Maschine
  überstimmt: *„Der erste Entwurf kommt von der KI. Was bei dir ankommt, hat Michael
  durchgesehen — und was ihm nicht passt, schickt er zurück in die Werkstatt."* Kam aus einem
  Zielkunden-Test: Die Sektion löste diese Frage aus und beantwortete sie nicht.
- **Stimmen-Kopf neu getextet.** Der alte Lead erklärte unsere Redaktionsarbeit („Eine davon
  hatte keine Überschrift, da haben wir ihren stärksten Satz nach oben gezogen") — an genau der
  Stelle, an der es endlich mal nicht um uns geht.
- **Hero-Chip „Über 20 Seiten stehen schon" entfernt** (Lennys Entscheidung): Solange wir keine
  Referenzen zeigen, behaupten wir auch keine Zahl.
- **Handwerk:** alle sieben Porträt-`alt`-Texte geleert (ein Screenreader las jeden Namen doppelt
  und hielt die KI-Rollen für Menschen) · am Handy hing die Werkstatt-Ebene ohne Verbindungslinie
  an Klaus · totes CSS raus (`.people` / `.person` / `.ki-team`).

## 📌 Was als Nächstes ansteht

1. **Porträt-Familie angleichen** (der größte offene Punkt). Michaels und Lennys echte Fotos haben
   hellen Küchen-Hintergrund und werden auf dem dunklen Panel zu leuchtenden Scheiben, während die
   fünf KI-Porträts in die Sektion hineinschmelzen. Dazu sind die echten Gesichter im selben Kreis
   etwa doppelt so groß, weil die KI-Bilder Halbfiguren mit Requisiten sind — die der Kreis
   obendrein anschneidet. Der Bruch **Foto vs. Zeichnung** soll bleiben, der ist ehrlich und
   gewollt; **Hintergrund und Aufnahmedistanz** sollten angeglichen werden.
2. **Gründer-Ebene hat keinen Querbalken.** Die Linie zu Klaus startet im Leerraum zwischen den
   beiden Karten, ohne Balken, der Michael und Lenny zusammenführt. Die Werkstatt-Ebene darunter
   hat einen richtigen Verteiler — als Organigramm gelesen sind das zwei Grammatiken.
3. **OG-Tags fehlen auf den drei Rechtsseiten** (Impressum, Datenschutz, AGB).
4. **`ASSETS-LIZENZEN.md` fehlt** — Foto-Rechte-Ampel, vor dem Cutover fällig.
5. **Lighthouse vor dem Cutover neu messen.** Letzte Messung ist vom 12.06., seither sind
   Porträts, Lenis und die Animationen dazugekommen.

## 🙏 Bitte beachten

- **`noindex` bleibt drin**, bis wir gemeinsam live gehen.
- **Ton & Look:** warm, „Du", mit Seele · warm-dunkel „Lagerfeuer" mit Gold/Bernstein — **kein Türkis**.
- **Preis in der AGB muss = Preis auf der Seite sein** (aktuell 790 €).
- **0 externe Requests** — dadurch braucht die Seite keinen Cookie-Banner. Bitte nichts von
  fremden Servern nachladen (keine Google Fonts, kein CDN).
- Rechtsseiten (Impressum, Datenschutz, AGB) sind verlinkt — Texte nicht löschen.
- Details zu Technik und Bewegungs-Effekten stehen in der `CLAUDE.md`.

## 🛟 Wenn was klemmt
`git log` zeigt jede frühere Version, nichts geht verloren. Im Zweifel Claude Code fragen —
er kennt die `CLAUDE.md`.

Viel Spaß beim Bauen! 🔥
