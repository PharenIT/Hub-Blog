# Fallstudie: Automatisiertes Verpackungs‑Scanning mit Rust

![Industrieverpackung und Barcode‑Scanner](package_scanner.jpg)

## Einleitung

Wer schon einmal in einer lauten Halle neben dem Förderband stand, weiß: Hier zählt jede Sekunde. Jede kleine Verzögerung entscheidet darüber, wie viele Pakete das Werk verlassen – und ob sie im richtigen Karton ankommen. Vor unserem Projekt bedeutete das, Kartons mit dem Zollstock zu vermessen, Maße zu notieren und im Zweifel auf Verdacht einen größeren Karton zu wählen.  

Als das Produktionsteam uns ansprach, war der Wunsch klar: Ein System, das die Wahl des Kartons so selbstverständlich macht wie der Griff zum Scanner. Paket auflegen, und in weniger als einer halben Sekunde sind die Kontur erfasst, die Maße berechnet und das passende Etikett gedruckt.  

Diese Fallstudie zeigt, wie wir mit Rust und 3D‑Sensoren eine Lösung geschaffen haben, die den Arbeitsalltag spürbar erleichtert.

## Kunde & Eckdaten

| Kunde | Plattformtyp | Team | Branche | Benutzer | Standort | Markt | Projektlaufzeit |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Industrieunternehmen | Desktop-/Mobile-App | PM, Rust Dev, Computer Vision, UI/UX, QA | Produktion | Produktionsmitarbeiter, Logistikteams | Europa | weltweit | 3 Monate |

## Warum es zählt

Beim ersten Rundgang durch das Werk bemerkten wir, wie viel Zeit Mitarbeiter mit Messwerkzeugen und Notizzetteln verbringen. Kartons werden oft auf Verdacht ausgewählt, Verpackungsmaterial verschwendet und Versandkosten steigen. Moderne 3D‑Sensoren können unregelmäßige Pakete jedoch präzise scannen. Sie erfassen Volumen, Höhe, Breite und Länge und helfen dabei, Lager‑ und Transportplatz optimal zu nutzen【375008585752810†L1101-L1106】. Darüber hinaus erkennen sie Beschädigungen und Fehlstellungen, die herkömmliche 2D‑Kameras übersehen【375008585752810†L1108-L1115】.

Die wichtigsten Vorteile auf einen Blick:

- **Tempo:** Jeder Scan dauert weniger als 0,5 Sekunden – eine völlig neue Dimension im Vergleich zum manuellen Messen.
- **Genauigkeit:** 3D‑Sensoren entdecken Dellen und Risse, bevor sie zum Problem werden【375008585752810†L1108-L1115】.
- **Sparpotenzial:** Exakte Maße sparen Verpackungsmaterial und senken das Versandvolumen – Kosten gehen spürbar zurück.
- **Daten als Schatz:** Jeder Scan wird gespeichert und steht für Analysen bereit.

## Erlebnis für Nutzer

Eine industrietaugliche Software muss robust und intuitiv sein. Das war unser Anspruch. Bedienelemente, die sich mit Handschuhen nutzen lassen, klare Farben und große Schrift sorgen dafür, dass jeder Schritt auf einen Blick verständlich ist.  

Das System führt die Mitarbeitenden Schritt für Schritt: Kontur scannen, Maße anzeigen, passende Kartonklasse vorschlagen und das Etikett drucken. Die gleiche Software läuft auch auf Tablets – ideal für mobile Einsätze, etwa beim Wareneingang.

## Was unsere Kunden gewinnen

- **Blitzschnelle Scans:** Die Kontur wird in weniger als einer halben Sekunde erfasst.
- **Korrekte Ergebnisse:** Automatik verhindert falsche Werte und ersetzt handschriftliche Notizen.
- **Höhere Produktivität:** Teams steigern die Paketzahl pro Schicht deutlich.
- **Grundlage für Qualität:** Historische Scanwerte ermöglichen die Optimierung von Prozessen und das Erkennen von Trends.
- **Leicht skalierbar:** Dank der plattformübergreifenden Architektur läuft die App auf verschiedenen Geräten.

## Geschäftliche Auswirkungen

Unsere Lösung hat den Verpackungsprozess grundlegend verändert. Falsch dimensionierte Sendungen sind zur Seltenheit geworden, die Versandkosten sinken und Retouren nehmen ab. Mitarbeitende berichten, dass sie entlastet werden und ihre Zeit sinnvoller nutzen können. Daten fließen direkt ins ERP und stehen dem Controlling jederzeit zur Verfügung.

## Projektanforderungen

Unser Kunde wollte ein System, das verschiedene Kartongrößen und ‑formen schnell erkennt, automatisch die passende Klasse vorschlägt und Etiketten erstellt. Die Anwendung musste offline funktionieren, sich leicht mit dem ERP verbinden lassen und sowohl stationär als auch mobil nutzbar sein.

### Projektphasen

#### Discovery (1 Woche)

Wir verbrachten mehrere Tage im Werk, beobachteten den Verpackungsprozess und sprachen mit den Mitarbeitenden. Gemeinsam identifizierten wir Engpässe und sammelten Anforderungen. Ein 3D‑Scanner erwies sich als ideale Basis, da er unregelmäßige Formen zuverlässig erfasst【375008585752810†L1101-L1106】.

#### UI/UX Design (2 Wochen)

Im Anschluss entwickelten wir Wireframes und interaktive Prototypen. In Feedback‑Runden testeten wir die Konzepte direkt mit den Anwendern. Anpassungen wie größere Buttons oder Farbcodes resultierten aus diesen Gesprächen.

#### Entwicklung & Integration (5 Wochen)

Die Software entstand in Rust. Wir nutzten **Tauri** und **Crux** für die plattformübergreifende Benutzeroberfläche; Tauri erzeugt schlanke, performante Apps【477875218039410†L46-L63】, Crux trennt Kernlogik und UI【932251511387094†L134-L138】【932251511387094†L192-L220】. Weitere Komponenten:

- **OpenCV‑Anbindung** für die Bild‑ und 3D‑Datenverarbeitung.
- **Sensor‑Adapter**, die Daten vom Scanner einlesen.
- **Klassifizierungslogik** für Kartongrößen.
- **Etikettendrucker‑Schnittstelle**.
- **Lokaler Speicher** für Offline‑Betrieb und spätere Synchronisation.

## Unsere Lösung & Architektur

Im Herzen der Anwendung arbeitet ein Rust‑Service, der Sensordaten empfängt, verarbeitet und Ergebnisse bereitstellt. Die UI‑Schicht greift über ein internes API darauf zu. Ereignisse wie „Scan gestartet“ oder „Etikett gedruckt“ werden über einen Event‑Dispatcher weitergegeben. Ist keine Netzwerkverbindung vorhanden, werden die Daten lokal gespeichert und später synchronisiert.

## Highlights & Design

- **Sub‑Sekunden‑Scans:** Jeder Vorgang dauert weniger als eine halbe Sekunde.
- **Qualitätskontrolle inklusive:** Das System erkennt Dellen und Risse【375008585752810†L1108-L1115】.
- **Automatische Größenwahl:** Passende Kartonklassen werden vorgeschlagen.
- **Etikettendruck:** Barcodes werden direkt aufgedruckt.
- **Offlinefähig:** Daten werden gespeichert und später mit dem ERP synchronisiert.
- **Dashboard:** Analyse von Durchlaufzeiten und Fehlern.

## Ergebnis

Dank unserer Lösung arbeiten die Teams schneller und machen weniger Fehler. Verpackungsmaterial wird effizienter genutzt, und die Versandkosten sinken. Kunden melden weniger Beschädigungen und freuen sich über schnellere Lieferungen. Die App ist inzwischen an mehreren Standorten im Einsatz – und die Investition hat sich schnell bezahlt gemacht.

## Fazit

Technologie ist nur ein Werkzeug. Entscheidend ist, zuzuhören und den Alltag der Menschen zu verstehen. Unser Projekt zeigt: Wenn man auf die Nutzer eingeht und die Lösung an ihre Arbeitsweise anpasst, lässt sich mit moderner Software Großes erreichen.
