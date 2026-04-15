# Fallstudie: Automatisiertes Verpackungs‑Scanning mit Rust

![Industrieverpackung und Barcode‑Scanner](package_scanner.jpg)

## Einleitung

Auf dem Fabrikboden tickt die Uhr. Jede Sekunde entscheidet darüber, wie viele Pakete versendet werden können und ob die richtigen Kartons verwendet werden. Wir wurden gebeten, ein System zu bauen, das die Kartonwahl so einfach macht wie ein Handgriff: Paket auflegen, zack – in weniger als einer halben Sekunde ist die Kontur erfasst, die Maße berechnet und das passende Etikett gedruckt.

## Kunden & Eckdaten

| Kunde | Plattformtyp | Team | Branche | Benutzer | Standort | Markt | Projektlaufzeit |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Industrieunternehmen | Desktop-/Mobile-App | PM, Rust Dev, Computer Vision, UI/UX, QA | Produktion | Produktionsmitarbeiter, Logistikteams | Europa | weltweit | 3 Monate |

## Business Value

Beim Rundgang durch das Werk stellten wir fest: Viele Mitarbeiter vermessen Kartons von Hand, notieren Zahlen auf Zetteln und wählen oft zu große Verpackungen. Das verschwendet Material, führt zu höheren Versandkosten und kostet Zeit. Mit modernen 3D‑Sensoren lassen sich unregelmäßig geformte Pakete exakt scannen, Abmessungen wie Volumen, Höhe, Breite und Länge werden erfasst und helfen, Lager- und Transportplatz zu optimieren【375008585752810†L1101-L1106】. Sie erkennen zudem Beschädigungen und Fehlstellungen, die mit klassischen 2D‑Kameras nicht sichtbar sind【375008585752810†L1108-L1115】.

- **Schnelligkeit:** Der Vorgang dauert weniger als 0,5 Sekunden – kein Vergleich zum manuellen Messen.
- **Qualität:** 3D‑Sensoren erkennen Dellen oder Risse【375008585752810†L1108-L1115】.
- **Kostenersparnis:** Exakte Maße reduzieren Verpackungsmaterial und Versandvolumen, wodurch sich Kosten spürbar senken lassen.
- **Datentransparenz:** Jeder Scan wird gespeichert und kann für Analysen genutzt werden.

## User Experience

Die Anwendung ist so gestaltet, dass sie auch unter industriellen Bedingungen funktioniert. Mit Handschuhen bedienbare Schaltflächen, klare Farben und große Schrift stellen sicher, dass man den Prozess auf einen Blick versteht. Das System führt die Nutzer Schritt für Schritt durch die Stationen: Kontur scannen, Maße anzeigen, Kartonklasse vorschlagen und Etikett drucken. Auf dem Tablet läuft dieselbe Software für mobile Einsätze, etwa beim Wareneingang.

## Customer Benefits

- **Blitzschnelles Scannen:** Die Kontur wird in weniger als 0,5 Sekunden erfasst.
- **Fehlerfreie Messungen:** Die Automatik verhindert falsche Werte und macht handschriftliche Notizen überflüssig.
- **Mehr Pakete pro Schicht:** Teams können ihre Produktivität deutlich steigern.
- **Daten für Qualitätskontrolle:** Historische Scanwerte helfen, Prozesse zu optimieren und Trends zu erkennen.
- **Einfache Skalierung:** Durch die plattformübergreifende Architektur kann die App auf verschiedenen Geräten laufen.

## Business Impact

Die automatisierte Lösung hat den Verpackungsprozess revolutioniert: Falsch dimensionierte Sendungen sind zur Ausnahme geworden, Versandkosten sinken und Retouren verringern sich. Die Mitarbeiter schätzen die Entlastung und können ihre Zeit besser nutzen. Daten werden direkt ins ERP übernommen und stehen dem Controlling zur Verfügung.

## Projektanforderungen

Der Kunde wünschte sich ein schnelles, zuverlässiges System, das Kartons verschiedener Größen und Formen erkennt, automatisch die passende Klasse auswählt und Etiketten erstellt. Die App sollte offline funktionieren, sich einfach mit dem ERP verbinden lassen und sowohl am stationären Arbeitsplatz als auch mobil einsetzbar sein.

### Projektphasen

#### Discovery (1 Woche)

Wir verbrachten einige Tage im Werk, beobachteten den Verpackungsprozess und sprachen mit den Mitarbeitenden. Gemeinsam identifizierten wir Engpässe und sammelten Anforderungen. Ein 3D‑Scanner schien ideal, da er unregelmäßige Formen zuverlässig erfasst【375008585752810†L1101-L1106】.

#### UI/UX Design (2 Wochen)

Anschließend entwickelten wir Wireframes und interaktive Prototypen. In Feedback‑Runden testeten wir die Konzepte direkt mit den Anwendern. Anpassungen wie größere Buttons oder Farbcodierungen entstanden aus diesen Gesprächen.

#### Entwicklung & Integration (5 Wochen)

Die Software entstand in Rust. Wir nutzen **Tauri** und **Crux** für die plattformübergreifende UI; Tauri erzeugt schlanke, performante Apps【477875218039410†L46-L63】, Crux trennt die Kernlogik von der Benutzeroberfläche【932251511387094†L134-L138】【932251511387094†L192-L220】. Zusätzlich integrierten wir:

- Eine **OpenCV**‑Anbindung für die Bild‑ und 3D‑Datenverarbeitung.
- **Sensor‑Adapter**, die Daten vom Scanner einlesen.
- **Klassifizierungslogik** für Kartongrößen.
- **Etikettendrucker‑Schnittstelle**.
- **Local Storage** für Offline‑Betrieb und spätere Synchronisation.

## Unsere Lösung & Architektur

Der Kern unserer Anwendung ist ein Rust‑Service, der Sensordaten empfängt, verarbeitet und Ergebnisse bereitstellt. Die UI‑Schicht greift über ein internes API darauf zu. Ereignisse wie "Scan gestartet" oder "Etikett gedruckt" werden über einen Event‑Dispatcher weitergegeben. Wenn keine Netzwerkverbindung besteht, werden Daten lokal gespeichert und später synchronisiert.

## Highlights & Design

- **Sekundenbruchteile pro Scan:** Jeder Vorgang ist in weniger als 0,5 Sekunden abgeschlossen.
- **Qualitätskontrolle inklusive:** Dellen und Risse werden erkannt【375008585752810†L1108-L1115】.
- **Automatische Größenwahl:** Die passende Kartonklasse wird vorgeschlagen.
- **Etikettenerstellung:** Integrierter Druck mit Barcode.
- **Offlinefunktionen:** Speichern und späteres Synchronisieren mit dem ERP.
- **Dashboard:** Analyse von Durchlaufzeiten und Fehlern.

## Outcome

Dank der Lösung arbeiten die Teams schneller und machen weniger Fehler. Verpackungsmaterial wird effizienter genutzt, und die Versandkosten sinken. Kundenberichte zeigen weniger Beschädigungen und eine schnellere Lieferung. Die App wird inzwischen an mehreren Standorten eingesetzt, und die Investition hat sich schnell amortisiert.

## Fazit

Technik allein löst keine Probleme – wichtig ist das Verständnis für den Alltag der Menschen. Unser Projekt beweist: Wenn man den Nutzern zuhört und die Lösung an ihre Arbeitsweise anpasst, lässt sich mit moderner Software viel erreichen.
