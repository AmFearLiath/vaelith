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
