# 02 — Designprinzipien und Leitplanken

## 2.1 Verbindliche Arbeitsgrundsätze

### Vollständigkeit vor Schein-Fertigstellung
Ein System gilt erst dann als umgesetzt, wenn Datenmodell, Bedienablauf, Validierung, Persistenz, Laufzeitintegration, Fehlerbehandlung, Tests und Dokumentation vorhanden sind. Ein Editorfenster mit einigen Buttons ist kein fertiger Editor.

### Durchgängige Integration
Ein NPC aus dem NPC-Editor muss in einer Siedlung wohnen, einen Beruf ausüben, Beziehungen besitzen, auf Quests referenzierbar sein und in der Simulation korrekt behandelt werden. Ein Gebäude aus dem Building Editor muss im Settlement-/World-Kontext platziert werden können, Navigation berücksichtigen und mit Wirtschaft bzw. Interaktionen verbunden sein.

### Gemeinsame Daten statt Insellösungen
Editoren und Runtime-Systeme verwenden gemeinsame kanonische Datenmodelle, stabile IDs und explizite Referenzen. Kopien derselben Definition in mehreren Editoren sind zu vermeiden. Spezialisierte Profile dürfen unterschiedliche Inhalte und Regeln besitzen, sollen aber gemeinsame Grundlagen nutzen.

### Determinismus und Nachvollziehbarkeit
Prozedurale Systeme verwenden kontrollierte Seeds und dokumentierte Generatorversionen. Änderungen sollen reproduzierbar sein. Bereits veröffentlichte Regionen dürfen nicht unbeabsichtigt durch spätere Generatoränderungen umgestaltet werden.

### Konsequenzen statt bloßer Kulisse
Wirtschaftliche, ökologische, soziale und erzählerische Aktionen sollen in verbundenen Systemen nachvollziehbare Auswirkungen erzeugen. Auswirkungen dürfen skaliert simuliert werden, müssen aber konsistent sein.

### Spielerautonomie
Die Geschichte darf den Spieler führen, aber seine Entscheidungen nicht vollständig entwerten. Vaelith kann beraten, widersprechen und provozieren, darf jedoch nicht die Entscheidungen des Spielers ersetzen.

## 2.2 Erhalt bestehender Projektinhalte

Vor jeder Konsolidierung oder Migration vorhandener Inhalte ist ein Inventar der Originalquellen anzulegen. Zu erhalten sind – soweit vorhanden – Namen, Begriffe, Definitionen, JSON-Strukturen, IDs, Kategorien, Attribute, Verknüpfungen, Kataloge, Questlogik, wirtschaftliche Regeln und Monetarisierungsideen.

Technische Anpassungen an Unity/3D sind zulässig und notwendig, dürfen aber keine inhaltliche Löschung verschleiern. Für jede Änderung ist zu protokollieren:
- Quelle und ursprüngliche Bezeichnung/Struktur.
- Änderungstyp: umbenennen, verschieben, ergänzen, bearbeiten, ersetzen, aufteilen oder löschen.
- Begründung und technische bzw. spielerische Auswirkung.
- Zielstruktur und Migrationsregel.
- Umgang mit bestehenden IDs und Referenzen.

Nicht vorliegende Quelldaten werden als Quellenlücke markiert. Sie werden nicht durch plausibel klingende Vermutungen ersetzt.

## 2.3 Keine stillen Festlegungen

Zahlen und technische Parameter, die noch nicht ausdrücklich entschieden sind, bleiben konfigurierbar oder als offen markiert. Beispiele sind Weltmaßstab, Kartenauflösung, Region-/Chunkgröße, Biomenliste, Schwierigkeitsstufen, Simulationsintervalle, Zielplattformen und konkrete Performancebudgets.

## 2.4 Wissenschafts-Fantasy-Arbeitsrichtung

Die aktuell erwogene Science-Fantasy-Ausrichtung soll vielfältige Kulturen und Entwicklungsstände ermöglichen: futuristische Städte, technologisch fortgeschrittene Gesellschaften, primitive oder traditionell organisierte Gemeinschaften, uralte Ruinen und magische Orte können koexistieren, wenn Weltgeschichte und Kultur dies plausibel erklären. Das Setting darf nicht zu einem reinen Science-Fiction-Shooter werden. Magie, Mystik, Abenteuer und fantastische Kreaturen bleiben wesentliche Bestandteile.

## 2.5 Trennung von Identität, Gefahr und Fortschritt

- Ein Biom beschreibt ökologische und geografische Eigenschaften.
- Gefahr beschreibt Risiken durch Kreaturen, Fraktionen, Umwelt und Ereignisse.
- Schwierigkeit beschreibt die erwartete Herausforderung bzw. Skalierung.
- Spielerfortschritt und Questfreischaltungen sind davon getrennte Zustände.

Ein Wald ist daher nicht automatisch gefährlich oder hochstufig. Ein friedliches Gebiet kann gefährliche Ereignisse erleben; ein gefährliches Gebiet kann verschiedene Biome enthalten.

## 2.6 Entscheidungen und Prioritäten

Bei Konflikten ist nicht automatisch die technisch bequemste Lösung richtig. Die Lösung muss Spielvision, Datenbestand, Wartbarkeit, Performance und Benutzererlebnis berücksichtigen. Claude soll Lücken und Konflikte sichtbar machen, priorisierte Empfehlungen aussprechen und innerhalb des genehmigten Umfangs entscheiden. Grundlegende Richtungsänderungen bleiben Sache der Projektleitung.
