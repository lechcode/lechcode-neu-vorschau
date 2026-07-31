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

## 🎬 Das Video austauschen (für Lenny)

⚠️ **Das geht NICHT über die GitHub-Weboberfläche.** Der Web-Uploader nimmt maximal 25 MB,
unser Video (`assets/lechcode-video.mp4`) wiegt aktuell **87 MB**. Also über Weg B:

```bash
git pull --rebase
# neue Datei nach assets/lechcode-video.mp4 kopieren (gleicher Name = sonst nichts zu tun)
git add assets/lechcode-video.mp4
git commit -m "Neues Video"
git push
```

Drei Dinge dazu:
- **Poster-Bild nicht vergessen:** `assets/video-poster.jpg` ist das Standbild vor dem Klick.
  Passt es nicht mehr zum neuen Video, gleich mit austauschen.
- **Bitte kleiner exportieren als das alte:** 1080p, H.264, `-movflags +faststart`, Ziel **10–15 MB**.
  Die 87 MB machen fast das ganze Repo aus und laden auf dem Handy quälend lang — auf einer
  Seite, die „schnell auf jedem Gerät" verspricht.
- **Untertitel:** Die Einbaustelle steht als Kommentar direkt am `<video>`-Element. Wenn eine
  deutsche `.vtt` vorliegt, dort die `<track>`-Zeile einkommentieren. Das ist aktuell die einzige
  bekannte Barrierefreiheits-Lücke der Seite.

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

## 📄 Was drinsteht (Stand 28.07.2026)

- **Angebot:** komplette Website einmalig **790 €**, wirklich alles inklusive.
  **Kein 19-€-Abo mehr** — danach null laufende Kosten, Hosting und Domain tragen wir.
  Änderungen unbegrenzt über das Dashboard oder per Nachricht.
- **Über uns** als KI-Werkstatt-Organigramm: wir beide plus fünf klar gekennzeichnete KI-Rollen.
  Auf Desktop aufgeklappt, am Handy zugeklappt.
- **Stimmen** als Slider mit drei echten Bewertungen (Emily und Anna von Trustpilot, C. M. von Google).
- **Sprach-Runde 28.07.:** Texte komplett auf „menschlich statt KI" überarbeitet, vom KI-Team
  in vier Runden durchlaufen und abgenommen.

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
