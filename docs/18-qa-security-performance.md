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

## 18.11 Teststrategie und risikobasierte Abdeckung

Testaufwand richtet sich nach Auswirkung und Änderungsrisiko. Besonders kritisch sind Persistenz, Weltgenerierung, Migration, systemübergreifende Transaktionen, Modding und veröffentlichte Inhalte.

Jede wesentliche Änderung benötigt:
- klaren Umfang und betroffene Systeme;
- reproduzierbare Testdaten und Voraussetzungen;
- erwartete Ergebnisse und Grenzfälle;
- automatisierte Tests, soweit sinnvoll;
- manuelle Funktions- und Sichtprüfung;
- dokumentierte Einschränkungen und offene Fehler.

Eine hohe Testanzahl ersetzt keine fachliche Abdeckung. Tests müssen reale Fehlerbilder und abhängige Systeme berücksichtigen.

## 18.12 Regression und Kompatibilität

Für zentrale Workflows sind Regressionstests vorzusehen. Dazu gehören Start/Neustart, Save/Load, Regionswechsel, Questfortschritt, Inventar-/Itemzustände, Produktion, Zucht, Editorimport, Mod-Laden und Weltgenerierung.

Änderungen an Schemas, Generatoren, API-Verträgen oder Assets benötigen gezielte Kompatibilitätstests. Bestehende veröffentlichte Inhalte und repräsentative ältere Spielstände sind in die Testmatrix aufzunehmen.

## 18.13 Fehler- und Vorfallmanagement

Fehlerberichte benötigen eindeutige Kennung, Schweregrad, betroffene Version, Umgebung, Reproduktionsschritte, erwartetes/tatsächliches Verhalten, Logs und Auswirkungen auf Daten.

Bei Datenverlust, Sicherheitsvorfällen oder beschädigten Spielständen ist zunächst der betroffene Prozess zu sichern und die Ursache einzugrenzen. Korrekturen müssen Wiederherstellung und Regressionstests enthalten. Fehler dürfen nicht durch stilles Löschen betroffener Daten kaschiert werden.

## 18.14 Sicherheitsgrenzen und Bedrohungsmodell

Sicherheitsprüfungen sollen Angriffsflächen und Vertrauensgrenzen benennen. Zu berücksichtigen sind importierte Daten, Mods, Savegames, Updatepakete, lokale Dateien, Web-/Backend-Verbindungen und interne Editorfunktionen.

Für jede relevante Grenze sind Schutzbedarf, Eingabevalidierung, Rechte, Fehlerverhalten und Protokollierung zu dokumentieren. Das Bedrohungsmodell wird mit neuen Funktionen aktualisiert; eine einmalige Prüfung reicht nicht.

## 18.15 Sichere Daten- und Dateiverarbeitung

Importe und Spielstände sind als nicht vertrauenswürdige Eingaben zu behandeln. Zu prüfen sind:
- Dateigrößen- und Mengenlimits;
- Pfadmanipulation und unerlaubte Dateizugriffe;
- fehlerhafte oder rekursive Datenstrukturen;
- ungültige IDs und Referenzen;
- Parser-/Deserialisierungsfehler;
- Ressourcenerschöpfung durch übergroße Inhalte;
- sichere temporäre Dateien und atomare Schreibvorgänge.

Fehlerhafte Eingaben müssen kontrolliert abgewiesen werden. Diagnosemeldungen dürfen keine Geheimnisse oder vollständigen sensiblen lokalen Pfade unnötig offenlegen.

## 18.16 Modding-Sicherheitsprüfung

Datenmods und ausführbare Code-Mods benötigen getrennte Prüf- und Vertrauensmodelle. Datenmods werden strikt validiert und auf Ressourcen-/Referenzgrenzen geprüft. Code-Mods laufen im Prozess und sind als privilegierter Code zu behandeln.

Tests müssen unter anderem fehlerhafte Plugins, absichtliche Konflikte, übermäßige Ressourcenverwendung, Lade-/Shutdownfehler und Auswirkungen auf Savegames berücksichtigen. Die API darf keine Sandboxwirkung versprechen, die technisch nicht existiert.

## 18.17 Performance-Budgets und Messmethodik

Budgets werden anhand definierter Zielhardware und repräsentativer Spielsituationen festgelegt. Messungen benötigen reproduzierbare Szenen, Builds, Einstellungen und Laufzeiten. Durchschnittswerte allein reichen nicht; Spitzen, Stottern und Ladezeiten sind ebenfalls zu betrachten.

Zu erfassen sind mindestens:
- CPU-/GPU-Zeit und Framezeitverteilung;
- RAM, VRAM und Speicherallokationen;
- Streaming- und Savegame-I/O;
- Simulationskosten nach Relevanzstufe;
- NPC-/Kreaturen-/Animationslast;
- Rendering, Draw Calls und Materialwechsel;
- Lade-, Wechsel- und Wiederherstellungszeiten.

## 18.18 Skalierungs- und Belastungstests

Testwelten müssen steigende Belastungsszenarien enthalten: viele NPCs, Kreaturen, Gebäude, Produktionsketten, aktive Ereignisse, große Sichtweiten und häufige Regionswechsel.

Belastungstests sollen Engpässe sichtbar machen und Grenzverhalten prüfen. Optimierungen müssen gegen dieselben Szenarien gemessen werden. Unbelegte Performanceversprechen oder rein theoretische Skalierbarkeit gelten nicht als Nachweis.

## 18.19 Release-Gates und Abnahme

Ein Releasekandidat benötigt definierte Freigabekriterien für Startfähigkeit, Kernspielabläufe, Savegameintegrität, kritische Fehler, Plattformkompatibilität, Assetrechte, Moddinghinweise und Performance.

Blocker und kritische Fehler verhindern die Freigabe, sofern keine ausdrücklich dokumentierte und verantwortete Ausnahme beschlossen wird. Nicht ausgeführte Tests, bekannte Einschränkungen und nicht unterstützte Plattform-/Modkombinationen müssen offengelegt werden.

## 18.20 Datenschutz und Diagnoseinformationen

Diagnose- und Telemetriedaten sollen auf das notwendige Maß begrenzt sein. Erhebung, Zweck, Speicherort, Aufbewahrung und Übertragung sind transparent zu dokumentieren und anwendbare rechtliche Anforderungen zu prüfen.

Das Spiel muss grundlegende Fehlerdiagnose ohne verpflichtende externe Telemetrie ermöglichen. Zugangsdaten, private Inhalte und unnötige Identifikatoren gehören nicht in Logs oder Supportpakete.

## 18.21 Schrittweise Verifikation

Jedes Arbeitspaket liefert einen früh prüfbaren Zustand. Tests und visuelle Kontrolle erfolgen fortlaufend und nicht erst am Ende eines großen Entwicklungsblocks.

Der Bericht unterscheidet eindeutig zwischen implementiert, integriert, technisch getestet, im Spiel getestet, zur Abnahme bereit und akzeptiert. Fehler werden vor dem Ausbau abhängiger Funktionen priorisiert und bearbeitet.

## 18.22 Offene QA-, Sicherheits- und Performanceentscheidungen

| ID | Thema | Status |
|---|---|---|
| QA-001 | Zielhardware und verbindliche Performancebudgets | Produkt-/Benchmarkentscheidung erforderlich |
| QA-002 | Automatisierungsgrad und CI-Testpipeline | Prozess-/Toolentscheidung erforderlich |
| QA-003 | Umfang repräsentativer Testwelten und Lastprofile | QA-Konzept erforderlich |
| QA-004 | Savegame-Kompatibilitäts- und Wiederherstellungsziele | Produkt-/Technikentscheidung erforderlich |
| QA-005 | Bedrohungsmodell und Sicherheitsreview-Zyklus | Sicherheitskonzept erforderlich |
| QA-006 | Release-Gates und Ausnahmefreigaben | Prozessentscheidung erforderlich |
| QA-007 | Telemetrie, Datenschutz und Diagnoseexport | Produkt-/Rechtsprüfung erforderlich |
| QA-008 | Plattformübergreifende Modding- und Backend-Testmatrix | Kompatibilitätstests erforderlich |
| QA-009 | Visuelle Qualitätsmetriken und Abnahmeverfahren | Art-/QA-Abstimmung erforderlich |
| QA-010 | Langzeittests für Simulation und Weltzeit | Testkonzept erforderlich |


## 18.23 Systemübergreifende Integrationsprüfungen

Einzeltests je Fachsystem reichen nicht aus, wenn ein Feature Daten und Zustände über mehrere Systeme hinweg verändert. Für zentrale Spielabläufe sind reproduzierbare Ende-zu-Ende-Prüfungen vorzusehen.

Geeignete Integrationsketten umfassen beispielsweise:
- World-/Biome-Definition → Regionsgenerierung → persistierte Region → Streaming und Runtime;
- Settlement/Building → NPC-Arbeitsplatz und Tagesablauf → Produktion → Wirtschaftszustand;
- Questbedingung → Entscheidung/Trigger → systemübergreifende Zustandsänderung → Belohnung und persistente Konsequenz;
- Itemdefinition → Instanz/Inventar → Ausrüstung → Charakter-/Kampfwirkung;
- Datenmod → Paket- und Referenzvalidierung → Registrierung → Runtime-Nutzung → Savegame-Wiederöffnung;
- Editoränderung → Validierung/Übernahme → Build oder Laufzeit → erneutes Laden.

Jede Integrationsprüfung dokumentiert Ausgangsdaten, Versionen, Seeds soweit relevant, erwarteten Zustand, tatsächliches Ergebnis und Wiederholbarkeit. Fehler müssen auf das verantwortliche System und die betroffenen IDs eingegrenzt werden können.

## 18.24 Releaseprüfung über Daten-, Asset- und Contentgrenzen

Vor einem Release werden nicht nur ausführbare Dateien, sondern auch die tatsächlich ausgelieferten Datenpakete und Assets geprüft. Die Prüfung umfasst mindestens:
- Schema- und Referenzintegrität;
- erforderliche Mod-/Content-Abhängigkeiten;
- Assetherkunft, Lizenzstatus und vorgeschriebene Attribution;
- Versionen und Migrationsfähigkeit unterstützter Spielstände;
- unbeabsichtigte Test-, Debug- oder nicht freigegebene Inhalte;
- Übereinstimmung zwischen freigegebenem Content und ausgeliefertem Build.

Nicht auflösbare Lizenz-, Datenintegritäts- oder Sicherheitsblocker verhindern die Releasefreigabe. Nicht ausgeführte Prüfungen sind als offen zu melden und dürfen nicht als bestanden gelten.
