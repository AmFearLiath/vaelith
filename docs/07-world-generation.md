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

## 7.13 Weltkoordinaten und räumliche Referenzen

Die Welt benötigt ein über Regionen und Generatorversionen hinweg stabiles Koordinatensystem. Weltkoordinaten, Regionskoordinaten und technische Chunkkoordinaten sind getrennt zu behandeln und eindeutig ineinander überführbar.

Zu definieren und zu testen sind:
- Ursprung, Achsenorientierung und Maßeinheiten;
- globale Koordinaten und lokale Koordinaten je Region/Chunk;
- Höhenbezug und vertikale Referenzierung;
- Koordinatentransformationen für importierte Karten;
- Toleranzen an Regions- und Chunkgrenzen;
- stabile IDs für geografische Features und POIs.

Ein Objekt darf nicht allein über seine aktuelle Chunkzugehörigkeit identifiziert werden. Streaming- oder Aufteilungsänderungen dürfen seine dauerhafte Identität nicht verändern. Geografische Referenzen müssen auch nach Verschiebung technischer Ladegrenzen gültig bleiben.

## 7.14 Regionale Generierungsverträge

Jede Generierungsstufe muss definierte Eingaben, Ausgaben, Abhängigkeiten und Validierungsregeln besitzen. Eine nachgelagerte Stufe darf keine bereits festgelegte geografische Grundlage unbemerkt verändern.

Ein Generierungsvertrag dokumentiert mindestens:
- Eingabeparameter und relevante Seed-Ableitung;
- verwendete Generator- und Regelsatzversion;
- erzeugte Daten und stabile Referenzen;
- Abhängigkeiten zu Nachbarregionen;
- erlaubte nachgelagerte Änderungen;
- Fehler- und Warnbedingungen;
- Reproduzierbarkeit und Validierung.

Regionen müssen an Grenzen gemeinsame geografische Informationen nutzen können. Flüsse, Gebirgszüge, Küsten und andere fortlaufende Features dürfen nicht unabhängig pro Region entstehen, wenn dadurch sichtbare Brüche entstehen würden.

## 7.15 Seeds und unabhängige Zufallsströme

Die Generierung soll nachvollziehbare Seed-Ableitungen verwenden. Ein globaler Seed allein darf nicht dazu führen, dass eine kleine Änderung in einem frühen Generierungsschritt sämtliche nachfolgenden Ergebnisse unkontrolliert verändert.

Zu prüfen ist eine Trennung in fachliche Zufallsströme, beispielsweise für Großgeografie, Klima, Biome, Wasser, Ressourcen, Vegetation, Fauna und POIs. Die konkrete Aufteilung ist technisch zu evaluieren.

Ziel:
- gleiche Eingaben und Versionen liefern reproduzierbare Ergebnisse;
- Änderungen an einem unabhängigen Generierungsbereich beeinflussen andere Bereiche möglichst nicht;
- einzelne Regionen und Features können gezielt reproduziert und verglichen werden;
- Generatorfehler lassen sich auf einen Seed-/Versions-/Parameterkontext zurückführen.

## 7.16 Weltkarte, Region und Chunk als getrennte Ebenen

Die Weltkarte beschreibt die globale geografische Struktur und Planungsinformationen. Regionen bilden fachliche und persistente Weltbereiche. Chunks sind technische Einheiten für Laden, Entladen, Rendern, Kollision und gegebenenfalls Simulation.

Diese Ebenen dürfen nicht gleichgesetzt werden:
- Eine Region kann aus vielen Chunks bestehen.
- Ein Chunk kann technische Grenzen überschreiten, sofern die Architektur dies sinnvoll vorsieht.
- Eine Region kann geplant sein, ohne dass ihre Chunks als 3D-Inhalte existieren.
- Eine Region kann teilweise entwickelt sein, ohne automatisch als veröffentlicht zu gelten.

Regionen besitzen fachliche Metadaten und Lebenszyklusstatus. Chunks besitzen technische Lade- und Ressourcenstatus. Die Zuordnung muss explizit und versionierbar sein.

## 7.17 Geländeformen, Erosion und natürliche Kontinuität

Die Weltgenerierung muss natürliche Zusammenhänge zwischen Höhenmodell, Wasser, Klima, Boden, Vegetation und Eignung berücksichtigen. Die konkrete Modellierung kann schrittweise erfolgen; ein optisch überzeugendes Einzelbild reicht nicht als Qualitätsnachweis.

Zu validieren sind unter anderem:
- plausible Höhenübergänge und Hangneigungen;
- Einzugsgebiete und Entwässerungsrichtungen;
- Flussquellen, Zusammenflüsse, Seen und Mündungen;
- Küstenverläufe und Übergänge zwischen Land und Wasser;
- natürliche Pässe, Täler und Barrieren;
- Eignung von Gelände für Wege, Siedlungen und Infrastruktur;
- Übergänge zwischen Höhenlage, Klima und Vegetation.

Erosion, Sedimenttransport und geologische Detailprozesse sind mögliche Generierungs- oder Simulationsverfahren, aber keine bereits festgelegte Pflichttechnik.

## 7.18 Klima, Wetter und saisonale Weltparameter

Langfristige Klimafelder und kurzfristiges Wetter sind zu unterscheiden. Klima beeinflusst unter anderem Biomverteilung, Vegetationspotenzial, Wasserhaushalt und regionale Eignung. Wetter ist ein zeitabhängiger Zustand und gehört zur Welt-/Simulationslogik.

Die Generierung kann Klimazonen und saisonale Profile vorbereiten. Laufendes Wetter darf die dauerhaft festgelegte geografische Identität einer veröffentlichten Region nicht unkontrolliert verändern.

Zu prüfen sind Abhängigkeiten von Breitengrad, Höhenlage, Meeresnähe, Wind- und Feuchtigkeitsmustern sowie Jahreszeiten. Konkrete Modelle und Parameter bleiben offen.

## 7.19 Ressourcen, Vegetation und Fauna

Ressourcen-, Pflanzen- und Tierverteilung muss aus geeigneten Weltbedingungen und fachlichen Profilen abgeleitet werden. Ein Biom definiert mögliche ökologische Eigenschaften, aber nicht zwingend eine überall identische Arten- oder Ressourcenliste.

Verteilung berücksichtigt bei Bedarf:
- Klima, Höhenlage, Boden, Wasser und Mikrohabitate;
- regionale Verfügbarkeit und Vorkommensgrenzen;
- ökologische Beziehungen und Populationsbedingungen;
- Seltenheit, Regenerations- und Erschöpfungsregeln;
- Siedlungs-, Produktions- und Questanforderungen;
- geschützte oder besonders wichtige Weltinhalte.

Die Generierung legt Ausgangsbedingungen fest. Laufende Populationen, Wachstum, Jagd und Ressourcenveränderungen werden anschließend durch die Simulation aus Dokument 06 fortgeschrieben.

## 7.20 Siedlungsräume, Wege und Erreichbarkeit

Geeignete Siedlungsräume sollen anhand geografischer und ökologischer Kriterien ermittelt werden können. Dazu zählen Gelände, Wasserzugang, Ressourcen, Klima, Gefahren, Platzangebot und Verbindung zu anderen Regionen.

Die Generierung kann Kandidaten und Eignungswerte liefern. Die tatsächliche Siedlungsplanung und Ausgestaltung erfolgt über die zuständigen Editoren und Datenmodelle. Ein Eignungswert ist keine automatische Garantie, dass eine Siedlung gebaut oder besiedelt wird.

Wege und Routen müssen Höhenunterschiede, Steigungen, Brücken, Flüsse, Engstellen und mögliche Sperren berücksichtigen. Erreichbarkeit ist nicht allein durch zweidimensionale Luftlinien zu bestimmen.

## 7.21 POI- und Inhaltsplatzierung

POIs wie Ruinen, Dungeons, Höhlen, Landmarken, Ressourcenorte und Geheimnisse benötigen Platzierungsregeln und stabile Referenzen. Regeln können Gelände, Biom, Klima, Geschichte, Zugänglichkeit, Gefahrenprofil und Abstände zu anderen POIs berücksichtigen.

Die Platzierung muss Kollisionen, unzugängliche Eingänge, ungültige Innen-/Außenübergänge und widersprüchliche Quest-/Siedlungsreferenzen erkennen. Story- oder questkritische Orte benötigen Schutz vor unbeabsichtigter Entfernung oder Verschiebung.

## 7.22 Importierte Kartengrundlagen und Azgaar-Daten

Importierte Karten werden als versionierte Eingabe-/Referenzdaten behandelt. Der Importprozess muss Originaldatei, Herkunft, Lizenz-/Nutzungsprüfung, Importzeitpunkt, Formatversion, Transformationen und vorgenommene Ableitungen dokumentieren.

Vor einer Nutzung sind mindestens zu prüfen:
- Koordinatensystem, Maßstab und Projektion;
- Datenqualität und Vollständigkeit;
- Höhen-, Fluss-, Küsten- und Regionsinformationen;
- Umgang mit fehlenden oder widersprüchlichen Daten;
- Lizenz und zulässige Weiterverwendung;
- reproduzierbarer Import und Vergleich zur Quelle.

Ein Import darf nicht unbemerkt bestehende freigegebene Weltgeografie überschreiben. Der Nutzer muss erkennen können, welche Daten direkt übernommen, abgeleitet, verworfen oder neu generiert wurden.

## 7.23 Generierungsprofile, Vorschau und Freigabe

Ein Generierungsprofil bündelt die für eine Welt oder Region relevanten Parameter und Referenzen auf Regelsätze. Profile benötigen Versionierung, Vergleich und nachvollziehbare Änderungen.

Vor Freigabe müssen Vorschau und Validierung mindestens ermöglichen:
- 2D-Übersicht und relevante Layer;
- 3D-Terrainvorschau;
- Regionen- und Nachbargrenzenprüfung;
- Wasser-, Höhen- und Biomdiagnostik;
- Ressourcen-, Fauna- und POI-Verteilung;
- Erreichbarkeit und Navigationsprüfung;
- Performance- und Speicherabschätzung;
- Vergleich mit vorheriger Generierung.

Freigabe ist ein bewusster, protokollierter Schritt. Testgenerierungen dürfen veröffentlichte Daten nicht ersetzen.

## 7.24 Versionswechsel und geschützte Weltinhalte

Generatorupdates müssen zwischen nicht freigegebenen, in Entwicklung befindlichen und veröffentlichten Regionen unterscheiden. Für veröffentlichte Inhalte sind kontrollierte Migration, Kompatibilitätsprüfung und Wiederherstellungsplan erforderlich.

Eine Änderung an einem Algorithmus kann Auswirkungen auf abhängige Daten haben. Vor Übernahme müssen betroffene Regionen, POIs, Routen, Siedlungen, Quests, Ressourcen und Speicherstände ermittelt werden. Unbeabsichtigte Neugenerierung veröffentlichter Inhalte ist zu verhindern.

## 7.25 Offene Entscheidungen

| ID | Thema | Status |
|---|---|---|
| WORLD-001 | Weltmaßstab, Projektion und geografische Ausdehnung | Offen |
| WORLD-002 | Auflösung und Detailgrad der globalen Weltkarte | Technische Prüfung erforderlich |
| WORLD-003 | Regionengröße und Verhältnis zu technischen Chunks | Prototyp/Profiling erforderlich |
| WORLD-004 | Generatoralgorithmen für Kontinente, Höhenmodell und Küsten | Evaluierung erforderlich |
| WORLD-005 | Klima-, Wind-, Niederschlags- und Wasserhaushaltsmodell | Offen |
| WORLD-006 | Finale Biomenliste und Übergangsregeln | Gemeinsam festzulegen |
| WORLD-007 | Fluss-/Entwässerungsmodell und regionsübergreifende Kontinuität | Technische Spezifikation erforderlich |
| WORLD-008 | Ressourcen-, Vegetations- und Faunaverteilungsregeln | Fachlicher Abgleich erforderlich |
| WORLD-009 | POI-Dichte, Seltenheit und Schutz storykritischer Orte | Offen |
| WORLD-010 | Weltkoordinatensystem und Maßeinheiten | Technische Entscheidung erforderlich |
| WORLD-011 | Seed-Aufteilung und Stabilitätsgarantien bei Generatoränderungen | Technische Prüfung erforderlich |
| WORLD-012 | Azgaar-Importumfang, Exportformate und Lizenzprüfung | Quellen-/Lizenzprüfung erforderlich |
| WORLD-013 | Terrain-Technologie: Unity Terrain, Mesh-Chunks oder Kombination | Prototyp/Profiling erforderlich |
| WORLD-014 | Freigabe- und Migrationsverfahren veröffentlichter Regionen | Prozessentscheidung erforderlich |
| WORLD-015 | Kriterien für Siedlungseignung und Routenplanung | Offen |
