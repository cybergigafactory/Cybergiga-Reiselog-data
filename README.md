# Cybergiga-Reiselog-data

Öffentliche Daten für die versteckte Seite **Reise-Log** auf cybergigafactory.grok.me (`/reise-log`, nur per Link, kein Navigationsknopf). Die Seite zeigt Rappys Urlaubsfahrt Richtung Holland als dunkle Karte: Strecke in Blau, Supercharger als roter Kreis, Destination-Lader als weißer Kreis, Werte und Bilder pro Stopp.

## Inhalt

| Datei | Was |
|---|---|
| `daten/stops.json` | Stopps der Reise nach Schema version 1 (öffentliche Fassung) |
| `daten/stops.schema.json` | JSON-Schema (Archie) |
| `daten/route.geojson` | Strecke zwischen den Stopps, einmalig über OSRM gebaut |
| `daten/umriss.geojson` | sehr dezente Länderumrisse (Natural Earth 1:50m, Public Domain) |
| `site/index.html` | die Seite als eine HTML-Datei, lädt die Daten oben live von raw.githubusercontent.com und Leaflet 1.9.4 von unpkg (mit SRI) |

## Wer pflegt was

- **Archie** schreibt `stops.json` (Nachtpass erkennt Rappys Reise-Posts auf X, ergänzt Werte aus Screenshots und Rappys Antworten).
- Die Route baut `werkzeuge/route_bauen.py` im Nachtpass nach jedem neuen Stopp.
- **Jarvis** pflegt die Seite (`site/index.html`) und den Abgleich: `werkzeuge/daten_sync.sh` im internen Arbeitsordner baut diese öffentliche Fassung und committet sie. Push nur auf `main`, nie mit Force.

## Datenschutz

- Start und Ziel sind immer Karlsruhe, der echte Ort liegt woanders. Erste und letzte Etappe tragen „(+ ~20 min Datenschutz)“.
- Keine Wohnorte, Hotels oder Unterkünfte. Koordinaten sind Ortsmitten oder öffentliche Ladeorte.
- Keine Live-Position: Ein Stopp erscheint erst, wenn Rappy weitergefahren ist (Abfahrtszeit eingetragen).
- Kilometerstände und interne Notizen sind entfernt.

Route: OSRM, Daten © OpenStreetMap-Mitwirkende (ODbL). Umrisse: Natural Earth. Kein offizielles Angebot von Tesla. Tesla und Supercharger sind Marken der Tesla, Inc.
