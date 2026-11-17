# 07 — Prozedurale Weltgenerierung

## 7.1 Grundsatz

**Leitplanke:** Die Weltkarte wird prozedural generiert. Ein von Hand gezeichnetes Weltkartenmodell oder ein verpflichtender Hybrid aus handgebauter Karte und Generator ist derzeit nicht vorgesehen. Werkzeuge dürfen Ergebnisse nachbearbeitbar machen; der zugrunde liegende Weltaufbau bleibt jedoch generativ und datengetrieben.

## 7.2 Gesamtkarte und spielbare Regionen

Die große geografische Weltstruktur wird früh definiert. Dazu gehören langfristig Kontinente, Inseln, Meere, Küsten, grobe Höhenzüge, Regionen und geplante Biomzuordnungen.

Nicht alle Gebiete werden von Anfang an vollständig generiert oder ausgeliefert:
- **Geplant/gesperrt:** minimale Regionsdefinition, stabile ID, geografische Planungsdaten und ggf. grobe Biom-/Schwierigkeitsmetadaten. Kein vollständiges 3D-Terrain, keine Gebäude, NPCs oder volle Simulation.
- **In Entwicklung:** Region kann Generatorvorschauen und Testinhalte besitzen; diese sind noch nicht automatisch veröffentlichte Weltzustände.
- **Entwickelt/freigegeben:** vollständiges Terrain, Vegetation, Wasser, POIs, Siedlungen, Navigation, Inhalte und vorgesehene Simulation.
- **Veröffentlicht/persistiert:** Änderungen und relevante Ergebnisse bleiben stabil und dürfen durch spätere Generatorläufe nicht unbeabsichtigt verändert werden.

Die geografische Gesamtkarte ist von der tatsächlich geladenen und gerenderten 3D-Welt zu trennen.

## 7.3 Determinismus und Regionsstabilität

Jede Welt und Region benötigt stabile IDs und reproduzierbare Seeds. Generatorversionen und relevante Parameter müssen gespeichert werden. Spätere Änderungen am Generator dürfen veröffentlichte Regionen nicht unerwartet umformen.

Daraus folgen:
- Welt-Seed und Regions-Seed;
- Generatorversion und Version der Daten-/Regelsätze;
- dokumentierte Abhängigkeiten der Generationsstufen;
- Persistenz freigegebener Regionsergebnisse;
- Migrationsstrategien bei Generatorupdates;
- deterministische Referenzen zwischen Regionen und benachbarten Geografiedaten.

Gebietsgrenzen, Flüsse, Berge, Küsten, Biome, Wege und Siedlungspositionen, die für bereits freigegebene Inhalte relevant sind, dürfen nicht ohne geplante Migration verschoben werden.

## 7.4 Generationspipeline

Empfohlene logische Stufen, deren konkrete Algorithmen noch zu evaluieren sind:

1. Weltparameter und Seed.
2. Großmaßstäbliche Land-/Wasserverteilung.
3. Kontinente, Inseln, Küsten und Meere.
4. Höhen- und Geländestruktur.
5. Klima- und Feuchtigkeitsfelder.
6. Biomverteilung auf Basis der Biome-Katalogdefinitionen.
7. Flüsse, Seen, Wasserläufe und Entwässerung.
8. regionale Gelände- und Materialverteilung.
9. Ressourcen-, Vegetations- und Faunaverteilung.
10. Gefahren-/Schwierigkeitszonen als eigene Layer.
11. POIs, Ruinen, Dungeons und geeignete Siedlungsräume.
12. Siedlungen, Infrastruktur und Wege.
13. Terrain-Meshes, Materialien, Vegetation, Navigation und Streamingdaten.
14. Validierung, Vorschau, Freigabe und Persistenz.

Die Abfolge ist eine Architekturgliederung, kein Festlegen auf einen spezifischen Algorithmus.

## 7.5 Biome

Biome werden zuerst im **Biome Catalogue/Editor** definiert und anschließend nach konfigurierbaren Kriterien über die Welt verteilt. Ein Biom ist eine ökologische/geografische Definition und darf nicht mit Gefahr oder Charakterstufe gleichgesetzt werden.

Ein Biomprofil kann enthalten:
- Klima: Temperatur, Niederschlag, Luftfeuchtigkeit und saisonale Ausprägung;
- Geografie: Höhenlage, Hangneigung, Küstennähe und Geländeformen;
- Boden, Gestein, Wasser und Oberflächenmaterialien;
- Vegetation und Verteilung;
- Ressourcen und Vorkommen;
- Tiere, Kreaturen und ökologische Beziehungen;
- Eignung für Siedlungen, Landwirtschaft, Infrastruktur und Besiedlung;
- Gefahrenarten, Umweltrisiken und mögliche Begegnungen;
- Übergangsregeln zu benachbarten Biomen.

Die endgültige Biomenliste ist offen. Keine beispielhafte Liste darf als beschlossen gelten.

## 7.6 Gefahr und Schwierigkeit

Gefahr-/Schwierigkeitsdaten werden als separate Layer oder Profile modelliert. Kriterien können Kreaturenstärke, Fraktionsaktivität, Umweltgefahr, Ereignisdichte, Ressourcenrisiko und erwartete Spielherausforderung sein. Übergänge können graduell, zoniert oder ereignisabhängig sein.

Ein Biom kann unterschiedliche Gefahrenprofile tragen. Die Verteilung muss nachvollziehbar und im Editor sichtbar sein.

## 7.7 Höhenmodell und 3D-Terrain

Das Spiel ist vollständig dreidimensional. Terrain muss Höhenunterschiede, Steigungen, Felswände, Täler, Hochebenen, Höhlen, Tunnel, Brücken und Übergänge zu Bauwerken unterstützen. Terrain-Daten, sichtbares Mesh, Kollisionskörper, Navigation, Wasser und Materialdarstellung sind aufeinander abzustimmen.

Der technische Ansatz (Unity Terrain, Mesh-basierte Chunks oder eine Kombination) ist durch einen Prototyp und Performance-/Workflowtests zu bestimmen. Die Entscheidung darf nicht ausschließlich anhand der Editorbequemlichkeit getroffen werden.

## 7.8 Wasser und Gewässer

Wasserflächen, Küsten, Seen und Flüsse müssen mit Höhenmodell, Navigation und Biomen zusammenarbeiten. Flussverläufe müssen deterministisch und regionsübergreifend konsistent sein. Wasser ist als Welt- und Gameplay-System zu betrachten: Übergänge, Querungen, Küstenzugänge, Ressourcen und ggf. Gefahren.

## 7.9 Streaming und Regionen

Die Runtime lädt und entlädt Weltabschnitte nach Relevanz. Region und Chunk sind unterschiedliche Begriffe: Region ist primär ein inhaltlicher/geografischer Container; Chunk ein technischer Lade- und Renderbereich. Ihre Größen sind noch nicht festgelegt.

Streaming muss berücksichtigen:
- Terrain- und Materialdaten;
- Vegetation und Props;
- Gebäude/POIs;
- NPCs und Kreaturen;
- Navigation und Kollisionsdaten;
- Audio- und Atmosphärendaten;
- persistente Veränderungen;
- Quests und aktive Ereignisse.

## 7.10 Azgaar und externe Kartenwerkzeuge

Eine mit Azgaar erzeugte Karte kann als Referenz, Eingabequelle oder Ausgangspunkt für Kartendaten dienen, ist jedoch nicht automatisch die endgültige 3D-Welt. Zu prüfen sind Exportformate, Lizenzbedingungen, Datenqualität, Skalierung, Koordinatentransformationen, Höhen-/Flussdaten und die Frage, welche Daten übernommen, neu generiert oder nur als Planungsinformation genutzt werden.

Die World-Generator-Tools müssen sowohl eine reine prozedurale Erzeugung als auch die kontrollierte Nutzung importierter Kartengrundlagen unterstützen, ohne den Grundsatz „prozedurale Weltkarte“ aufzugeben.

## 7.11 Validierung

Vor Freigabe einer Region sind mindestens zu prüfen:
- geografische Kontinuität an Regionsgrenzen;
- Wasser- und Höhenübergänge;
- Biomgrenzen und Übergänge;
- Erreichbarkeit und Navigationskonnektivität;
- Spawn- und POI-Kollisionen;
- Ressourcen-/Faunaverteilung;
- Siedlungseignung;
- Quest- und Referenzintegrität;
- Performance-/Speicherbudgets;
- deterministische Wiederholbarkeit.

## 7.12 Offene technische Parameter

Weltmaßstab, Kartenauflösung, Region-/Chunkmaß, Höhenauflösung, Generatoralgorithmen, Streamingradien, Simulationsraten und konkrete Biome bleiben offen, bis Testprototypen und Zielplattformen belastbare Werte liefern.
