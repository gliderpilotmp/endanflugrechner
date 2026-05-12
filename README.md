# Endanflugrechner

Ein Endanflugrechner für Segelflieger am Flugplatz **LOXN Wiener Neustadt**. Die App berechnet das tagesaktuelle ECET (End of Civil Evening Twilight) und hilft beim Planen des Heimflugs.

## Funktionen

### ECET-Anzeige
- Automatische Berechnung von Sonnenuntergang und ECET (Sonne bei −6°) für LOXN
- Echtzeit-Countdown mit Fortschrittsbalken und Farbwarnung (grün → orange → rot)
- Anzeige in UTC
- Manuelle Endzeit-Überschreibung möglich (z. B. für spezielle Wettbewerbsregeln)

### Zwei Rechenmodi

**Distanz → Geschwindigkeit**  
Eingabe der Distanz zur Landung in km → Anzeige der erforderlichen Durchschnittsgeschwindigkeit in km/h.

**Geschwindigkeit → Distanz**  
Eingabe der Durchschnittsgeschwindigkeit in km/h → Anzeige der noch erreichbaren Distanz in km.

Beide Modi zeigen zusätzlich die verbleibende Flugzeit und die voraussichtliche Ankunftszeit.

### Weitere Features
- Live-Uhr (Lokalzeit) in der Kopfzeile
- Light / Dark / Auto Theme (gespeichert im Browser)
- Stepper-Buttons (+/−) und Slider für schnelle Eingabe
- Farbcodiertes Ergebnis (grün / gelb / rot) je nach Machbarkeit

## Technik

- **Plattform:** Reines HTML/CSS/JavaScript – keine Frameworks, keine externen Abhängigkeiten
- **PWA:** Installierbar als App auf iOS und Android über den Browser
- **Offline-fähig:** Service Worker cacht alle Assets, die App funktioniert ohne Internetverbindung
- **Sonnenberechnung:** Spencer/Grena-Algorithmus, exakt für LOXN (47.843°N 16.260°E)
- **ECET-Definition:** Sonnenhöhe −6° (bürgerliche Dämmerung), Sonnenuntergang bei −0.83° (Refraktion + Sonnenscheibe)

## Dateien

| Datei | Beschreibung |
|---|---|
| `index.html` | Komplette App (UI + Logik) |
| `sw.js` | Service Worker für Offline-Betrieb und Update-Erkennung |
| `manifest.json` | PWA-Manifest für Installation |
| `icon-192.png` / `icon-512.png` | App-Icons |
| `arcus.png` | Logo (Arcus-Segelflugzeug) |

## Installation als App

Unter Chrome/Edge (Android): Beim Öffnen der Seite erscheint automatisch ein „Installieren"-Button in der Kopfzeile.

Unter Safari (iOS): Seite öffnen → Teilen-Symbol → „Zum Home-Bildschirm".

## Hinweis

Diese App dient ausschließlich zur Flugplanung und ist **keine offizielle Informationsquelle**. Maßgeblich sind stets die offiziellen Tageslimits des Wettbewerbs bzw. der ATC.
