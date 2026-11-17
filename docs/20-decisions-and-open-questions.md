# 20 — Entscheidungsregister und offene Fragen

## 20.1 Zweck

Dieses Register unterscheidet ausdrücklich festgehaltene Leitplanken von offenen oder nur vorgeschlagenen Konzepten. Neue Erkenntnisse und Änderungen werden hier mit Datum, Quelle, Auswirkung und Status ergänzt.

## 20.2 Festgehaltene Leitplanken aus den verfügbaren Gesprächen

| Thema | Festgehaltene Aussage | Status |
|---|---|---|
| Engine | Vollständig 3D in Unity | Leitplanke |
| Bewegung/Welt | echte 3D-Bewegung und vertikale Räume | Leitplanke |
| Karten | prozedurale Weltkarte, nicht handgezeichnete Pflichtkarte | Leitplanke |
| Weltumfang | große geografische Gesamtkarte früh definieren | Leitplanke |
| Regionsfreigabe | nicht entwickelte Regionen bleiben minimale Platzhalter ohne vollständige 3D-Inhalte/Simulation | Leitplanke |
| Regionsstabilität | freigegebene Regionen nicht unerwartet neu generieren | Leitplanke |
| Biome | erst definieren, danach nach Kriterien verteilen | Leitplanke |
| Gefahr | unabhängig von Biomidentität behandeln | Leitplanke |
| Editoren | gemeinsame Datenmodelle/IDs/Referenzen, keine isolierten Wahrheiten | Leitplanke |
| Schloss/Dorf | gemeinsames Editorfundament, unterschiedliche Profile und Kataloge | Leitplanke |
| Dungeon | befreite Dungeons können ausgebaut, betrieben und verteidigt werden | Arbeitskonzept mit klarer Zielrichtung |
| Tiere/Kreaturen | gemeinsames Framework für Rollen, Bedürfnisse, Verhalten und Zucht | Arbeitskonzept mit klarer Zielrichtung |
| Modding | BepInEx-Grundlage und offizielle Vaelith Mod API in C# | vorgesehene Architektur |
| Modding-Sicherheit | Code-Mods sind privilegierter In-Process-Code; keine falsche Sandboxzusage | Leitplanke |
| Website | Spiel startet erst nach bewusster Spieleraktion im Hauptmenü | Leitplanke |
| Agenten | Claude primär; andere Agenten nur nach ausdrücklicher Freigabe | Leitplanke |
| ASHFALL | keine projektspezifischen Inhalte übernehmen | strikte Leitplanke |

## 20.3 Arbeitskonzepte, noch nicht endgültig festgelegt

- Science-Fantasy/futuristisch-magische Welt als bevorzugte aktuelle Setting-Richtung.
- Dramaturgischer Aufbau mit Vaelith, hybrider Spielerherkunft, Gefangenschaft und Befreiung.
- Spätere Freischaltung von Schloss-/Siedlungsbau, Dungeonbetrieb und Zucht.
- M00–M12 Roadmap.
- Konkrete Editor-Unterteilung und Liste zusätzlicher Fach-Editoren.
- Simulationsstufen nach Nähe und Relevanz.
- Vollständiger Zugang zum magischen Potenzial nach Vaeliths Befreiung mit späterer Beherrschung/Meisterung.

## 20.4 Offene inhaltliche Entscheidungen

1. Endgültiges Setting, Welt-/Planetenname und vollständige Kosmologie.
2. Ursprüngliche Emberwild-Lore und deren vollständige Integration.
3. Antworten zu Vaeliths Gefangenschaft, Gegenspielern und Ober-/Unterwelt.
4. Exakte Bedeutung und Abgrenzung von Hoftieren.
5. Finale Kapitel-/Queststruktur und Freischaltbedingungen.
6. Magiesystem, Progressionslogik und konkrete Fähigkeiten.
7. Finale Biomenliste, Gefahrenprofile und Regions-/Weltmaßstab.
8. Zielplattformen, Mindesthardware und Releaseumfang.
9. Detaillierte Item-, Quest-, NPC- und Wirtschaftsmodelle.
10. Vollständiges Monetarisierungsmodell.
11. Online-/Offline-Architektur und eventuelle Backend-Abhängigkeit.

## 20.5 Quellenstatus und verbleibende Quellenlücken

Die am 17. November 2026 bereitgestellte documents.zip wurde eingelesen und in Dokument 23 inventarisiert. Die Quest-Erweiterung, ein Quest-Beispiel, die Emberwild-Storygrundlagen, Konzeptfusion, Bausystem-/Expansionsdokumente, Multiplayer-Konzepte und die Item-/Produktionsunterlagen wurden direkt gesichtet. Die 240 JSON-Dateien ließen sich syntaktisch parsen; eine vollständige semantische Feld-, ID- und Referenzmigration ist noch offen.

Weiterhin separat zu prüfen bzw. erneut zu beschaffen sind:
- frühere Einzelgespräche „Geschichte und Quests entwickeln“, „Quest-System Erklärung“ und „Quest-System bewerten“, falls sie Details enthalten, die nicht in documents.zip vorliegen;
- „Wirtschaftsbalancing besprechen“ — konkrete historische Balancingentscheidungen und Monetarisierungsbezüge;
- „Webdesign für Vaelith“ — vollständige Seiten-/Funktions- und Designvorgaben;
- „Emberwild - World Generator“ — ursprüngliche Generator-/Editoranforderungen und Generatorintegration;
- frühere Einzelunterhaltungen „Emberwild“ und „Emberwild - World Generator“;
- VAELITH_Development_Manifest_v1.2.md — Draft prüfen; nicht automatisch als beschlossen behandeln;
- ursprüngliche Monetarisierungsunterlagen, sofern sie außerhalb des ZIP-Archivs liegen.

Die Quellenregister 23–25 dokumentieren, was tatsächlich aus documents.zip eingesehen wurde und welche Migration noch aussteht. Ein Agent darf frühere Gespräche oder Dateien nicht als gelesen ausgeben, wenn kein tatsächlicher Zugriff vorliegt.

## 20.6 Änderungsprotokoll

Für jede Änderung an einer Leitplanke oder einem bestehenden Datenmodell ist zu ergänzen:
- Datum und Referenz/Quelle;
- alter Wortlaut bzw. alter Zustand;
- neuer Wortlaut bzw. neuer Zustand;
- Änderungstyp;
- Begründung;
- betroffene Dateien, IDs, Systeme und Speicherstände;
- Migration und Tests;
- entscheidende Person und Status.

## 20.7 Annahmen und Zahlen

Unbestätigte Größenangaben aus früheren Beispielen (z. B. bestimmte Regionenzahlen, Kilometermaße, Chunkgrößen oder Installationsgrößen) gelten nicht als genehmigte Spezifikation. Sie müssen durch Prototypen und Messungen ersetzt werden.

## 20.8 Ergänzte offene Entscheidungen aus dem Spieler- und Magiekonzept

Die folgenden Punkte wurden bei der Ausarbeitung von 04-player-progression-and-magic.md als noch nicht entschieden identifiziert. Sie bleiben offen, bis vorhandene Originaldaten geprüft und die fachlichen Entscheidungen gemeinsam getroffen wurden.

| ID | Thema | Quelle | Status |
|---|---|---|---|
| PROG-001 | Grundattribute und abgeleitete Werte des Character-Systems | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |
| PROG-002 | Klassen, Rollen oder freie Spezialisierung | 04-player-progression-and-magic.md | Offen |
| PROG-003 | Bestehende Stufen-, Erfahrungs- und Fortschrittsregeln | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |
| PROG-004 | Aktive/passive Fähigkeiten und Gruppierung | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |
| PROG-005 | Magieformen, Schulen und Kategorien | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |
| PROG-006 | Funktionsweise der Machtströme und Spieler-Aura | 04-player-progression-and-magic.md | Offen |
| PROG-007 | Spielmechanische Darstellung des vollständigen Potenzials nach Vaeliths Befreiung | 04-player-progression-and-magic.md | Arbeitskonzept, Umsetzung offen |
| PROG-008 | Entwicklung von Kontrolle, Präzision und Meisterschaft | 04-player-progression-and-magic.md | Offen |
| PROG-009 | Magieressourcen, Kosten, Abklingzeiten oder andere Begrenzungen | 04-player-progression-and-magic.md | Offen |
| PROG-010 | Bestehende Kampf-, Bewegungs- und Trefferregeln | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |
| PROG-011 | Verknüpfung von Itemattributen, Ausrüstungsslots und Charakterwerten | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |
| PROG-012 | Klassifikation persistenter Entscheidungswirkungen | 04-player-progression-and-magic.md | Offen |
| PROG-013 | Konkrete Unterrichts-, Begleiter- und Reaktionsfunktionen Vaeliths | 04-player-progression-and-magic.md | Offen |
| PROG-014 | Übernahme und Migration vorhandener Charakter-, Skill-, Magie- und Kampfdaten | 04-player-progression-and-magic.md | Quellenabgleich erforderlich |

## 20.9 Ergänzte offene Entscheidungen aus den Gameplay-Systemen

Die folgenden Punkte wurden bei der Erweiterung von 05-gameplay-systems.md als nicht abschließend spezifiziert identifiziert. Sie sind keine stillschweigenden Designentscheidungen. Vor Implementierung sind vorhandene Quellen zu prüfen und die offenen Regeln gemeinsam festzulegen.

| ID | Thema | Quelle | Status |
|---|---|---|---|
| GAME-001 | Vollständige Interaktionsarten, Kontextregeln und Abbruchverhalten | 05-gameplay-systems.md | Offen |
| GAME-002 | Bestehende Kampfregeln, Trefferlogik und Aktionszustände | 05-gameplay-systems.md | Quellenabgleich erforderlich |
| GAME-003 | Kampfressourcen, Effekte, Widerstände und Niederlagenfolgen | 05-gameplay-systems.md | Offen |
| GAME-004 | Verbindliche Verknüpfung von Questentscheidungen mit persistenten Weltzuständen | 05-gameplay-systems.md | Offen |
| GAME-005 | Bauplatzierung: Raster, Freiform oder kontextabhängiges Hybridverfahren | 05-gameplay-systems.md | Offen |
| GAME-006 | Baukosten, Bauzeit, Materialtransport und Arbeitskräfteberechnung | 05-gameplay-systems.md | Offen |
| GAME-007 | Schloss-/Siedlungsrechte, Grenzen und Besitz-/Kontrollmodell | 05-gameplay-systems.md | Offen |
| GAME-008 | Dungeonbesitz, Personal, Unterhalt, Angriffe und Wiederherstellung | 05-gameplay-systems.md | Offen |
| GAME-009 | Konkrete Raumtypen und Funktionsprofile für Dungeons | 05-gameplay-systems.md | Offen |
| GAME-010 | Kreaturenrollen-Kompatibilität und Zuweisungsregeln | 05-gameplay-systems.md | Offen |
| GAME-011 | Definition und Abgrenzung von Hoftieren | 05-gameplay-systems.md | Gemeinsam festzulegen |
| GAME-012 | Zuchtregeln, Genetik, Wahrscheinlichkeiten und Generationseffekte | 05-gameplay-systems.md | Offen |
| GAME-013 | Gameplay-UI, Eingabebelegung und Accessibility-Anforderungen | 05-gameplay-systems.md | Offen |
| GAME-014 | Speichern/Wiederherstellen mehrstufiger Gameplay-Aktionen | 05-gameplay-systems.md | Technische Spezifikation erforderlich |
| GAME-015 | Vollständiger Abgleich des vorhandenen Quest-JSON und Quest-Editors | 05-gameplay-systems.md | Quellenabgleich erforderlich |

## 20.10 Ergänzte offene Entscheidungen aus der Welt- und Simulationsarchitektur

Die folgenden Punkte wurden bei der Erweiterung von 06-living-world-simulation.md identifiziert. Sie beschreiben offene fachliche oder technische Entscheidungen und sind nicht als bereits beschlossene Regeln zu behandeln.

| ID | Thema | Quelle | Status |
|---|---|---|---|
| SIM-001 | Finale NPC-Bedürfnisgruppen und deren Priorisierung | 06-living-world-simulation.md | Offen |
| SIM-002 | Detailgrad und Speicherumfang persönlicher Erinnerungen | 06-living-world-simulation.md | Offen |
| SIM-003 | Informationsverbreitung zwischen NPCs und Fraktionen | 06-living-world-simulation.md | Offen |
| SIM-004 | Beziehungsmodell und Fraktionsdynamik | 06-living-world-simulation.md | Offen |
| SIM-005 | Faktoren und Grenzen des Siedlungswachstums | 06-living-world-simulation.md | Offen |
| SIM-006 | Konkrete Produktions-, Verbrauchs- und Transportregeln | 06-living-world-simulation.md | Quellenabgleich/Design erforderlich |
| SIM-007 | Ökologische Populationsmodelle und Schutz seltener Arten | 06-living-world-simulation.md | Offen |
| SIM-008 | Weltzeit bei geschlossenem Spiel und Offline-Fortschritt | 06-living-world-simulation.md | Produktentscheidung erforderlich |
| SIM-009 | Simulationsintervalle, Radien und CPU-/Speicherbudgets | 06-living-world-simulation.md | Profiling erforderlich |
| SIM-010 | Determinismus-Anforderungen über Plattformen und Spielstände hinweg | 06-living-world-simulation.md | Technische Prüfung erforderlich |
| SIM-011 | Übergang von aggregierten Populationen zu individuellen NPCs/Tieren | 06-living-world-simulation.md | Technische Spezifikation erforderlich |
| SIM-012 | Ereignisketten, Zufallssteuerung und globale Ereignisgrenzen | 06-living-world-simulation.md | Offen |
| SIM-013 | Konkrete Rollen von Krankheiten, Verletzungen und Sterblichkeit in der Simulation | 06-living-world-simulation.md | Offen |
| SIM-014 | Simulation politischer Konflikte, Bündnisse und territorialer Kontrolle | 06-living-world-simulation.md | Lore-/Gameplay-Abgleich erforderlich |
| SIM-015 | Umgang mit Questfiguren und geschützten Populationen in Fernsimulation | 06-living-world-simulation.md | Offen |

## 20.11 Ergänzte offene Entscheidungen aus der Weltgenerierung

Die folgenden Punkte wurden bei der Erweiterung von 07-world-generation.md identifiziert. Sie sind nicht als bereits getroffene technische oder inhaltliche Entscheidungen zu verstehen.

| ID | Thema | Quelle | Status |
|---|---|---|---|
| WORLD-001 | Weltmaßstab, Projektion und geografische Ausdehnung | 07-world-generation.md | Offen |
| WORLD-002 | Auflösung und Detailgrad der globalen Weltkarte | 07-world-generation.md | Technische Prüfung erforderlich |
| WORLD-003 | Regionengröße und Verhältnis zu technischen Chunks | 07-world-generation.md | Prototyp/Profiling erforderlich |
| WORLD-004 | Generatoralgorithmen für Kontinente, Höhenmodell und Küsten | 07-world-generation.md | Evaluierung erforderlich |
| WORLD-005 | Klima-, Wind-, Niederschlags- und Wasserhaushaltsmodell | 07-world-generation.md | Offen |
| WORLD-006 | Finale Biomenliste und Übergangsregeln | 07-world-generation.md | Gemeinsam festzulegen |
| WORLD-007 | Fluss-/Entwässerungsmodell und regionsübergreifende Kontinuität | 07-world-generation.md | Technische Spezifikation erforderlich |
| WORLD-008 | Ressourcen-, Vegetations- und Faunaverteilungsregeln | 07-world-generation.md | Fachlicher Abgleich erforderlich |
| WORLD-009 | POI-Dichte, Seltenheit und Schutz storykritischer Orte | 07-world-generation.md | Offen |
| WORLD-010 | Weltkoordinatensystem und Maßeinheiten | 07-world-generation.md | Technische Entscheidung erforderlich |
| WORLD-011 | Seed-Aufteilung und Stabilitätsgarantien bei Generatoränderungen | 07-world-generation.md | Technische Prüfung erforderlich |
| WORLD-012 | Azgaar-Importumfang, Exportformate und Lizenzprüfung | 07-world-generation.md | Quellen-/Lizenzprüfung erforderlich |
| WORLD-013 | Terrain-Technologie: Unity Terrain, Mesh-Chunks oder Kombination | 07-world-generation.md | Prototyp/Profiling erforderlich |
| WORLD-014 | Freigabe- und Migrationsverfahren veröffentlichter Regionen | 07-world-generation.md | Prozessentscheidung erforderlich |
| WORLD-015 | Kriterien für Siedlungseignung und Routenplanung | 07-world-generation.md | Offen |

## 20.12 Ergänzte offene Entscheidungen aus der Editor-Suite

| ID | Thema | Quelle | Status |
|---|---|---|---|
| EDITOR-001 | Technische Basis der Editor-Suite innerhalb/außerhalb des Unity-Editors | 08-editor-suite.md | Architekturentscheidung erforderlich |
| EDITOR-002 | Gemeinsames UI-/UX-System und Layoutstandards | 08-editor-suite.md | Prototyp/Abstimmung erforderlich |
| EDITOR-003 | Gemeinsames Referenz- und Dependency-Browser-Konzept | 08-editor-suite.md | Technische Spezifikation erforderlich |
| EDITOR-004 | Undo/Redo-Umfang und Änderungs-/Transaktionsmodell | 08-editor-suite.md | Technische Prüfung erforderlich |
| EDITOR-005 | Import-/Exportformate und Migrationsworkflow je Fachgebiet | 08-editor-suite.md | Quellenabgleich erforderlich |
| EDITOR-006 | Berechtigungs- und Freigabemodell | 08-editor-suite.md | Offen |
| EDITOR-007 | Umfang von Simulationen direkt in Fach-Editoren | 08-editor-suite.md | Workflowprüfung erforderlich |
| EDITOR-008 | Erweiterungspunkte für Datenmods und Code-Mods | 08-editor-suite.md | Abgleich mit Dokument 11 erforderlich |
| EDITOR-009 | Gemeinsame Suche, Tags und Metadatenstandards | 08-editor-suite.md | Technische Spezifikation erforderlich |
| EDITOR-010 | Automatisierte Editor-Workflowtests und Testdatenverwaltung | 08-editor-suite.md | QA-Spezifikation erforderlich |

## 20.13 Ergänzte offene Entscheidungen aus der Datenarchitektur

| ID | Thema | Quelle | Status |
|---|---|---|---|
| DATA-001 | Kanonische Serialisierung für Definitionen, Weltzustände und Spielstände | 09-data-architecture.md | Technische Evaluierung erforderlich |
| DATA-002 | Speichertechnologie und Datenbankbedarf | 09-data-architecture.md | Architekturentscheidung erforderlich |
| DATA-003 | Granularität von Welt-/Regions-/Chunkpersistenz | 09-data-architecture.md | Prototyp/Profiling erforderlich |
| DATA-004 | Ereignisprotokoll: Umfang, Aufbewahrung und Kompaktierung | 09-data-architecture.md | Offen |
| DATA-005 | Transaktions-/Wiederherstellungsmodell für systemübergreifende Aktionen | 09-data-architecture.md | Technische Spezifikation erforderlich |
| DATA-006 | Schema- und Paketversionierung für Mod-Inhalte | 09-data-architecture.md | Abgleich mit Dokument 11 erforderlich |
| DATA-007 | Provenienzmodell für externe Karten, Assets und Contentimporte | 09-data-architecture.md | Offen |
| DATA-008 | Umgang mit Konflikten zwischen Generatorupdates und Spieleränderungen | 09-data-architecture.md | Technische Spezifikation erforderlich |

## 20.14 Ergänzte offene Entscheidungen aus der Unity-Architektur

| ID | Thema | Quelle | Status |
|---|---|---|---|
| ARCH-001 | Finale Unity-Version und Upgrade-Politik | 10-unity-architecture.md | Projektstartprüfung erforderlich |
| ARCH-002 | Renderpipeline und Renderfeature-Set | 10-unity-architecture.md | Prototyp/Benchmark erforderlich |
| ARCH-003 | Assembly-/Modulzuschnitt und Abhängigkeitsregeln | 10-unity-architecture.md | Vertikaler Prototyp erforderlich |
| ARCH-004 | Einsatz von ECS/DOTS gegenüber klassischer Unity-Architektur | 10-unity-architecture.md | Profiling und Anwendungsfallprüfung erforderlich |
| ARCH-005 | Threading-/Job-System für Generator und Simulation | 10-unity-architecture.md | Prototyp/Profiling erforderlich |
| ARCH-006 | Szenen-, Streaming- und Weltzustandslebenszyklus | 10-unity-architecture.md | Technische Spezifikation erforderlich |
| ARCH-007 | Physik-, Kollisions- und Navigationslösungen | 10-unity-architecture.md | Prototyp erforderlich |
| ARCH-008 | Zielplattformen, Backends und Buildprofile | 10-unity-architecture.md | Produktentscheidung erforderlich |
| ARCH-009 | Logging-/Telemetrieumfang und Datenschutzgrenzen | 10-unity-architecture.md | Produkt-/Technikentscheidung erforderlich |
| ARCH-010 | Netzwerk-/Onlinefunktionen und Backend-Abhängigkeiten | 10-unity-architecture.md | Produktentscheidung erforderlich |

## 20.15 Ergänzte offene Entscheidungen aus Modding und Vaelith Mod API

| ID | Thema | Quelle | Status |
|---|---|---|---|
| MOD-001 | BepInEx-Version, Fork-/Patchbedarf und unterstützte Plattformen | 11-modding-api.md | Kompatibilitätstest erforderlich |
| MOD-002 | Mono-/IL2CPP- und sonstige Backendstrategie | 11-modding-api.md | Technische Prüfung erforderlich |
| MOD-003 | Öffentliche API-Schichten und genaue Erweiterungspunkte | 11-modding-api.md | API-Design erforderlich |
| MOD-004 | Datenmod-Paketformat und Schema-Versionierung | 11-modding-api.md | Technische Spezifikation erforderlich |
| MOD-005 | Mod-ID-/Content-ID-Namensraum und Kollisionsregeln | 11-modding-api.md | Entscheidung erforderlich |
| MOD-006 | Mod-Ladepriorität und Konfliktauflösung | 11-modding-api.md | Design/Prototyp erforderlich |
| MOD-007 | Savegame-Verhalten bei fehlenden oder geänderten Mods | 11-modding-api.md | Technische Spezifikation erforderlich |
| MOD-008 | Vertrauenshinweise, Signaturen und Herkunftsprüfung | 11-modding-api.md | Sicherheitsprüfung erforderlich |
| MOD-009 | Mod-Manager-Umfang und Diagnoseexport | 11-modding-api.md | Produkt-/UX-Entscheidung erforderlich |
| MOD-010 | API-Versionierung, Supportfenster und Deprecation | 11-modding-api.md | Governance-Entscheidung erforderlich |

## 20.16 Ergänzte offene Entscheidungen aus Assets, Animation und Audio

| ID | Thema | Quelle | Status |
|---|---|---|---|
| ASSET-001 | Finale visuelle Stilrichtlinien und technische Qualitätsprofile | 12-assets-animation-audio.md | Art Direction erforderlich |
| ASSET-002 | Assetkatalog und stabile Asset-ID-Konvention | 12-assets-animation-audio.md | Daten-/Toolentscheidung erforderlich |
| ASSET-003 | Importprofile und unterstützte Austauschformate | 12-assets-animation-audio.md | Pipeline-Prototyp erforderlich |
| ASSET-004 | LOD- und Speicherbudgets je Assetkategorie | 12-assets-animation-audio.md | Profiling erforderlich |
| ASSET-005 | Modulare Charakter-/Ausrüstungs- und Kreaturenpipeline | 12-assets-animation-audio.md | Prototyp erforderlich |
| ASSET-006 | Rig-/Retargeting-Standards und Ausnahmen je Artengruppe | 12-assets-animation-audio.md | Animationstest erforderlich |
| ASSET-007 | Umfang und Lizenzierung von Musik, Sprache und Soundeffekten | 12-assets-animation-audio.md | Content-/Lizenzplanung erforderlich |
| ASSET-008 | Audio-Middleware oder Unity-Bordmittel | 12-assets-animation-audio.md | Prototyp/Anforderungsprüfung erforderlich |
| ASSET-009 | Asset-Streaming- und Addressables-Strategie | 12-assets-animation-audio.md | Technische Evaluierung erforderlich |
| ASSET-010 | Assetfreigabe und visuelle Qualitätsabnahme | 12-assets-animation-audio.md | Prozessentscheidung erforderlich |

## 20.17 Ergänzte offene Entscheidungen aus QA, Sicherheit und Performance

| ID | Thema | Quelle | Status |
|---|---|---|---|
| QA-001 | Zielhardware und verbindliche Performancebudgets | 18-qa-security-performance.md | Produkt-/Benchmarkentscheidung erforderlich |
| QA-002 | Automatisierungsgrad und CI-Testpipeline | 18-qa-security-performance.md | Prozess-/Toolentscheidung erforderlich |
| QA-003 | Umfang repräsentativer Testwelten und Lastprofile | 18-qa-security-performance.md | QA-Konzept erforderlich |
| QA-004 | Savegame-Kompatibilitäts- und Wiederherstellungsziele | 18-qa-security-performance.md | Produkt-/Technikentscheidung erforderlich |
| QA-005 | Bedrohungsmodell und Sicherheitsreview-Zyklus | 18-qa-security-performance.md | Sicherheitskonzept erforderlich |
| QA-006 | Release-Gates und Ausnahmefreigaben | 18-qa-security-performance.md | Prozessentscheidung erforderlich |
| QA-007 | Telemetrie, Datenschutz und Diagnoseexport | 18-qa-security-performance.md | Produkt-/Rechtsprüfung erforderlich |
| QA-008 | Plattformübergreifende Modding- und Backend-Testmatrix | 18-qa-security-performance.md | Kompatibilitätstests erforderlich |
| QA-009 | Visuelle Qualitätsmetriken und Abnahmeverfahren | 18-qa-security-performance.md | Art-/QA-Abstimmung erforderlich |
| QA-010 | Langzeittests für Simulation und Weltzeit | 18-qa-security-performance.md | Testkonzept erforderlich |


## 20.18 Ergänzte offene Entscheidungen aus Wirtschaft, Items und Crafting

| ID | Thema | Quelle | Status |
|---|---|---|---|
| ECON-001 | Wirtschaftsakteure, Geld-/Tauschmodell und regionale Marktgrenzen | 13-economy-items-crafting.md | Quellenabgleich/Design erforderlich |
| ECON-002 | Preisbildung und Gewichtung von Angebot, Nachfrage, Qualität und Entfernung | 13-economy-items-crafting.md | Balancingentscheidung erforderlich |
| ECON-003 | Händlerbestände, Geldquellen und Bestandsregeneration | 13-economy-items-crafting.md | Offen |
| ECON-004 | Transportkosten, Transportzeiten, Träger und Verlustrisiken | 13-economy-items-crafting.md | Offen |
| ECON-005 | Wirtschaftsereignisse, Engpässe und regionale Abhängigkeiten | 13-economy-items-crafting.md | Offen |
| ECON-006 | Aggregation von Wirtschaftsflüssen in der Fernsimulation | 13-economy-items-crafting.md | Prototyp/Profiling erforderlich |
| ECON-007 | Wirtschaftsdiagnose, Kennzahlen und Referenzszenarien | 13-economy-items-crafting.md | Tool-/QA-Spezifikation erforderlich |
| ECON-008 | Steuern, Abgaben, Löhne und weitere Geldsenken/-quellen | 13-economy-items-crafting.md | Quellenabgleich/Design erforderlich |

| ID | Thema | Quelle | Status |
|---|---|---|---|
| ITEM-001 | Vollständiger Import der historischen Itemarchive und Verzeichnisstruktur | 13-economy-items-crafting.md | Quellenzugriff erforderlich |
| ITEM-002 | Kanonisches Schema für Itemdefinitionen und Iteminstanzen | 13-economy-items-crafting.md | Quellenabgleich erforderlich |
| ITEM-003 | Erhalt und Migration bestehender Item-IDs und Referenzen | 13-economy-items-crafting.md | Migrationsplanung erforderlich |
| ITEM-004 | Kategorien, Unterkategorien und Ausrüstungsslots | 13-economy-items-crafting.md | Quellenabgleich erforderlich |
| ITEM-005 | Trennung von Qualität, Seltenheit, Zustand und visueller Variante | 13-economy-items-crafting.md | Designentscheidung erforderlich |
| ITEM-006 | Gewicht, Volumen, Stackregeln und Lagerkapazitäten | 13-economy-items-crafting.md | Quellenabgleich/Design erforderlich |
| ITEM-007 | Iteminstanz-Persistenz, Haltbarkeit und Zustandsänderungen | 13-economy-items-crafting.md | Technische Spezifikation erforderlich |
| ITEM-008 | Modding-Namensräume und Konfliktregeln für Itemdefinitionen | 13-economy-items-crafting.md | Abgleich mit MOD-004/005 erforderlich |

| ID | Thema | Quelle | Status |
|---|---|---|---|
| CRAFT-001 | Vollständiger Bestand bestehender Rezepte und Herstellungsdaten | 13-economy-items-crafting.md | Quellenzugriff erforderlich |
| CRAFT-002 | Rezeptmodell, Inputs, Outputs und Nebenprodukte | 13-economy-items-crafting.md | Quellenabgleich erforderlich |
| CRAFT-003 | Werkstatt-/Stationsanforderungen und Stationszustände | 13-economy-items-crafting.md | Offen |
| CRAFT-004 | Herstellungszeit, Abbruch und Transaktionsverhalten | 13-economy-items-crafting.md | Technische Spezifikation erforderlich |
| CRAFT-005 | Einfluss von Fähigkeiten, Berufen und Rohstoffqualität | 13-economy-items-crafting.md | Balancingentscheidung erforderlich |
| CRAFT-006 | Editorworkflow für Rezepte, Validierung und Simulation | 13-economy-items-crafting.md | Editor-Spezifikation erforderlich |

## 20.19 Ergänzte offene Entscheidungen aus Webplattform und Administration

| ID | Thema | Quelle | Status |
|---|---|---|---|
| WEB-001 | Finale Website-Seitenstruktur und Informationsarchitektur | 14-web-platform.md | Abgleich mit Original-Webdesign erforderlich |
| WEB-002 | Launcher-Architektur und expliziter Startablauf | 14-web-platform.md | Technische Entscheidung erforderlich |
| WEB-003 | Kontenmodell und Identitätsanbieter, falls benötigt | 14-web-platform.md | Produkt-/Architekturentscheidung erforderlich |
| WEB-004 | Onlinepflicht, Offlinebetrieb und Backendabhängigkeiten | 14-web-platform.md | Abgleich mit ARCH-010 erforderlich |
| WEB-005 | Finale Adminmodule und Rollen-/Rechtematrix | 14-web-platform.md | Scopeentscheidung erforderlich |
| WEB-006 | Hosting, Umgebungen, Betrieb und Wiederherstellung | 14-web-platform.md | Betriebs-/Architekturentscheidung erforderlich |
| WEB-007 | Content-Publishing, Versionierung und Rollback | 14-web-platform.md | Prozess-/Technikspezifikation erforderlich |
| WEB-008 | Gemeinsames Designsystem und Komponentenverantwortung | 14-web-platform.md | UI-Prototyp/Abstimmung erforderlich |
| WEB-009 | Datenschutz, Aufbewahrung und Auditumfang | 14-web-platform.md | Rechts-/Produktprüfung erforderlich |
| WEB-010 | Barrierefreiheit und unterstützte Browser-/Geräteklassen | 14-web-platform.md | Qualitäts-/Produktentscheidung erforderlich |

## 20.20 Ergänzte offene Entscheidungen aus Monetarisierung

| ID | Thema | Quelle | Status |
|---|---|---|---|
| MON-001 | Vollständige Sichtung der historischen Monetarisierungsvorgaben | 15-monetization.md | Originalquellen erforderlich |
| MON-002 | Bestätigte Monetarisierungsarten und Angebotsformen | 15-monetization.md | Quellenabgleich erforderlich |
| MON-003 | Historisch festgelegte Preise, Währungen und regionale Regeln | 15-monetization.md | Quellenabgleich erforderlich |
| MON-004 | Umfang und Rechte von Updates, Erweiterungen und Zusatzinhalten | 15-monetization.md | Quellenabgleich erforderlich |
| MON-005 | Auswirkungen auf Gameplay, Progression, Modding und Spielstände | 15-monetization.md | Analyse nach Quellenimport erforderlich |
| MON-006 | Store-, Plattform-, Backend- und Zahlungsanforderungen | 15-monetization.md | Abhängig vom bestätigten Modell |
| MON-007 | Umgang mit widersprüchlichen oder überholten historischen Aussagen | 15-monetization.md | Projektleitungsentscheidung erforderlich |

## 20.21 Ergänzte offene Entscheidungen aus der MDP

| ID | Thema | Quelle | Status |
|---|---|---|---|
| MDP-001 | Granularität und Kennzeichnung von Monolithen, Paketen, Aufgaben und Unteraufgaben | 16-mdp-development-process.md | Prozessentscheidung erforderlich |
| MDP-002 | Zentrales Format und Ablage der Arbeitspaketdefinitionen | 16-mdp-development-process.md | Tool-/Prozessentscheidung erforderlich |
| MDP-003 | Verbindliche Abhängigkeitsdarstellung und Paketplanung | 16-mdp-development-process.md | Prozessspezifikation erforderlich |
| MDP-004 | Review- und Freigabepunkte je Paketgröße und Risikoklasse | 16-mdp-development-process.md | Prozessentscheidung erforderlich |
| MDP-005 | CI-/Build-/Testintegration in den Paketlebenszyklus | 16-mdp-development-process.md | Tool-/Prozessentscheidung erforderlich |
| MDP-006 | Rückfall- und Migrationsverfahren für gemeinsam genutzte Datenverträge | 16-mdp-development-process.md | Technische Spezifikation erforderlich |
| MDP-007 | Messbare Priorisierungskriterien und Roadmappflege | 16-mdp-development-process.md | Prozessentscheidung erforderlich |

## 20.22 Ergänzte offene Entscheidungen aus den Agentenregeln

| ID | Thema | Quelle | Status |
|---|---|---|---|
| AGENT-001 | Verbindliches Format für Agentenstart- und Bestandsberichte | 19-agent-operating-rules.md | Prozessentscheidung erforderlich |
| AGENT-002 | Ablage und Nachweisformat für Tests, Screenshots und Builds | 19-agent-operating-rules.md | Tool-/Prozessentscheidung erforderlich |
| AGENT-003 | Genehmigungsworkflow für zusätzliche Agenten und externe Mitwirkende | 19-agent-operating-rules.md | Projektleitungsentscheidung erforderlich |
| AGENT-004 | Asset-/Bibliothekslizenzinventar und regelmäßige Prüfung | 19-agent-operating-rules.md | Prozessspezifikation erforderlich |
| AGENT-005 | Einheitliches Übergabeformat und Statusnachweise | 19-agent-operating-rules.md | Prozessspezifikation erforderlich |
| AGENT-006 | Technische Projektprüfung vor Paketbeginn einschließlich Unity-Umgebung | 19-agent-operating-rules.md | Prozessspezifikation erforderlich |


## 20.23 Ergänzte offene Entscheidungen aus Asset-Credits und Urhebernachweisen

| ID | Thema | Quelle | Status |
|---|---|---|---|
| ASSET-011 | Technische Form, Ablage, Pflege und Buildintegration des zentralen Asset-Credit- und Attribution-Registers | 12-assets-animation-audio.md | Tool-/Prozessentscheidung erforderlich |
| ASSET-012 | Automatisierte Prüfung ausgelieferter Assets gegen Lizenz- und Creditregister | 12-assets-animation-audio.md | Pipeline-/QA-Spezifikation erforderlich |
| ASSET-013 | Konkrete Credit-Platzierung und Ausgabeformate je Releasekanal | 12-assets-animation-audio.md | Lizenz- und Produktprüfung erforderlich |


## 20.24 Ergänzte offene Entscheidungen aus der systemübergreifenden Konsistenzprüfung

| ID | Thema | Betroffene Dokumente | Status |
|---|---|---|---|
| DATA-009 | Globales ID-/Namensraummodell für Grundspiel, Mods, Importe und lokale Inhalte | 09, 11 | Technische Spezifikation erforderlich |
| DATA-010 | Einheitlicher Änderungs-, Validierungs-, Freigabe- und Wiederherstellungslebenszyklus | 08, 09, 14, 18 | Prozess- und Architekturentscheidung erforderlich |
| DATA-011 | Regeln für Änderungen an Definitionen gegenüber bestehenden Instanzen und persistentem Weltzustand | 07, 09, 13 | Fachliche und technische Spezifikation erforderlich |
| WEB-011 | Kanonische Eigentümerschaft, Veröffentlichungsworkflow und Synchronisation gemeinsamer Web-/Spielinhalte | 09, 14 | Produkt-/Architekturentscheidung erforderlich |
| QA-011 | Verbindliche Ende-zu-Ende-Integrationsszenarien und Testdatenbasis je Kernspielablauf | 05, 08, 09, 18 | Testkatalog vor Implementierungsbeginn festzulegen |

Diese Punkte wurden als Klärungsbedarf ergänzt. Die zugehörigen Abschnitte beschreiben notwendige Anforderungen, legen aber weder ein konkretes ID-Format noch eine bestimmte Datenbank, Backendarchitektur oder technische Transaktionsimplementierung fest.

## 20.25 Übergeordnete Projekt- und Konzeptklassifizierung

| Aussage | Einordnung | Konsequenz |
|---|---|---|
| Das neue Spiel heißt Vaelith | Verbindliche Projektleitplanke | Produktname in Projekt, Dokumentation und Builds |
| Entwicklung als vollständiges 3D-Spiel in Unity | Verbindliche Projektleitplanke | Eigenständige Unity-Neuentwicklung |
| Bestehende Emberwild-/Vaelith-Konzepte und Daten | Fachliche Ausgangsquellen | Vor Übernahme prüfen, danach migrieren/anpassen/erweitern oder begründet ausnehmen |
| In den Konzeptdokumenten beschriebene Systemrichtungen | Jeweils Leitplanke, Arbeitskonzept oder Vorschlag gemäß Kennzeichnung | Keine pauschale Implementierung aller genannten Features |
| Zusätzliche Ideen und Funktionsvorschläge | Vorschlag/Funktionserweiterung | Erst nach Spezifikation, Priorisierung und Freigabe umsetzen |
| Nicht entschiedene Fragen und Quellenlücken | Offen | Nicht als beschlossene Architektur oder Spielfunktion behandeln |

Diese Einordnung ist übergeordnet und gilt für sämtliche Fachkonzepte. Sie ersetzt nicht die jeweils konkrete Statuskennzeichnung in den einzelnen Dokumenten.


## 20.26 Entscheidungen aus dem Quellenimport und Quest-System-Design

| ID | Entscheidung / Thema | Status |
|---|---|---|
| QUEST-001 | Quest Runtime als zentrale, datengetriebene Event-/Zustandsmaschine; keine Questlogik in Szenenskripten | Vaelith-Zielarchitektur festgelegt |
| QUEST-002 | Questdefinitionen, Dialoge, Knowledge, World State und Player Quest State sind getrennte Datenbereiche | Zielarchitektur festgelegt |
| QUEST-003 | Conditions als typisierte verschachtelte Ausdrucksbäume mit AND/OR/NOT | Zielarchitektur festgelegt |
| QUEST-004 | Objectives als azyklischer Graph mit Gruppen, Abhängigkeiten und Alternativpfaden | Zielarchitektur festgelegt |
| QUEST-005 | Entscheidungen werden dauerhaft im Decision Ledger gespeichert und können verzögerte Konsequenzen auslösen | Zielarchitektur festgelegt |
| QUEST-006 | World Actions sind zentral definiert, autorisiert und idempotent | Zielarchitektur festgelegt |
| QUEST-007 | Knowledge unterstützt Quellen, Bestätigung, Widerlegung und widersprüchliche Informationen | Zielarchitektur festgelegt |
| QUEST-008 | Hauptstory-Quests sind standardmäßig nicht aufgebbar; Zeitlimits müssen klar kommuniziert sein | Vaelith-Designentscheidung |
| QUEST-009 | Multiplayer-Questregeln sind nicht Teil des aktuellen verbindlichen Umfangs | Singleplayer-first; Multiplayer offen |
| QUEST-010 | Bestehende Quest-IDs, Objective-IDs, Übersetzungen und World-Change-Referenzen sind soweit möglich zu erhalten | Migrationsleitplanke |
| QUEST-011 | Questdaten enthalten keinen beliebigen ausführbaren Code | Sicherheits-/Architekturleitplanke |
| DATA-012 | Itemdefinitionen, Instanzen, Stacks, Rezepte, Produktionsaufträge und Facilities sind getrennte Datenkonzepte | Zielarchitektur festgelegt |
| DATA-013 | Historische Katalogversionen werden familienweise verglichen; Einträge verschiedener Versionen werden nicht addiert | Migrationsleitplanke |
| GAME-016 | Volle 3D-Bewegung ist Primärmodell; isometrische Übersicht ist Kameramodus, keine 2D-Bewegungsarchitektur | Projektleitplanke konkretisiert |
| GAME-017 | Kamera-/Physikwerte aus Emberwild-Entwürfen sind Prototypwerte und müssen in Unity validiert werden | Technische Leitplanke |
| EDITOR-011 | Quest Editor muss Graphauthoring, Simulation, Debugging und Validierung abdecken | Zielanforderung |
| EDITOR-012 | 3D-Editor-Grundwerkzeuge werden als gemeinsame Infrastruktur bereitgestellt | Zielanforderung |

Die detaillierten Anforderungen und Quellen stehen in Dokument 23 (Quellenregister), Dokument 24 (Item-/Produktionsmigration) und Dokument 25 (Quest-System). Diese Entscheidungen konkretisieren die Vaelith-Zielarchitektur; sie behaupten nicht, dass die ursprünglichen Emberwild-Systeme bereits fertig implementiert waren.

## 20.27 Quellenimport und delegierte Ausarbeitung

| ID | Thema | Einordnung | Status |
|---|---|---|---|
| SRC-001 | documents.zip ist zusätzliche fachliche Originalquelle | Quellenleitplanke | Inventarisiert; systemweise Konsolidierung läuft |
| SRC-002 | Emberwild-Fachkonzepte sind auf Vaelith-Eignung zu prüfen | Migrationsleitplanke | Gilt projektweit |
| SRC-003 | ASHFALL-spezifische Inhalte bleiben ausgeschlossen | Verbindliche Leitplanke | Unverändert |
| SRC-004 | Multiplayer-Konzepte sind nicht automatisch Bestandteil des Releaseumfangs | Produkt-/Scopeentscheidung | Singleplayer-first; Umfang offen |
| SRC-005 | Delegierte offene Designfragen dürfen eigenständig für Vaelith ausgearbeitet werden | Arbeitsauftrag | Ausarbeitung muss als neue Vaelith-Entscheidung gekennzeichnet sein |
| SRC-006 | Quest-System ist noch nicht fertig entwickelt | Quellen-/Projektstatus | Zielarchitektur in Dokument 25; Implementierung und Datenmigration offen |
| SRC-007 | Das eingebettete Items.zip überschneidet sich mit dem äußeren Items-Bestand | Migrationsleitplanke | Vor Katalogzählung und Migration deduplizieren |

Die Quellenregister 23–25 sind Teil der maßgeblichen Projektdokumentation. Ein als Arbeitskonzept gekennzeichneter Vorschlag wird erst nach Projektfreigabe zur verbindlichen Produktentscheidung, sofern die Projektleitung nicht ausdrücklich eine konkrete Designentscheidung delegiert hat.