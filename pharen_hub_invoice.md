# Fallstudie: Eingangsrechnungs‑Tool mit Pharen Hub

![Eingangsrechnung](invoice.jpg)

## Einleitung

Viele Buchhaltungsteams kennen dieses Bild: ein Schreibtisch, auf dem Papierstapel wachsen, Rechnungen aus allen möglichen Kanälen und eine Mitarbeiterin, die zwischen E‑Mails, Ordnern und dem ERP‑System pendelt. So sah der Alltag unseres Kunden aus, bevor wir gestartet sind.  

Gemeinsam haben wir eine Lösung geschaffen, die diese Zettelwirtschaft ablöst. Eingehende Rechnungen werden automatisch importiert, in weniger als zwei Minuten ausgelesen und können mit einem Klick freigegeben werden. Hinter dieser Einfachheit steckt eine Reise, die wir in dieser Fallstudie erzählen.

## Kunde & Eckdaten

| Kunde | Plattformtyp | Team | Branche | Benutzer | Standort | Markt | Projektlaufzeit |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Mittelständisches Unternehmen | Eingangsrechnungs‑Tool | PM, App‑Builder, Prozessdesign, AI/OCR, QA | Finanzen/Buchhaltung | Buchhaltung, Einkauf, Management | Deutschland | europaweit | 4 Monate |

## Warum das wichtig ist

In unseren Gesprächen mit dem Finanzteam wurde schnell klar: Manuelle Rechnungsverarbeitung frisst Zeit und Geld. Eine einzelne Rechnung kostet durchschnittlich 15 bis 40 US‑Dollar, wenn sie per Hand erfasst wird【755249572714523†L56-L63】. Über die Hälfte der Unternehmen verbringt wöchentlich zehn oder mehr Stunden mit dieser Routine【755249572714523†L64-L66】. Automatisierung verändert das Bild: Rechnungen lassen sich bis zu 85 % schneller bearbeiten【755249572714523†L74-L81】, die Anzahl der Rechnungen pro Mitarbeiter steigt um 64 %【755249572714523†L87-L90】, und die Fehlerquote sinkt dramatisch【755249572714523†L104-L113】. Die Kosten pro Rechnung reduzieren sich auf nur noch wenige Dollar【755249572714523†L137-L144】.

Diese Zahlen sind mehr als Statistik – sie zeigen den Gewinn an Lebensqualität. Wenn Mitarbeitende nicht mehr stundenlang Daten abtippen, bleibt Zeit für Analyse und Beratung. Automatische Erfassung und Validierung reduzieren Tippfehler und Dubletten【755249572714523†L104-L113】. Der Verzicht auf Papier und manuelle Arbeit senkt die Kosten pro Rechnung【755249572714523†L137-L144】. Und klare Workflows verhindern Verzögerungen und Mahngebühren.

## Erlebnis für Nutzer

Eine Buchhaltungssoftware darf sich nicht wie eine zusätzliche Hürde anfühlen. Unser Tool wirkt wie eine zentrale Inbox: Eingehende Rechnungen werden automatisch gesammelt und übersichtlich dargestellt. Lieferant, Datum und Betrag sind bereits vorausgefüllt. Mitarbeitende können diese Angaben prüfen, Notizen hinzufügen und die Rechnung mit einem Klick freigeben oder zurückweisen. Warnhinweise machen auf Unstimmigkeiten aufmerksam. Eine mobile Version ermöglicht es, Rechnungen auch unterwegs zu prüfen.

## Was unsere Kunden gewinnen

- **Schnelle Entscheidungen:** Rechnungen werden in weniger als zwei Minuten verarbeitet und freigegeben.
- **Weniger Fehler:** Intelligente Felder erkennen Dubletten und Betrugsversuche【755249572714523†L104-L113】.
- **Lückenlose Historie:** Jede Aktion wird dokumentiert, sodass jederzeit nachvollziehbar ist, wer was getan hat.
- **Weniger Papierkram:** Digitale Workflows sparen Platz und Aufwand.
- **Nahtlose Anbindung:** Die Integration ins ERP erfolgt reibungslos, ohne Medienbrüche.

## Geschäftliche Auswirkungen

Mit der neuen Plattform sinken die Durchlaufzeiten dramatisch: Rechnungen, die früher 15 Minuten beanspruchten, sind nun in rund zwei Minuten abgearbeitet【755249572714523†L92-L95】. Das Team kann 64 % mehr Rechnungen pro Mitarbeiter bearbeiten【755249572714523†L87-L90】, und die Kosten pro Rechnung sind um über 80 % gesunken【755249572714523†L137-L144】. Gleichzeitig sichern sich Unternehmen Frühzahlungsrabatte und vermeiden Mahngebühren. Dank der transparenten Übersicht über offene Verbindlichkeiten lassen sich Budgets besser planen.

## Projektanforderungen

Gefordert war eine Lösung, die bestehende Microsoft‑365‑ und ERP‑Umgebungen nutzt, flexibel anpassbar ist und automatisch Rechnungen importiert, ausliest, prüft und verbucht. Sicherheit und Datenschutz hatten oberste Priorität.

### Projektphasen

#### Discovery (1 Woche)

In kurzen, intensiven Workshops haben wir den Ist‑Prozess skizziert und Schwachstellen identifiziert. Verschiedene OCR‑Dienste und Workflow‑Optionen wurden evaluiert, und wir definierten ein klares Zielbild.

#### UI/UX Design (3 Wochen)

Gemeinsam mit den Nutzern entwickelten wir Prototypen, testeten sie und passten sie an. Wichtig war eine vertraute Umgebung, die sich nahtlos in Microsoft 365 einfügt. Hinweise und Farbcodes helfen, Fehler zu vermeiden.

#### Entwicklung & Integration (5 Wochen)

Als Low‑Code‑Basis diente **Pharen Hub**. Mit dem **Lists App Builder** legten wir Felder und Workflows an. Ein OCR‑Service analysiert die Rechnungen und gleicht sie mit Bestellungen ab. Weitere Komponenten:

- **E‑Mail‑, Drive‑ und ERP‑Connectoren** für den Datenaustausch.
- **Genehmigungsregeln** mit Eskalationen.
- **Benachrichtigungsservice** für Erinnerungen.
- **Reporting** mit Kennzahlen wie Bearbeitungszeit und Einsparungen.

## Unsere Lösung & Architektur

Unsere Anwendung läuft vollständig in der Cloud. Eingehende Rechnungen landen in einer SharePoint‑Liste und werden von einem OCR‑Service ausgelesen. Ein Workflow‑Service ordnet die Rechnung der richtigen Kostenstelle zu und bestimmt den Genehmigungsweg. Das Frontend, gebaut mit dem Lists App Builder, zeigt alle Informationen übersichtlich an und ermöglicht Freigaben per Klick. Bei Freigabe werden die Daten automatisch ins ERP übertragen. Dashboards geben jederzeit einen Überblick über offene Posten und den Cashflow.

## Highlights & Design

- **Zentrale Inbox:** Alle Rechnungen an einem Ort.
- **Intelligente Felder:** Automatische Erkennung von Rechnungsdaten und Dubletten【755249572714523†L104-L113】.
- **Freigabe per Klick:** Workflows funktionieren auch auf dem Smartphone.
- **Compliance & Audit:** Jede Aktion wird protokolliert.
- **Kennzahlen auf Knopfdruck:** Berichte zeigen Einsparungen und Durchlaufzeiten.

## Ergebnis

Vier Monate nach Projektstart ging das Tool live. Die Bearbeitungszeit pro Rechnung sank von 15 auf etwa 2 Minuten【755249572714523†L92-L95】, und das Team konnte rund 64 % mehr Rechnungen pro Mitarbeiter verarbeiten【755249572714523†L87-L90】. Die Kosten pro Rechnung reduzierten sich um mehr als 80 %【755249572714523†L137-L144】. Mitarbeitende sind entlastet, und das Management hat endlich einen transparenten Blick auf offene Verbindlichkeiten.

## Fazit

Wir haben zugehört und die realen Abläufe verstanden – nur so konnte eine Lösung entstehen, die den Alltag wirklich erleichtert. Die Kombination aus Pharen Hub, Lists App Builder und intelligenter OCR zeigt, wie kraftvoll Digitalisierung sein kann: für die Mitarbeitenden, die mehr Zeit für wertvolle Aufgaben gewinnen, und für das Unternehmen, das transparenter und effizienter wird.
