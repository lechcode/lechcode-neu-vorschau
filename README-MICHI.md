# Lechcode-Website — neuer Entwurf, für Michi 👋

Das ist der **neue Stand** der Agentur-Seite (Über-uns als KI-Werkstatt, Funken-Effekt im Hintergrund, Startpreis 790 € …).
Wie bei wairua: jede Seite ist **eine HTML-Datei**, kein Build. So arbeitest du weiter.

## 👀 Anschauen (ohne irgendwas zu installieren)
- **Live-Vorschau** (aktualisiert sich bei jedem Push): https://lechcode.github.io/lechcode-neu-vorschau/
- Oder lokal: Datei **`index.html`** doppelklicken → öffnet im Browser.
- Diese Vorschau ist **noindex** (bei Google unsichtbar) und **nicht** die Live-Seite — an **lechcode.de ändert sich nichts**.

## ✏️ Weiterarbeiten
Wir sind beide im selben **`lechcode`-GitHub-Account** — du hast also vollen Zugriff.
1. **Repo holen** (einmalig):
   ```
   git clone https://github.com/lechcode/lechcode-neu-vorschau.git
   cd lechcode-neu-vorschau
   ```
2. Ordner in **Claude Code** öffnen und sagen, was du möchtest („mach den Hero-Text kürzer …").
   Die `CLAUDE.md` erklärt Claude den Aufbau automatisch.
3. **Prüfen:** `index.html` im Browser neu laden (Cmd/Strg + Shift + R).
4. **Hochladen:**
   ```
   git add -A
   git commit -m "kurz was geändert wurde"
   git push
   ```
   → Die **Vorschau-URL oben aktualisiert sich (~1 Min).** Noch **nicht** live auf lechcode.de.

## 🚀 Live gehen (erst wenn wir beide zufrieden sind)
Das macht **Lenny** in einem Schritt: er schiebt den fertigen Stand ins Live-Repo (`ComingHomeMira/lechcode`) → lechcode.de. Sag ihm einfach Bescheid, wenn es so weit ist.

## 📄 Was in diesem Entwurf neu ist (Stand 23.07.2026)
- **Über uns** als KI-Werkstatt-**Organigramm** (Gründer → Klaus → Werkstatt), langer Text **ausklappbar**, klar als **KI-Team** gekennzeichnet.
- **Funken-Effekt** im Hintergrund der dunklen Abschnitte (dezent, cookiefrei).
- **Startpreis 790 €** überall (inkl. AGB), **kein Plätze-Zähler** mehr.
- **Kundenportal** im 19-€-Pflege-Abo (Änderungen per Chat) + echte **Trustpilot-Stimme** (Anna Sonntag).

## 🙏 Bitte beachten
- **`noindex` bleibt drin**, bis wir gemeinsam live gehen.
- **Ton & Look:** warm, „Du", mit Seele · warm-dunkel „Lagerfeuer" mit Gold/Bernstein — **kein Türkis**.
- Rechtsseiten (Impressum, Datenschutz, AGB) sind verlinkt — Texte nicht löschen; **Preis in der AGB muss = Preis auf der Seite sein** (aktuell 790 €).

## 🛟 Wenn was klemmt
- Versehentlich kaputtgemacht? `git log` zeigt alle Versionen, Claude hilft zurück.
- Im Zweifel **Claude Code fragen** — er kennt die `CLAUDE.md`.

Viel Spaß beim Bauen! 🔥
