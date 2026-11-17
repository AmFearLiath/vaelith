# 08 — Editor- und Tool-Suite

## 8.1 Ziel und Qualitätsanforderung

Die interne Editor-Suite ist ein zentrales Produktionswerkzeug. Jeder Editor muss vollständige reale Workflows ermöglichen. Er benötigt Datenmodell, Navigation/Ansichten, Erstellen/Bearbeiten/Löschen, Validierung, Referenzauflösung, Speichern/Laden, Undo/Redo soweit sinnvoll, Fehlermeldungen, Vorschau, Debugging und Integration in andere Editoren und Runtime.

Ein Editor ist nicht fertig, wenn lediglich ein Fenster geöffnet werden kann. Die Abnahmekriterien stehen in Kapitel 18.

## 8.2 Gemeinsame Plattform

Alle Editoren verwenden:
- kanonische Datenmodelle und stabile IDs;
- gemeinsame Asset-/Content-Browser;
- einheitliches Referenz- und Dependency-System;
- gemeinsame Validierungs- und Fehlermeldungsdarstellung;
- zentrale Versionierung und Migrationsregeln;
- standardisierte Import-/Exportfunktionen;
- gemeinsame Undo-/Änderungshistorie, soweit technisch möglich;
- gemeinsame Such-, Filter- und Taggingfunktionen;
- projektweite Einstellungen und Berechtigungen.

Es dürfen keine unabhängigen Editor-Datenbanken entstehen, die dieselben Inhalte widersprüchlich speichern.

## 8.3 World Editor

Aufgaben:
- Weltkarte, Kontinente, Inseln, Meere und Küsten inspizieren;
- geografische Layer und Regionsgrenzen anzeigen;
- 2D- und 3D-Ansichten;
- Welt-/Regions-Seeds und Generatorparameter verwalten;
- Biom- und Gefahrenlayer visualisieren;
- Regionen planen, sperren, freigeben und Entwicklungsstatus verfolgen;
- Generatorvorschauen auslösen und vergleichen;
- Karten-/Referenzdaten importieren;
- Grenz-, Fluss-, Höhen- und Kontinuitätsvalidierung anzeigen;
- Regions- und Streamingdiagnostik bereitstellen.

## 8.4 Biome Editor / Biome Catalogue

Aufgaben:
- Biome anlegen und bearbeiten;
- Klima, Gelände, Boden, Wasser, Vegetation, Ressourcen und Fauna definieren;
- Eignung für Siedlung, Landwirtschaft und Infrastruktur festlegen;
- ökologische Beziehungen und Gefahrenarten referenzieren;
- Biomübergänge und Verteilungsregeln verwalten;
- Beispielvorschauen und Verteilungsvalidierung anbieten;
- Abhängigkeiten zu Assets und Kreaturen anzeigen.

## 8.5 Settlement Editor

Aufgaben:
- Städte, Dörfer, Außenposten und Siedlungsräume definieren;
- Bezirke, Grundstücke, Gebäude, Plätze und Straßen verknüpfen;
- Bevölkerung, Berufsprofile und Bevölkerungsrollen verwalten;
- Infrastruktur, Versorgung und Wirtschaft konfigurieren;
- Siedlungsentwicklung und Wachstumsbedingungen simulieren;
- Siedlungsdaten mit World, Building, NPC, Route und Quest referenzieren.

## 8.6 Building Editor

Aufgaben:
- modulare Gebäudekomponenten und Baugruppen definieren;
- Räume, Stockwerke, Türen, Fenster, Treppen, Dächer, Fassaden und Innenräume erstellen;
- Platzierung, Raster/Snap, Rotation und Höhenbezug;
- Kollision, Begehbarkeit, NavMesh-/Navigationsanschlüsse und Interaktionen validieren;
- Blueprints speichern, laden, versionieren und instanziieren;
- Material-/Texturvarianten verwalten;
- Innen-/Außenansichten und Vorschauen anbieten.

Der Editor muss mehrgeschossige 3D-Gebäude und räumliche Übergänge unterstützen.

## 8.7 Gemeinsamer Vaelith Building Editor für Schloss und Dorf

Castle Build Mode und Village Build Mode besitzen ein gemeinsames Editorfundament. Gemeinsame Werkzeuge umfassen Platzierung, Terrain-/Fundamentprüfung, Dekoration, Material-/Texturauswahl, Wege, Blueprints und Speichern. Profile unterscheiden Gebäudekataloge, Funktionen, Regeln und verfügbare Strukturen.

Schloss- und Siedlungsbau dürfen nicht in getrennte Datenbanken oder voneinander unabhängige Bauwerkzeuge auseinanderlaufen. Gemeinsam nutzbare Dekorationen und Basiskomponenten sollen wiederverwendbar sein.

## 8.8 NPC Editor

Aufgaben:
- NPC-Definitionen, Attribute und Erscheinungsbild;
- Ausrüstung und Inventarreferenzen;
- Persönlichkeit, Bedürfnisse und Beziehungen;
- Berufe, Aufgaben und Tagesabläufe;
- Fraktions- und Siedlungszugehörigkeit;
- Dialoge, Questverknüpfungen und Verhalten;
- Spawn-/Platzierungsregeln;
- Vorschau und Verhaltenssimulation.

## 8.9 Quest Editor

Aufgaben:
- Questdefinitionen und Questketten;
- Ziele, Bedingungen, Trigger und alternative Lösungen;
- Dialoge, NPCs, Orte, Items, Fraktionen und Belohnungen referenzieren;
- Konsequenzen und Weltzustandsänderungen definieren;
- Ablaufgraph und Abhängigkeiten visualisieren;
- Fehler bei fehlenden Referenzen/unerreichbaren Zuständen erkennen;
- Quests simulieren, pausieren, Schritt für Schritt ausführen und Laufzeitstatus untersuchen.

## 8.10 Route & Travel Editor

Aufgaben:
- Straßen, Pfade, Handelsrouten und Patrouillen definieren;
- Start-/Zielpunkte und Übergänge validieren;
- Reisezeit, Gefahr, Zugänglichkeit und Verkehrstypen verwalten;
- NPC-Routinen mit Navigationsdaten verbinden;
- Regionsgrenzen und Höhenunterschiede berücksichtigen.

## 8.11 POI Editor

Aufgaben:
- Dungeons, Ruinen, Höhlen, Landmarken, Geheimnisse und Ereignisorte;
- Spawn-, Interaktions- und Questpunkte;
- Ressourcenorte und besondere Weltobjekte;
- Innenräume und Eingänge;
- Referenzen zu Region, Navigation, NPC, Kreatur und Quest.

## 8.12 Weitere Fach-Editoren

Weitere erforderliche bzw. zu prüfende Editoren:
- Items und Ausrüstung;
- Waffen, Rüstungen, Schilde und Schmuck;
- Kreaturen und Tiere;
- Animationen und Rigging;
- Dialoge und Story;
- Fraktionen/Königreiche;
- Wirtschaft und Produktion;
- Landwirtschaft und Zucht;
- Ressourcen und Crafting/Rezepte;
- Loot und Belohnungen;
- Wetter und Jahreszeiten;
- Dungeon-/Höhlengenerierung;
- Beleuchtung und Atmosphäre;
- Audio/Sound;
- Mod-/Plugin-Verwaltung.

Ob jede Funktion ein eigenständiges Fenster erhält oder als Fachbereich eines größeren Editors organisiert wird, ist anhand realer Produktionsabläufe zu entscheiden. Die Datenbasis bleibt gemeinsam.

## 8.13 Entwickler- und Debugwerkzeuge

Mindestens zu prüfen/planen:
- Debugkonsole und strukturierte Logs;
- Live-Inspektoren für Entity-, NPC-, Kreaturen- und Weltzustände;
- Weltzeitsteuerung und Simulationsgeschwindigkeit;
- freie Kamera, Teleport, Spawn von NPCs/Kreaturen;
- Quest-/Event-Simulator;
- World-Generation- und Regiondiagnostik;
- Referenz-/Dependency-Analyse;
- Profiling und Performanceansichten;
- Testwelten und automatisierte Szenarien;
- Daten-/Weltzustandsvergleich;
- Speicherstanddiagnostik.

## 8.14 Integration und Referenzvalidierung

Beispiel: Eine Stadt wird im Settlement Editor erstellt, liegt über stabile Koordinaten in einer Region des World Editors, nutzt Gebäude aus dem Building Editor, beherbergt NPCs, ist über Route Editor erreichbar, wird von Quest Editor referenziert und besitzt Wirtschafts-/Simulationsdaten.

Der zentrale Validator prüft unter anderem:
- Quest referenziert existierenden NPC;
- NPC verweist auf gültige Siedlung und Berufs-/Arbeitsplatzdefinition;
- Gebäude ist in zulässiger Lage platzierbar;
- Route hat gültige Endpunkte und durchgängige Navigation;
- Kreatur und Biom sind kompatibel, sofern Regeln dies verlangen;
- Item-/Reward-Referenzen existieren;
- Blueprints und Assets sind verfügbar und kompatibel.

## 8.15 Editor-Abnahme

Für jeden Editor muss eine dokumentierte Workflowprüfung existieren: Inhalt erstellen, bearbeiten, validieren, speichern, erneut laden, in anderem Editor referenzieren, in Runtime testen, fehlerhaften Zustand absichtlich erzeugen und Diagnose prüfen. Details siehe Kapitel 18.

## 8.16 Editorübergreifende Bedien- und Workflowstandards

Alle Fach-Editoren sollen sich trotz unterschiedlicher Aufgaben konsistent bedienen lassen. Gemeinsame Konzepte sind beispielsweise Auswahl, Suche, Filter, Inspektor, Vorschau, Validierung, Änderungsverlauf und Referenznavigation.

Ein Editorworkflow muss den Nutzer vom Auffinden eines Datensatzes bis zur Verwendung in abhängigen Systemen begleiten. Dazu gehören:
- direkte Navigation zu referenzierten Datensätzen;
- Anzeige eingehender und ausgehender Abhängigkeiten;
- verständliche Fehler mit betroffenen IDs und Pfaden;
- Vorschau vor Übernahme riskanter Änderungen;
- Speichern, Verwerfen und Wiederherstellen von Änderungen;
- Kennzeichnung ungespeicherter oder ungültiger Zustände;
- nachvollziehbare Meldungen bei fehlenden Assets oder inkompatiblen Versionen.

Gemeinsame Bedienstandards dürfen fachliche Unterschiede nicht einebnen. Ein World Editor benötigt andere räumliche Werkzeuge als ein Quest Editor, soll aber dieselben Grundprinzipien für Datenintegrität und Feedback verwenden.

## 8.17 Gemeinsamer Daten- und Referenzbrowser

Die Suite benötigt einen zentralen Browser für kanonische Datensätze und ihre Referenzen. Er soll Suche nach ID, Name, Typ, Tags und weiteren fachlichen Eigenschaften ermöglichen.

Der Browser muss mindestens:
- Datensätze nach Typ und Fachgebiet filtern;
- stabile IDs und Herkunft anzeigen;
- Referenzen öffnen und Abhängigkeiten visualisieren;
- verwaiste und doppelte Referenzen auffinden;
- Verwendungsorte eines Datensatzes auflisten;
- Änderungen und Versionen vergleichen;
- Mod-/Paketzugehörigkeit kenntlich machen.

Änderungen an gemeinsam verwendeten Daten müssen in allen betroffenen Editoren sichtbar werden. Lokale Kopien derselben Definition sind zu vermeiden.

## 8.18 Import, Export und Migrationswerkzeuge

Import-/Exportfunktionen sind Teil der Editorplattform und keine nachträglichen Hilfsskripte. Sie müssen Formate, Versionen, Herkunft und Validierungsergebnisse dokumentieren.

Erforderlich sind je nach Fachgebiet:
- Importvorschau mit Zuordnung erkannter Felder und Referenzen;
- Erkennung vorhandener IDs und möglicher Duplikate;
- explizite Regeln für Zusammenführen, Ersetzen und Ergänzen;
- Fehler- und Warnbericht vor dem Commit;
- Export mit Schema-/Paketversion;
- Migrationsvorschau und Sicherung des Ausgangsstands;
- nachvollziehbare Protokolle und Rücknahmeoptionen, soweit möglich.

Bestehende JSON-Daten dürfen nicht stillschweigend umgeschrieben oder reduziert werden. Der Importer muss unbekannte Felder und nicht unterstützte Inhalte sichtbar behandeln.

## 8.19 World- und Biome-Editor: spezielle Anforderungen

World Editor und Biome Editor benötigen synchronisierte 2D-/3D-Ansichten mit auswählbaren Layern. Änderungen an Weltparametern oder Biomprofilen müssen ihre Auswirkungen auf Regionen und abhängige Inhalte sichtbar machen.

Zu unterstützen sind:
- Seed- und Profilverwaltung;
- Layer für Höhenlage, Wasser, Klima, Biome, Gefahr und Ressourcen;
- Regions- und Chunkgrenzen;
- Generatorvorschau mit Vorher-/Nachhervergleich;
- Nachbarregionen- und Kontinuitätsdiagnostik;
- Anzeige geplanter, in Entwicklung befindlicher und freigegebener Regionen;
- Schutz veröffentlichter Regionen vor unbeabsichtigter Überschreibung.

## 8.20 Simulation und Test im Editor

Fach-Editoren sollen relevante Regeln ohne vollständigen Spielstart testen können, soweit das fachlich sinnvoll und technisch zuverlässig möglich ist. Beispiele sind Questabläufe, NPC-Tagespläne, Produktionsketten, Zuchtregeln, Routen und Generatorparameter.

Simulationen müssen:
- Testdaten von produktiven Daten trennen;
- verwendete Eingaben, Seeds und Regelversionen anzeigen;
- pausieren, schrittweise laufen und zurücksetzen können;
- erwartete und tatsächliche Ergebnisse darstellen;
- keine unbeabsichtigten Änderungen an echten Spielständen erzeugen;
- Fehler und nicht unterstützte Fälle eindeutig kennzeichnen.

Eine Editorvorschau ersetzt nicht den Runtime-Test. Die Abnahme verlangt weiterhin den Einsatz der Daten im tatsächlichen Spiel.

## 8.21 Rollen, Berechtigungen und sichere Änderungen

Die Editor-Suite soll Änderungen nachvollziehbar und kontrollierbar machen. Für Team-/Projektworkflows sind Rollen und Berechtigungen zu prüfen, insbesondere für Freigaben, globale Daten, veröffentlichte Regionen und Mod-/Paketverwaltung.

Unabhängig von einer späteren Mehrbenutzerlösung müssen riskante Operationen geschützt sein:
- Löschen oder Umbenennen referenzierter Datensätze;
- Änderungen an stabilen IDs;
- Überschreiben freigegebener Weltinhalte;
- Massenimporte und Massenänderungen;
- Schema- und Generatorversionen;
- Änderungen an gemeinsam genutzten Assets.

Vor solchen Aktionen sind Auswirkungen und betroffene Referenzen anzuzeigen. Eine Bestätigung allein ersetzt keine Backup- und Migrationsstrategie.

## 8.22 Erweiterbarkeit und Modding

Die Editorplattform muss Erweiterungen berücksichtigen, ohne den Kern von Vaelith von beliebigen Plugins abhängig zu machen. Mod-/Content-Pakete benötigen definierte Metadaten, Versionen, Abhängigkeiten, Konfliktinformationen und Validierung.

Datenmods und ausführbare Code-Mods sind getrennt zu behandeln. Die Editor-Suite darf keine Sicherheitsgarantie für beliebigen In-Process-Code suggerieren. Offizielle Modding- und API-Regeln werden in Dokument 11 festgelegt.

## 8.23 Gemeinsame Definition of Done für Fach-Editoren

Ein Fach-Editor ist erst abnahmefähig, wenn der reale Workflow nachweislich funktioniert:
1. Datensatz oder Inhalt neu anlegen.
2. Bestehende Inhalte öffnen und vollständig bearbeiten.
3. Referenzen und Abhängigkeiten auflösen.
4. Vorschau und fachliche Validierung ausführen.
5. absichtlich fehlerhafte Daten erzeugen und verständliche Diagnose erhalten.
6. Änderungen speichern, schließen und erneut laden.
7. Daten in mindestens einem abhängigen Editor verwenden.
8. Daten in Runtime oder einem repräsentativen Testsystem einsetzen.
9. Änderungen vergleichen und dokumentieren.
10. Fehlerfälle und bekannte Grenzen protokollieren.

Nicht anwendbare Schritte müssen begründet werden. Ein Fenster, eine Formularansicht oder ein erfolgreicher Speichervorgang allein ist keine vollständige Editorfunktion.

## 8.24 Schrittweise Entwicklung und visuelle Prüfbarkeit

Die Editor-Suite wird in kleinen, eigenständig prüfbaren Arbeitspaketen aufgebaut. Jeder Editor erhält früh eine tatsächlich bedienbare Zwischenversion, damit Funktionen, Layout, räumliche Werkzeuge und Arbeitsabläufe geprüft werden können.

Ein Arbeitspaket soll möglichst einen abgeschlossenen Workflow liefern, beispielsweise Datensatz anlegen, Vorschau öffnen, validieren, speichern und erneut laden. Nicht integrierte Bereiche und Platzhalter sind sichtbar zu kennzeichnen. Feedback und Korrekturen werden vor dem Ausbau abhängiger Funktionen berücksichtigt.

## 8.25 Offene Entscheidungen

| ID | Thema | Status |
|---|---|---|
| EDITOR-001 | Technische Basis der Editor-Suite innerhalb/außerhalb des Unity-Editors | Architekturentscheidung erforderlich |
| EDITOR-002 | Gemeinsames UI-/UX-System und Layoutstandards | Prototyp/Abstimmung erforderlich |
| EDITOR-003 | Gemeinsames Referenz- und Dependency-Browser-Konzept | Technische Spezifikation erforderlich |
| EDITOR-004 | Undo/Redo-Umfang und Änderungs-/Transaktionsmodell | Technische Prüfung erforderlich |
| EDITOR-005 | Import-/Exportformate und Migrationsworkflow je Fachgebiet | Quellenabgleich erforderlich |
| EDITOR-006 | Berechtigungs- und Freigabemodell | Offen |
| EDITOR-007 | Umfang von Simulationen direkt in Fach-Editoren | Workflowprüfung erforderlich |
| EDITOR-008 | Erweiterungspunkte für Datenmods und Code-Mods | Abgleich mit Dokument 11 erforderlich |
| EDITOR-009 | Gemeinsame Suche, Tags und Metadatenstandards | Technische Spezifikation erforderlich |
| EDITOR-010 | Automatisierte Editor-Workflowtests und Testdatenverwaltung | QA-Spezifikation erforderlich |


## 8.26 Gemeinsamer Änderungslebenszyklus und Datenintegrität

Alle Fach-Editoren verwenden die in Dokument 09 beschriebenen gemeinsamen Regeln für Entwurf, Validierung, Vorschau, Übernahme und Änderungsprotokoll. Fachspezifische Workflows ergänzen diese Regeln, ersetzen sie aber nicht.

Bei jeder Änderung an gemeinsam referenzierten Datensätzen muss der Editor:
- betroffene Referenzen und abhängige Systeme anzeigen;
- zwischen Definition, Instanz und persistentem Weltzustand unterscheiden;
- mögliche Auswirkungen auf bestehende Spielstände und veröffentlichte Regionen kenntlich machen;
- ungültige oder unvollständige Änderungen vor der Übernahme blockieren oder ausdrücklich als nicht freigabefähig markieren;
- die Änderung mit stabilen IDs und nachvollziehbarer Herkunft speichern.

Ein Editor darf eine Änderung nicht als erfolgreich übernommen melden, wenn nur seine lokale Ansicht aktualisiert wurde, die kanonische Datenquelle aber unverändert oder inkonsistent geblieben ist.

## 8.27 Testdaten, Produktionsdaten und sichere Vorschau

Die Trennung von Test- und Produktivdaten gilt für alle Fach-Editoren und ihre Simulatoren. Testläufe müssen ihre Datenbasis, Seed-/Regelversionen und Ausführungsumgebung kenntlich machen.

Vorschauen dürfen produktive Daten nur verändern, wenn der Nutzer ausdrücklich eine Übernahme ausführt und die betroffenen Änderungen vorher nachvollziehen kann. Reset- und Wiederherstellungsfunktionen müssen klar angeben, welchen Datenbereich sie betreffen.

Die Runtime-Abnahme bleibt erforderlich: Eine im Editor erfolgreiche Vorschau beweist nicht, dass derselbe Datensatz im Spiel korrekt geladen, gespeichert und verwendet wird.


## 8.28 Quest Editor — vollständiger Fachworkflow

Der Quest Editor ist ein vollwertiges Authoring- und Diagnosewerkzeug. Er umfasst Quest-/Questlinien-Browser, Questgraph, Objective-Gruppen und Abhängigkeiten, Condition Builder, Decision-/Consequence-Editor, Dialoggraph, Knowledge-Verwaltung, World-Action-/Reward-Referenzen, lokalisierte Texte, NPC-/Fraktions-/Item-/Regionsreferenzen, Ablaufvorschau, Pfadprüfung, Simulation, Live-Debugger, Eventverlauf, Schema- und Referenzvalidierung, Versionsvergleich sowie Import/Export. Details stehen in Dokument 25.

Ein Quest Editor gilt nicht als vollständig, wenn er lediglich JSON-Felder bearbeitet. Er muss unerreichbare Knoten, Zyklen, Softlocks, widersprüchliche Bedingungen, fehlende Referenzen, ungenutzte Inhalte und nicht abgedeckte Endzustände sichtbar machen.

## 8.29 Gemeinsame 3D-Dev-Tools

Die Editor-Suite erhält eine gemeinsame freie 3D-Editor-Kamera, Objektselektion, Transform-Gizmos, Duplizieren/Löschen, Asset-Palette mit Vorschau, Terrain-Ausrichtung sowie Kollisions-/Navigationsvisualisierung. Spezialisierte Pinsel- und Pfadwerkzeuge werden als gemeinsame Infrastruktur bereitgestellt, soweit Fach-Editoren sie benötigen.

## 8.30 Produktions- und Katalogeditoren

Item-, Material- und Rezeptdaten benötigen Browser und Editoren mit Versionsvergleich, Referenzprüfung, Rezept-/Produktionsgraph, Facility-Zuordnung, Import/Export, Migrationsvorschau und Validierungsbericht. Die Pflege darf nicht ausschließlich über Roh-JSON erfolgen müssen. Datenverträge und Migration sind in Dokument 24 beschrieben.