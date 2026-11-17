# 18 — Qualitätssicherung, Sicherheit und Performance

## 18.1 Qualitätsverständnis

Qualität umfasst nicht nur den sichtbaren Feature-Erfolg. Datenintegrität, Persistenz, Editorworkflow, Referenzvalidierung, Performance, Stabilität, Bedienbarkeit, Mod-Kompatibilität und nachvollziehbare Fehlerdiagnose sind gleichwertige Bestandteile.

## 18.2 Testebenen

- **Unit-Tests:** Regeln, Berechnungen, Datenvalidierung, Generatorbausteine.
- **Integrationstests:** Verbindungen zwischen Daten, Gameplay, Simulation, Persistenz und Editoren.
- **Systemtests:** vollständige Spiel- und Produktionsabläufe.
- **Editor-Workflowtests:** Erstellen, Bearbeiten, Validieren, Speichern, Laden und Weiterverwenden.
- **Generatortests:** Seed-Reproduzierbarkeit, Grenzkontinuität und Generatorversionen.
- **Savegame-/Migrationstests:** Laden alter Daten, Upgrade, Fehler-/Rollbackverhalten.
- **Performance-Tests:** repräsentative Welt- und Simulationslasten.
- **Moddingtests:** API-Kompatibilität, fehlerhafte Erweiterungen und Konflikte.
- **Spielertests:** tatsächliche Verständlichkeit, Bedienbarkeit und Spielgefühl.

## 18.3 Editor-Definition of Done

Jeder Editor muss anhand eines realistischen Workflows geprüft werden:
1. neuen Datensatz anlegen;
2. alle relevanten Felder bearbeiten;
3. Referenzen verbinden;
4. Vorschau aufrufen;
5. gültigen Datensatz validieren;
6. absichtlich ungültige Daten erzeugen und korrekte Diagnose erhalten;
7. speichern und Editor schließen;
8. Daten erneut laden;
9. in einem zweiten abhängigen Editor verwenden;
10. in Runtime/Build testen;
11. Änderungen vergleichen und dokumentieren.

## 18.4 Weltgenerierungs-QA

Zu testen sind deterministische Wiederholung, Generatorversion, Regionsgrenzen, Wasser-/Terrainkontinuität, Biomverteilung, POI-Erreichbarkeit, Navigationsnetz, Ressourcenverteilung, Siedlungseignung und Performance. Ein späterer Generator darf veröffentlichte Regionsergebnisse nicht ohne kontrollierte Migration überschreiben.

## 18.5 Simulations-QA

NPC-Routinen, Bedürfnisse, Wirtschaft, Tierpopulationen, Zucht, Produktion und Ereignisse müssen bei unterschiedlicher Simulationsstufe konsistente Ergebnisse liefern. Beschleunigte Zeit und Offline-Fortschreibung dürfen keine doppelten Produktionen oder negativen/ungültigen Zustände erzeugen.

## 18.6 Savegame und Datenintegrität

Tests umfassen:
- Speichern in kritischen Zuständen;
- Unterbrechung/Abbruch während des Schreibens;
- Laden nach Versionswechsel;
- fehlende oder verwaiste Referenzen;
- beschädigte Dateien;
- Wiederherstellung und Backup;
- Mod-abhängige Speicherstände;
- Persistenz von Weltveränderungen.

## 18.7 Sicherheit

Zu berücksichtigen sind:
- sichere Verarbeitung importierter Contentdaten;
- Eingabevalidierung und Größenlimits;
- Schutz interner Adminfunktionen und Backend-Geheimnisse;
- Modding-Vertrauensmodell;
- Rechte- und Berechtigungsprüfung;
- sichere Update-/Migrationsprozesse;
- keine sensiblen Zugangsdaten in Repository, Logs oder Builds.

## 18.8 Performance und Skalierbarkeit

Performancebudgets müssen aus Zielhardware und repräsentativen Szenen abgeleitet werden. Zu messen sind CPU, GPU, RAM/VRAM, Streaming-I/O, Speicherallokationen, Draw Calls/Instancing, Animation, Navigation und Simulationskosten.

Optimierungsmöglichkeiten wie LODs, Occlusion, Instancing, Culling, asynchrone Ladeprozesse, Datenaggregation und reduzierte Fernsimulation sind nach Bedarf zu prüfen. Keine einzelne Technik wird ohne Profiling pauschal als Lösung vorgeschrieben.

## 18.9 Ehrliche Testberichterstattung

Ein Testbericht muss Testumgebung, Version, Schritte, erwartetes und tatsächliches Ergebnis, Status sowie bekannte Einschränkungen nennen. Nicht ausgeführte Tests werden als „nicht ausgeführt“ markiert. Ein erfolgreicher Build ist kein Nachweis, dass ein Feature im Spiel korrekt funktioniert.

## 18.10 Fehlerpriorität

- **Blocker:** Datenverlust, Sicherheitsproblem, nicht startbares Spiel oder zerstörte Kernfunktion.
- **Kritisch:** zentraler Gameplay-/Save-/World-Ausfall.
- **Hoch:** wesentlicher Workflow oder wiederkehrende erhebliche Fehlfunktion.
- **Mittel:** begrenzte Funktionseinschränkung mit Workaround.
- **Niedrig:** kosmetischer oder selten auftretender Fehler.

Die konkrete Klassifizierung ist pro Projektprozess zu verfeinern.
