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

## 20.5 Quellen, die für Vollständigkeit erneut eingelesen werden müssen

- „Geschichte und Quests entwickeln“ — vollständige ursprüngliche Lore, Storydetails und Quests.
- „Quest-System Erklärung“ und „Quest-System bewerten“ — bestehende Queststruktur, JSON, Bewertungen und Migration.
- „Wirtschaftsbalancing besprechen“ — existierende Wirtschaftsregeln, Balancingkonzepte und Monetarisierungsbezüge, soweit enthalten.
- Item-Archive Items.zip und Items(1).zip — Itemkataloge, Verzeichnisstruktur und JSON-Felder.
- „Webdesign für Vaelith“ — vollständige Seiten-/Funktions- und Designvorgaben.
- „Emberwild - World Generator“ — ursprüngliche Generator-/Editoranforderungen und Generatorintegration.
- „Emberwild“ — vorhandene Inhalte, Assets und technische Ausgangsinformationen.
- früher erstelltes VAELITH_Development_Manifest_v1.2.md — Draft prüfen; nicht automatisch als beschlossen behandeln.

Diese Quellen sind in der vorliegenden Dokumentationsfassung nicht vollständig erneut inspiziert. Der Agent darf nicht so tun, als sei dies geschehen. Der jeweils tatsächliche Zugriff/Import ist zu protokollieren.

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
