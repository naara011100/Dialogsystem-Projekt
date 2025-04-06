# Dialogsysteme – AI-basierter Travel Assistant „JetMate“

## Projektbeschreibung

Dieses Projekt wurde im Rahmen des Moduls **Dialogsysteme** an der FHNW entwickelt und befasst sich mit der Konzeption und Umsetzung eines KI-basierten Kundendienstsystems zur Entlastung interner Supportstrukturen.

Hintergrund des Projekts war die Beobachtung, dass in vielen Organisationen die Menge an Kunden- oder Mitarbeiteranfragen die vorhandenen personellen Ressourcen übersteigt. Lange Antwortzeiten, überlastetes Personal und ineffiziente Abläufe im First-Level-Support sind die Folge. Zudem fehlte in der analysierten Ausgangssituation ein digitaler Kanal, der rund um die Uhr Anfragen bearbeiten kann.

Ziel des Systems war es daher, ein intelligentes Dialogsystem zu entwickeln, das repetitive Anfragen automatisiert verarbeitet und dabei die Servicequalität verbessert. Im Fokus standen:

- **Reduktion der Arbeitslast für Mitarbeitende**
- **Verbesserung der Reaktionsgeschwindigkeit**
- **Einführung eines vollständig digitalen, skalierbaren Systems**

Das entwickelte System adressiert sowohl bestehende Kunden als auch potenzielle Neukunden sowie interne Mitarbeitende, die häufig auf Informationen zugreifen oder administrative Aufgaben erledigen müssen.

Das System ist in eine unternehmensinterne Umgebung eingebettet und wurde für die Integration in webbasierte Plattformen konzipiert. Besondere Aufmerksamkeit wurde auf regulatorische Rahmenbedingungen und die Relevanz klar formulierter, automatisierter Antworten gelegt.


## Use Case – Überblick

- **Problemstellung**: Zu viele Anfragen an menschliche Mitarbeitende, lange Antwortzeiten, fehlendes digitales Servicemodell
- **Ziel**: Automatisierung wiederkehrender Aufgaben, Entlastung des Servicepersonals, Verbesserung der Antwortgeschwindigkeit
- **Zielgruppe**: Bestehende und potenzielle Kunden, interne Mitarbeitende mit regelmäßigem Reisebedarf
- **Kontext**: Integration des Bots in das Intranet zur Bearbeitung von Buchungs- und Ausgabenanfragen in einem unternehmensinternen Umfeld

## Persona

**User Persona – Alex Schneider**  
40 Jahre, Senior Consultant, international tätig. Benötigt schnelle, zuverlässige Informationen über Flugbuchungen, Hotelreservierungen und Spesenregelungen. Erwartet klare Kommunikation, Effizienz und eine stressfreie Nutzererfahrung.

**Bot Persona – JetMate**  
Hilfsbereit, effizient, professionell. Kommuniziert warm, präzise und empathisch. Entwickelt als smarter Reiseassistent, der Informationen konsolidiert und Reiseprozesse vereinfacht.

## Architekturübersicht

- **Datenbedarf**: Die Informationen, die der Bot verarbeitet, stammen aus einer vordefinierten Wissensbasis zu häufig gestellten Fragen rund um Reisen – etwa zu Buchungen, Hoteloptionen, Gepäckrichtlinien oder Visa-Vorgaben.
- **Kanal/Interface**: Das System ist für die Integration in eine öffentliche **Unternehmenswebsite** konzipiert und steht Kund:innen rund um die Uhr zur Verfügung.
- **Framework**: Der Bot wurde mit **Voiceflow** realisiert. Das Tool dient sowohl zur Modellierung der Konversationslogik als auch zur Implementierung einfacher Validierungen (z. B. Datumsprüfung per JavaScript).
- **Aktionen & API**: Der Bot nutzt simulierte API-Endpunkte, um exemplarisch Fluginformationen, Hotelangebote und Reisepakete bereitzustellen. Diese können in einem realen Einsatzszenario mit echten Partner-APIs verbunden werden.

## Technischer Workflow (Voiceflow)

Das konversationelle System wurde vollständig in **Voiceflow** modelliert und implementiert. Der Workflow ist modular aufgebaut und basiert auf einer klaren Trennung zwischen **Kontextsammlung**, **Nutzerpräferenz**, **Validierung**, **API-Integration** und **Antwortlogik**. Die nachfolgenden Prinzipien wurden verfolgt:

### Dialogflussstruktur

1. **Einstieg**: Der Bot begrüsst den Nutzer und bietet sechs Hauptfunktionen an (z. B. Flugbuchung, Hotelreservierung, FAQ).
2. **Intent-Zweig**: Je nach Auswahl des Nutzers wird ein spezialisierter Dialogfluss aktiviert.
3. **Datensammlung**: Abfrage relevanter Daten (z. B. Abflugort, Zielort, Datum, Flugklasse)
4. **Validierung**: Überprüfung der Eingaben (z. B. Check-in vor Check-out, unterschiedliche Städte)
5. **API-Anbindung**: Simulierte GET-Anfragen an externe Dienste zur Buchung von Flügen, Hotels oder Touren
6. **Antwortgenerierung**: Nutzerspezifische Rückmeldung inkl. Zusammenfassung und Bestätigung

### Designentscheidungen

- **Fallbacks**: Jedes Szenario enthält Absicherungen für Fehleingaben
- **Nutzerführung**: Nutzung von Buttons/Choices zur Vereinfachung
- **JavaScript-Logik**: Prüfung von Bedingungen (Datumsformate, Klassenwahl etc.)
- **API-Simulation**: Platzhalter für reale Reise- und Buchungssysteme mit strukturierter Datenübergabe

## Repository-Inhalte

- `docs/` – Use Case, Persona, Architektur, Entscheidungshistorie
- `voiceflow/` – Exportierte .vf-Dateien und Screenshots des vollständigen Flows
- `evaluation/` – Dialogszenarien, Testverläufe, Feedback-Zusammenfassungen
- `README.md` – Diese Datei

## Live-Demo

Eine lauffähige Version des Prototyps wird in der finalen Phase über die Voiceflow-Plattform veröffentlicht. Link zur Instanz:

**[https://creator.voiceflow.com/project/67d8399d16fe20e483bfdc4e/canvas/64dbb6696a8fab0013dba194]**

## Team

- Claudio Vinci
- Daliah Beck
- Naara Rivera

## Lizenz & Rahmen

Dieses Projekt wurde ausschliesslich zu Lehr- und Evaluationszwecken im Rahmen des Moduls *Dialogsysteme* an der FHNW durchgeführt. Eine kommerzielle Nutzung ist ausgeschlossen.
