# 17 — Roadmap und Arbeitspakete

## 17.1 Status

Die folgende M00–M12-Struktur ist eine **vorläufige Roadmap**, die aus den bisherigen Projektgesprächen abgeleitet wurde. Sie ist ein Ordnungs- und Planungsmodell, keine endgültig genehmigte Terminplanung. Reihenfolge und Umfang können sich nach Bestandsaufnahme, Prototypen und Abhängigkeiten ändern.

## 17.2 Vorläufige Monolithen

| ID | Themenbereich | Schwerpunkt |
|---|---|---|
| M00 | Projektdefinition und Gesamtarchitektur | Quelleninventar, Leitplanken, technische Basisentscheidungen, Systemgrenzen |
| M01 | Unity Core Framework | Projektstruktur, Core-Dienste, Logging, IDs, Daten-/Eventgrundlage |
| M02 | World Generation & Editor | Weltparameter, Weltkarte, Biom-/Gefahrenlayer, Regionsplanung |
| M03 | 3D Terrain Pipeline / World Generator | Gelände, Wasser, Material, Streaming-/Terrainprototyp |
| M04 | Region-/Settlement Editor und Konstruktion | Siedlungsdaten, Grundstücke, Gebäudezuordnung, Bauwerkzeuge |
| M05 | Gebäude und Infrastruktur | Gebäudemodule, Innenräume, Navigation, Bau- und Infrastrukturregeln |
| M06 | NPC-System und lebendige Welt | NPCs, Routinen, Bedürfnisse, Beziehungen, Simulation |
| M07 | Wirtschaft und Produktion | Ressourcen, Lager, Produktion, Handel und Balancing |
| M08 | Tiere und Zucht | gemeinsames Creature Framework, Tierrollen, Haltung, Zucht |
| M09 | Spielercharakter und ARPG-Kampf | Bewegung, Charakterentwicklung, Ausrüstung, Kampf, Magiegrundlage |
| M10 | Quests und Narrative | Questlaufzeit, Editor, Dialoge, Storyintegration |
| M11 | Erkundung und Interaktionen | POIs, Dungeons, Interaktionen, Exploration |
| M12 | Integration, Optimierung und Release | Systemintegration, Performance, QA, Builds und Releasevorbereitung |

## 17.3 Abhängigkeiten und Parallelisierung

M00 ist Voraussetzung für belastbare Grundentscheidungen. M01 bildet Kernservices, soll jedoch nicht als isolierte monatelange Architekturphase ohne Spielprototyp umgesetzt werden. M02/M03 sind eng miteinander verbunden. M04/M05 benötigen Daten- und World-Grundlagen. M06/M07/M08 sind stark gekoppelt. M09/M10/M11 benötigen frühe Integrationspunkte, damit ein spielbarer Vertikalabschnitt entsteht.

Parallelisierung ist nur sinnvoll, wenn Schnittstellen, Datenverantwortung und Ownership feststehen. Agenten dürfen nicht ohne Freigabe gleichzeitig dieselben Dateien, Datenmodelle oder Architekturentscheidungen verändern.

## 17.4 Vertikale Scheiben

Die Roadmap soll früh einen zusammenhängenden, testbaren Spielabschnitt liefern. Beispiel einer vertikalen Scheibe:
- begrenzte, generierte Region;
- Terrain und Navigation;
- Spielerbewegung und Interaktion;
- ein NPC mit Tagesablauf;
- ein POI bzw. Dungeon;
- eine kurze Quest;
- ein Item-/Inventarfluss;
- Speichern und Laden;
- ein einfacher Produktions-/Weltzustand;
- Tests und Profiling.

Dieses Beispiel dient zur Demonstration der Integrationsstrategie und ist nicht als endgültiger Demoumfang festgelegt.

## 17.5 Einstieg und Umgebungsprüfung

Claude beginnt mit:
1. Repository- und Dokumentationsanalyse;
2. Prüfung bestehender Projektdateien und vorhandener Unity-Installation;
3. Inventarisierung von Abhängigkeiten, Assets und Datenquellen;
4. Prüfung von Zielplattformen und Modding-Kompatibilität;
5. Vorschlag priorisierter MDP-Pakete und offenen Entscheidungen.

Unity soll nicht erneut installiert werden, wenn eine funktionierende Installation und Projektumgebung bereits vorhanden ist. Ist die Umgebung noch nicht eingerichtet oder fehlerhaft, dokumentiert Claude den Zustand und führt den Benutzer gezielt durch notwendige Schritte. Nur bei einer tatsächlich nötigen Benutzeraktion wird auf deren Bestätigung gewartet.

## 17.6 Freigabepunkte

Vor dem Start größerer Implementierungspakete werden Umfang, Abnahmekriterien und grundlegende Entscheidungen besprochen und freigegeben. Nach Abschluss erfolgt eine demonstrierbare Übergabe mit Testnachweisen.


## 17.7 Paketierung in überprüfbare Lieferstufen

Die Monolithen werden in MDP-Arbeitspakete zerlegt. Ein Monolith ist kein einzelner Entwicklungsauftrag und kein Grund, mehrere Monate ohne prüfbares Ergebnis zu arbeiten. Jedes Paket soll einen klar abgegrenzten Funktions- oder Integrationsschritt liefern.

Die Roadmap unterscheidet:
- **Grundlagen:** notwendige technische und fachliche Verträge;
- **Vertikale Scheiben:** kleine vollständige Abläufe im tatsächlichen Spielkontext;
- **Ausbau:** zusätzliche Varianten, Inhalte und Detailtiefe;
- **Härtung:** Performance, Sicherheit, Kompatibilität, Migration und Fehlerbehebung;
- **Releasevorbereitung:** Inhalte, Credits, Store-/Plattformanforderungen, Builds und Freigaben.

Die Reihenfolge wird anhand konkreter Abhängigkeiten und frühestmöglicher Prüfbarkeit festgelegt. Ein Paket soll nicht künstlich warten, wenn ein unabhängiger Teilbereich sinnvoll und sicher umgesetzt werden kann.

## 17.8 Meilensteine als Ergebniszustände

Meilensteine werden durch nachweisbare Ergebnisse beschrieben, nicht allein durch Kalenderdaten oder Prozentangaben. Ein Meilenstein enthält:
- erwartete spielbare bzw. technisch prüfbare Fähigkeiten;
- enthaltene und ausdrücklich ausgeschlossene Inhalte;
- abhängige Pakete und offene Entscheidungen;
- funktionale und visuelle Prüfkriterien;
- Qualitäts-, Performance- und Sicherheitsanforderungen;
- bekannte Einschränkungen und Freigabestatus.

Termine werden erst geplant, wenn Umfang, Abhängigkeiten, Ressourcen und Unsicherheiten ausreichend bekannt sind. Frühere Schätzungen sind keine verbindlichen Zusagen.

## 17.9 Roadmap-Änderungen und Prioritätswechsel

Neue Erkenntnisse aus Prototypen, Quellenprüfung, Lizenzklärung, Performanceprofiling oder Nutzerfeedback können eine Umpriorisierung erforderlich machen. Jede wesentliche Änderung hält Ursache, betroffene Pakete, neue Abhängigkeiten und Auswirkungen auf bereits begonnene Arbeiten fest.

Bestehende Fortschritte werden nicht allein wegen einer geänderten Reihenfolge verworfen. Bereits integrierte und geprüfte Ergebnisse sollen möglichst erhalten bleiben. Änderungen an freigegebenem Umfang folgen dem MDP-Änderungsprozess aus Dokument 16.

## 17.10 Release- und Inhaltsfreigabe

Ein Releasekandidat benötigt einen nachvollziehbaren Stand der enthaltenen Funktionen, Daten, Assets, Lizenzen und offenen Einschränkungen. Dazu gehören insbesondere:
- reproduzierbarer Build und dokumentierte Buildkonfiguration;
- bestandene relevante QA- und Regressionstests;
- geprüfte Savegame- und Datenmigration;
- geprüfte Plattform- und Moddingkompatibilität im freigegebenen Umfang;
- vollständige Herkunfts- und Lizenznachweise für Drittinhalte;
- erzeugte und geprüfte Asset-Credits gemäß den jeweiligen Lizenzbedingungen;
- dokumentierte bekannte Fehler und genehmigte Ausnahmen.

Die Veröffentlichung ist eine eigene Freigabeentscheidung. Ein technisch erstellbarer Build ist nicht automatisch releasefähig.

## 17.11 Vorläufige Phasenorientierung

Die folgende Orientierung beschreibt die logische Reifeentwicklung und ersetzt keine genehmigte Terminplanung:

1. **Projekt- und Quellenklarheit:** Bestände, Rechte, Datenmodelle, Leitplanken und technische Umgebung erfassen.
2. **Technischer Kern:** Unity-Projekt, kanonische Datenverträge, Persistenz, Diagnose und erste Editorgrundlagen.
3. **Welt-Vertikalschnitt:** generierte und begehbare Region mit Terrain, Navigation, Spieler und Interaktion.
4. **Lebendige Welt:** NPC, Kreaturen, Bedürfnisse, Simulation und erste wirtschaftliche Kreisläufe.
5. **Gameplay-Vertikalschnitt:** Quest, Kampf, Inventar, POI/Dungeon und persistente Konsequenzen.
6. **Aufbau und Betrieb:** Schloss, Siedlung, Dungeonverwaltung, Produktion, Zucht und erweiterte Editorworkflows.
7. **Inhalt und Ausbau:** weitere Regionen, Biome, Kreaturen, Items, Quests und narrative Inhalte.
8. **Härtung und Veröffentlichung:** Optimierung, Kompatibilität, Lizenz-/Creditprüfung, QA und Release.

Diese Phasen können sich teilweise überlappen, sofern Abhängigkeiten und Datenverträge gesichert sind. Die konkrete Reihenfolge der MDP-Pakete wird nach der Bestands- und Umgebungsprüfung bestätigt.


## 17.12 Quellenbasierte Ergänzung der MDP-Arbeitspakete

Der Quellenimport macht zusätzliche Arbeitspakete bzw. Teilpakete sichtbar. Sie werden nicht als starre neue Reihenfolge verstanden; Abhängigkeiten und frühe vertikale Tests bestimmen die tatsächliche Reihenfolge.

- Quest-System: Quest Runtime, World State, Decision Ledger, Knowledge, Dialog Runtime, Editor und Migration.
- Datenmigration: Item-/Materialkataloge, Rezept-/Facility-Daten, IDs, Referenzen und Versionsfamilien.
- 3D-Spielsteuerung: Third-Person-Rig, Hybrid-Zoom, Navigation, Vertikalität, Treppen, Kamera-Kollision und Mehrstöckigkeit.
- Bausystem: Gebäudekataloge, Baupläne, Platzierung, Baufortschritt, lokale Materialversorgung und Gebäudevalidierung.
- Living World: Ökologie, Population, Genetik, Meister-/Vorarbeitersystem, Karrieren und Krisenereignisse.
- Welt-/Wirtschaftsverknüpfung: regionale Spezialisierung, Außenposten, Warenlager, Transportaufträge, Karawanen und Routenrisiken.
- Dev-Editor: gemeinsame 3D-Kamera, Asset-Browser, Transformationswerkzeuge, Nav-/Kollisionsvisualisierung, Pinsel und versionierter Export.

Diese Pakete benötigen vor Implementierung eine genaue Abgrenzung, Akzeptanzkriterien, Datenverträge, Testfälle und Abhängigkeiten. Die Originalquellen liefern Fachideen und Beispiele; alte Engine- und Implementierungsanweisungen werden nicht fortgeschrieben.

## 17.13 Multiplayer als separate Scope-Entscheidung

Die ZIP enthält umfangreiche Multiplayer-Konzepte zu Gilden, Territorien, Diplomatie, kooperativem Bauen, Belagerungen, Serverereignissen und Netzwerkarchitektur. Diese Themen werden als optionale Erweiterungsrichtung dokumentiert. Sie dürfen nicht unbemerkt in die Singleplayer-first-Entwicklung einfließen oder die Kernarchitektur mit ungeprüften Serveranforderungen überfrachten.

Architekturentscheidungen sollen sinnvolle Erweiterbarkeit nicht unnötig verhindern, aber keine Multiplayer-Funktion gilt als beschlossen, bevor Produktumfang, Betrieb, Kosten, Sicherheit und Spielstandmodell ausdrücklich festgelegt sind.

## Player Experience und Wiederentdeckbarkeit als Konzeptbereich

Das neue PECS-Arbeitskonzept aus Dokument 26 ist als systemübergreifender Konzeptbereich zu berücksichtigen. Es wird nicht als sofortiges zusätzliches Vollsystem parallel zu den bestehenden M00–M12-Paketen umgesetzt. Zunächst sind Begriffe, Systemverantwortung, Abhängigkeiten und Auswirkungen auf Gameplay, Simulation, Quests, Daten und Modding zu präzisieren.

Frühe Architekturentscheidungen müssen die Trennung zwischen Spielausrichtung, Spieler-Simulationstiefe und technischer Simulationsauflösung berücksichtigen. Ein späteres eigenständiges Arbeitspaket für PECS ist nach Definition der Fachverträge und eines repräsentativen Vertical-Slice-Szenarios zu planen. Die tatsächliche Priorisierung und Paketnummerierung bleibt offen.
