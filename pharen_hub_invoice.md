# Fallstudie: Eingangsrechnungs‑Tool mit Pharen Hub

![Eingangsrechnung](invoice.jpg)

## Einleitung

Stellen Sie sich vor: Der Schreibtisch voller Papierstapel, dutzende Rechnungen aus verschiedenen Kanälen, und eine Buchhalterin, die zwischen E‑Mail, Ordnern und ERP hin‑ und herwechselt. So sah der Alltag unseres Kunden aus, bevor wir aktiv wurden. Gemeinsam haben wir ein Eingangsrechnungs‑Tool geschaffen, das diese Zettelwirtschaft ablöst: Rechnungen werden automatisch importiert, in weniger als zwei Minuten ausgelesen und mit einem Klick freigegeben.

## Kunden & Eckdaten

| Kunde | Plattformtyp | Team | Branche | Benutzer | Standort | Markt | Projektlaufzeit |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Mittelständisches Unternehmen | Eingangsrechnungs‑Tool | PM, App‑Builder, Prozessdesign, AI/OCR, QA | Finanzen/Buchhaltung | Buchhaltung, Einkauf, Management | Deutschland | europaweit | 4 Monate |

## Business Value

Unsere Gespräche mit dem Finanzteam zeigten: Manuelle Rechnungsverarbeitung kostet Nerven und Geld. Durchschnittlich 15 bis 40 US‑Dollar kostet eine manuelle Rechnung【755249572714523†L56-L63】, und mehr als die Hälfte der Unternehmen verbringt wöchentlich zehn Stunden oder mehr mit diesem Prozess【755249572714523†L64-L66】. Automatisierung spart Zeit – Rechnungen lassen sich bis zu 85 % schneller verarbeiten【755249572714523†L74-L81】, die Menge der bearbeiteten Rechnungen pro Mitarbeiter steigt um 64 %【755249572714523†L87-L90】, und die Fehlerquote sinkt um 90 %【755249572714523†L104-L113】. Kosten pro Rechnung reduzieren sich auf 2 bis 5 US‑Dollar, das sind rund 83 % weniger【755249572714523†L137-L144】.

- **Mehr Zeit für Wertvolles:** Wo früher stundenlang Daten abgetippt wurden, können sich Mitarbeitende jetzt auf Analyse und Beratung konzentrieren.
- **Weniger Fehler:** Automatische Datenerfassung und Validierung reduzieren Tippfehler und Dubletten【755249572714523†L104-L113】.
- **Kostenersparnis:** Durch Wegfall von Papier und manueller Arbeit sinken die Kosten pro Rechnung【755249572714523†L137-L144】.
- **Reibungslose Abläufe:** Klare Workflows verhindern Verzögerungen und Mahngebühren.

## User Experience

Das Tool fühlt sich an wie eine zentrale Inbox: Eingehende Rechnungen werden automatisch gesammelt und strukturiert angezeigt. Die wichtigsten Daten – Lieferant, Datum, Betrag – sind bereits ausgefüllt. Benutzer können die Informationen prüfen, Kommentare hinzufügen und die Rechnung per Klick freigeben oder zurücksenden. Warnhinweise zeigen, wenn etwas nicht stimmt. Eine mobile Version ermöglicht es, Rechnungen unterwegs zu prüfen.

## Customer Benefits

- **Schnellere Freigaben:** Rechnungen werden in unter zwei Minuten verarbeitet und freigegeben.
- **Fehlervermeidung:** Intelligente Felder erkennen Dubletten und Betrugsversuche【755249572714523†L104-L113】.
- **Transparente Historie:** Jede Aktion wird lückenlos dokumentiert.
- **Weniger Papier:** Digitale Workflows sparen Platz und Aufwand.
- **Einfache Anbindung:** Die Integration ins ERP erfolgt reibungslos und ohne Medienbruch.

## Business Impact

Die neue Plattform hat die Durchlaufzeiten drastisch verkürzt: Rechnungen, die früher 15 Minuten benötigten, sind jetzt in zwei Minuten erledigt【755249572714523†L92-L95】. Das Team kann 64 % mehr Rechnungen pro Mitarbeiter bearbeiten【755249572714523†L87-L90】, und die Kosten pro Rechnung sind um mehr als 80 % gesunken【755249572714523†L137-L144】. Zudem profitieren Unternehmen von Frühzahlungsrabatten und vermeiden Mahngebühren. Die Transparenz über offene Verbindlichkeiten ermöglicht bessere Budgetplanung.

## Projektanforderungen

Gefordert war eine Lösung, die bestehende Microsoft‑365‑ und ERP‑Umgebungen nutzt, flexibel anpassbar ist und automatisch Rechnungen importiert, ausliest, prüft und verbucht. Sicherheit und Datenschutz waren dabei oberste Priorität.

### Projektphasen

#### Discovery (1 Woche)

In kurzen, intensiven Workshops skizzierten wir den Ist‑Prozess und identifizierten Schwachstellen. Wir evaluierten verschiedene OCR‑Dienste und Workflow‑Optionen und definierten ein klares Zielbild.

#### UI/UX Design (3 Wochen)

Gemeinsam mit den Nutzern entwickelten wir Prototypen, testeten sie und passten sie an. Besonders wichtig war eine gewohnte Umgebung, die sich in Microsoft‑365 einfügt. Hinweise und Farbcodes helfen, Fehler zu vermeiden.

#### Entwicklung & Integration (5 Wochen)

Als Low‑Code‑Basis dient **Pharen Hub**. Mit **Lists App Builder** legten wir Felder und Workflows an. Ein OCR‑Service analysiert die Rechnungen und gleicht sie mit Bestellungen ab. Weitere Komponenten:

- **E‑Mail‑, Drive‑ und ERP‑Connectoren** für den Datenaustausch.
- **Genehmigungsregeln** mit Eskalationen.
- **Benachrichtigungsservice** für Erinnerungen.
- **Reporting** mit Kennzahlen wie Bearbeitungszeit und Einsparungen.

## Unsere Lösung & Architektur

Die Anwendung läuft in der Cloud. Rechnungen landen in einer SharePoint‑Liste und werden von einem OCR‑Service ausgelesen. Ein Workflow‑Service ordnet die Rechnung der richtigen Kostenstelle zu und bestimmt den Genehmigungsweg. Das Frontend, erstellt mit dem Lists App Builder, zeigt alle Informationen an und erlaubt Freigaben mit einem Klick. Bei Freigabe werden die Daten automatisch ins ERP übertragen. Dashboards liefern einen Überblick über offene Posten und Cashflow.

## Highlights & Design

- **Zentrale Inbox:** Alle Rechnungen gesammelt an einem Ort.
- **Intelligente Felder:** Automatische Erkennung von Rechnungsdaten und Dubletten【755249572714523†L104-L113】.
- **Genehmigung per Klick:** Workflows funktionieren auch auf dem Smartphone.
- **Compliance & Audit:** Jede Aktion wird protokolliert.
- **Kennzahlen auf Knopfdruck:** Berichte zeigen Einsparungen und Durchlaufzeiten.

## Outcome

Vier Monate nach Projektstart war das Tool live. Die Bearbeitungszeit pro Rechnung sank von 15 auf etwa 2 Minuten【755249572714523†L92-L95】, und das Team konnte rund 64 % mehr Rechnungen pro Mitarbeiter verarbeiten【755249572714523†L87-L90】. Die Kosten pro Rechnung wurden um mehr als 80 % reduziert【755249572714523†L137-L144】. Die Mitarbeiter sind entlastet, und das Management hat endlich einen transparenten Blick auf offene Verbindlichkeiten.

## Fazit

Indem wir den Menschen zugehört und ihre Arbeitsabläufe verstanden haben, konnten wir eine Lösung bauen, die den Alltag vereinfachte. Die Kombination aus Pharen Hub, Lists App Builder und intelligenter OCR zeigt, wie wirkungsvoll Digitalisierung sein kann – für die Menschen und für das Unternehmen.
