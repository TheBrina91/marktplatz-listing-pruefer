# Marktplatz-Listing-Prüfer

Ein Web-Tool, das Produktdaten vor dem Upload auf Marktplätze wie Amazon, Kaufland, eBay oder WooCommerce prüft. Es läuft direkt im Browser, ohne Installation.

**➡️ Live ausprobieren:** [thebrina91.github.io/marktplatz-listing-pruefer](https://thebrina91.github.io/marktplatz-listing-pruefer/)

## Was das Tool prüft

| Feld | Prüfung |
|---|---|
| **Produkttitel** | Länge (ideal 40–80 Zeichen), Werbewörter wie „versandkostenfrei“ oder „Bestseller“, Sonderzeichen `! ? €`, Wörter in GROSSBUCHSTABEN (Abkürzungen wie IP54, LED, USB sind erlaubt) |
| **EAN / GTIN-13** | Erkennt interne Artikelnummern (SKU), prüft die Länge und rechnet die GS1-Prüfziffer nach. Bei einem Tippfehler zeigt es die richtige Prüfziffer an. |
| **Bulletpoints** | Mindestens 3 Punkte, jeder höchstens 200 Zeichen |
| **Preis** | Gültige Zahl größer als 0 |

## Ergebnis

- **Listing Health Score** von 0 bis 100 % mit Ampel: Upload-bereit, Optimierung nötig oder Upload wird abgelehnt
- **Smartphone-Vorschau**, so wie das Angebot in einer Marktplatz-App aussehen würde, inklusive EAN-13-Strichcode
- **HTML-Export** der Bulletpoints als `<ul><li>` zum Kopieren in das Beschreibungsfeld

## Schnelltest

Oben im Tool gibt es zwei Knöpfe:
- **✅ Perfektes Beispiel laden**: ein sauberes Listing mit 100 %
- **❌ Fehler-Beispiel laden**: ein Listing voller typischer Fehler

## So rechnet die EAN-Prüfung

Die ersten 12 Ziffern werden abwechselnd mit 1 und 3 multipliziert und addiert. Die Prüfziffer ist der Wert, der die Summe auf den nächsten Zehner auffüllt.

Beispiel `401234567890?`: Summe = 89 → (10 − 9) mod 10 = **1** → gültige EAN `4012345678901`

Hinweis: Die Prüfziffer findet Tippfehler. Ob eine EAN bei GS1 registriert ist, prüft erst der Marktplatz.

## Technik

- Eine einzige Datei: `index.html` mit HTML, CSS und JavaScript
- Keine Bibliotheken, keine Daten werden gesendet, alles läuft lokal im Browser
- Hell- und Dunkelmodus, funktioniert auf Handy und Desktop

## Hintergrund

Ich bin Kauffrau im E-Commerce mit Schwerpunkt Produktdatenpflege und Marktplatzanbindung. Das Tool bildet Prüfungen ab, die ich aus der täglichen Arbeit mit Kaufland, eBay und WooCommerce kenne.

**Sabrina Preuß** · Dortmund
