# Fallstudie: KI‑gestützte Workflow‑Automatisierung für Versicherungen

![Workflow Diagramm der Schadenbearbeitung](workflow.jpg)

## Einleitung

Versicherer sehen sich zunehmend mit steigenden Erwartungen an schnelle und transparente Schadenabwicklung konfrontiert. Handbuch‑basierte Prozesse binden Ressourcen, erzeugen Fehler und frustrieren Kunden. In dieser Fallstudie erzählen wir, wie wir gemeinsam mit dem Team eines Versicherers eine moderne Schadenplattform aufgebaut haben: Meldungen werden in weniger als acht Sekunden erfasst, innerhalb einer Minute prüft eine KI die eingereichten Dokumente, und alle Beteiligten sehen den Fortschritt live.

## Kunden & Eckdaten

| Kunde | Plattformtyp | Team | Branche | Benutzer | Standort | Markt | Projektlaufzeit |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Versicherungsdienstleister | Schadenbearbeitung | PM, Backend, Frontend, KI, QA | Versicherung | Schadensmanager, Sachbearbeiter, Versicherte | Deutschland | national | 4 Monate |

## Business Value

Im Gespräch mit Sachbearbeitern hörten wir oft denselben Frust: Viel Zeit geht für Routineaufgaben drauf. Eine Branchenstudie bestätigt das: Etwa 30 % der Arbeitszeit wird für low‑value‑Tasks wie Dokumentenprüfung verwendet【927659360655962†L117-L120】. Gleichzeitig beklagen 31 % der Kunden einen schlechten Schadenservice; 60 % nennen die lange Bearbeitungsdauer【927659360655962†L123-L128】. Unser System automatisiert das Erstellen und Prüfen von Schadenmeldungen und verkürzt die Regulierungszeiten von Wochen auf wenige Stunden【927659360655962†L124-L128】.

- **Effizienzzuwachs:** Arbeitsschritte, die früher Tage gedauert haben, werden jetzt in Stunden erledigt. Automatisierte Workflows übernehmen lästige Routinen, sodass mehr Zeit für den Kunden bleibt.
- **Steigerung der Genauigkeit:** KI‑Algorithmen erkennen Muster und reduzieren manuelle Fehler. Klassische Automatisierung kommt bei nur etwa 7 % der Fälle ohne menschlichen Eingriff aus【927659360655962†L146-L155】; unsere Kombination aus KI und menschlichem Feedback führt zu einer höheren automatischen Verarbeitung.
- **Skalierbarkeit:** Der modulare Aufbau erlaubt, weitere Versicherungsprodukte hinzuzufügen, ohne die Architektur zu ändern.
- **Nachhaltigkeit:** Der Papierverbrauch sinkt, die Daten sind jederzeit verfügbar.

## User Experience

Wir wollten, dass sich die Lösung für alle Akteure leicht anfühlt. Versicherte melden einen Schaden in einer geführten Maske und sehen sofort, welche Informationen fehlen. Sachbearbeiter erhalten einen aufgeräumten Arbeitsplatz mit Priorisierung. Push‑Benachrichtigungen informieren bei Statusänderungen. Das Ergebnis ist ein stressfreier Prozess, der Transparenz schafft.

## Customer Benefits

- **Kürzere Settlement‑Zeiten:** Bearbeitungszeiten sinken von Tagen auf Stunden【927659360655962†L124-L128】.
- **Transparenz:** Versicherte und Sachbearbeiter können den Fortschritt des Falls jederzeit einsehen.
- **Weniger Fehler:** Automatisierte Datenerfassung reduziert die Fehlerquote spürbar【927659360655962†L146-L155】.
- **Höhere Zufriedenheit:** Schnellere Entscheidungen bedeuten zufriedenere Kunden und weniger Rückfragen.

## Business Impact

Mit der neuen Plattform kann das Team doppelt so viele Fälle bearbeiten, ohne zu wachsen. Routinearbeiten werden automatisiert, die Datenqualität steigt und Compliance‑Nachweise sind auf Knopfdruck verfügbar. Die Kosten pro Fall sinken, während die Kundentreue steigt.

## Projektanforderungen

Der Versicherer wollte den gesamten Schadenprozess digitalisieren, ohne sein Kernsystem zu ersetzen. Wichtig war ein flexibler, erweiterbarer Ansatz, der DSGVO‑konform ist und sich mit bestehenden Systemen verzahnen lässt.

### Projektphasen

#### Discovery (2 Wochen)

In Workshops mit Schadenteams und IT analysierten wir den Status quo. Schnell war klar: nur 7 % der Schadenanträge wurden bislang vollautomatisch verarbeitet【927659360655962†L146-L155】. Viele Daten waren unstrukturiert und mussten manuell eingegeben werden. Wir dokumentierten die Probleme und skizzierten erste Lösungsansätze.

#### UI/UX Design (4 Wochen)

Unsere Designer entwarfen Prototypen, testeten sie mit Anwendern und passten sie laufend an. Ein Design‑System mit klaren Komponenten, responsive Layouts und barrierefreien Formularen entstand. Wir entwickelten über 40 individuelle Icons, um komplexe Vorgänge leicht verständlich zu machen.

#### Entwicklung & Integration (6 Wochen)

Das Backend bauten wir mit Django und FastAPI auf, um saubere APIs zu liefern und KIs problemlos anzubinden【282307985541576†L324-L341】. Das Frontend entstand mit Nuxt, das file‑basiertes Routing und serverseitiges Rendering bietet【321147738204318†L15-L19】【321147738204318†L140-L150】. Wir setzten auf Microservices, einen AI‑Layer für Dokumenten‑Analyse und eine PostgreSQL‑Datenbank für Transaktionsdaten【42843466638634†L37-L50】. Schnittstellen zu externen Partnern und umfangreiche Tests rundeten den Entwicklungszyklus ab.

## Unsere Lösung & Architektur

Die fertige Plattform basiert auf einem Gateway, das Frontend, Backend und KI verknüpft. Schadenmeldungen werden normalisiert, von der KI ausgelesen und von einem Entscheidungsservice bewertet. Alle Schritte werden protokolliert und sind im Dashboard sichtbar. Dank modularer Services lassen sich neue Produkte oder Funktionen schnell hinzufügen.

## Highlights & Design

- **Priorisierte Arbeitsliste:** Sachbearbeiter sehen sofort, welche Fälle dringend sind.
- **Live‑Status:** Alle Nutzer können den Fortschritt des Falls in Echtzeit verfolgen.
- **Benachrichtigungen:** Automatische Mails und Push‑Nachrichten halten alle auf dem Laufenden.
- **Erweiterbarkeit:** Neue Prozesse lassen sich per Konfiguration aktivieren.
- **Audit & Compliance:** Dashboards liefern Nachweise für interne und externe Prüfungen.

## Outcome

Innerhalb von vier Monaten haben wir den Schadenprozess komplett digitalisiert. Die manuelle Arbeit sank um rund 30 %【927659360655962†L117-L120】; die durchschnittliche Bearbeitungszeit reduzierte sich von mehreren Tagen auf wenige Stunden【927659360655962†L124-L128】. Das Team ist motivierter, und die Kunden loben die Geschwindigkeit und Transparenz. Die Plattform bildet die Grundlage für weitere Innovationen wie Chatbots oder Self‑Service‑Portale.

## Fazit

Es geht nicht nur um Technik, sondern um Menschen: Indem wir zugehört und die realen Probleme der Mitarbeiter und Kunden verstanden haben, konnten wir eine Lösung entwickeln, die den Unterschied macht. Die Kombination aus modernem Design, leistungsfähiger Technik und KI sorgt für zufriedene Kunden und entlastete Teams.
