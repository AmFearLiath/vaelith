# 10 — Unity-Architektur

## 10.1 Plattformwahl

**Leitplanke:** Vaelith wird als vollständiges 3D-Spiel in Unity entwickelt. Zu Projektbeginn prüft Claude die aktuell unterstützte stabile Unity-Version, Renderpipeline, kompatible Pakete, Scripting-Backend, Plattformen und Tooling. Nicht automatisch die neueste experimentelle Version wählen. Stabilität, Langzeitpflege, Asset-Kompatibilität und Modding sind mitzuberücksichtigen.

## 10.2 Architekturziele

- klare Trennung von Daten, Simulation, Gameplay, Darstellung und Tools;
- modulare Fachsysteme mit definierten Schnittstellen;
- stabile Daten- und Entity-Identität;
- deterministische Generator- und Simulationskomponenten, wo erforderlich;
- Streaming und skalierbare Simulation;
- Testbarkeit außerhalb vollständiger Spielabläufe;
- robuste Persistenz und Migration;
- kontrollierte Mod-Erweiterung;
- nachvollziehbare Logs, Telemetrie und Fehlerdiagnostik.

## 10.3 Layer-Vorschlag

Die genaue Assembly-/Namespace-Struktur entsteht aus dem ersten Architekturpaket. Logisch zu trennen sind:

1. **Core/Foundation:** IDs, Zeit, Ereignisse, Konfiguration, Logging, Save-Schnittstellen.
2. **Domain/Data:** kanonische Definitionen und Regeln.
3. **World:** Regionen, Terrain, Biome, Streaming, Navigation.
4. **Simulation:** NPCs, Ökologie, Wirtschaft, Produktion, Ereignisse.
5. **Gameplay:** Spieler, Kampf, Interaktion, Quests, Inventar, Magie.
6. **Content Runtime:** Laden/Validieren von Content und Assets.
7. **Presentation:** Rendering, Animation, UI, Audio, VFX.
8. **Tools/Editors:** interne Produktions- und Debugwerkzeuge.
9. **Mod Integration:** BepInEx-Anbindung und offizielle Vaelith Mod API.

Die Benennung ist ein Vorschlag für Verantwortlichkeitsgrenzen, kein festgelegtes Klassenlayout.

## 10.4 Renderpipeline und visuelle Technik

Renderpipeline und Renderfeatures sind anhand Zielhardware, gewünschter Bildqualität, Plattformen und Assetverfügbarkeit zu wählen. Der Agent muss einen repräsentativen Szenenprototyp aufbauen und Beleuchtung, Materialien, Transparenz, Vegetation, Wasser, Postprocessing und Performance vergleichen. Eine Entscheidung ist mit Version, Gründen und bekannten Einschränkungen zu dokumentieren.

## 10.5 Welt-Streaming

Regionen und technische Chunks sind voneinander zu abstrahieren. Streaming verwaltet Laden, Aktivieren, Deaktivieren, Entladen, Persistenz und Priorisierung. Es muss auch mit NPCs, Navigation, Audio, Animation und dynamischen Weltobjekten funktionieren.

## 10.6 Navigation und räumliche Systeme

Die dreidimensionale Welt benötigt koordinierte Terrain-, Kollisions-, Navigations- und Interaktionsdaten. Mehrgeschossige Gebäude, Brücken, Höhlen und vertikale Verbindungen müssen valide Navigationsübergänge besitzen. Ein visuell begehbarer Bereich darf nicht ohne Diagnose von Navigation ausgeschlossen sein.

## 10.7 Events und Systemkommunikation

Fachsysteme sollen über klar definierte Schnittstellen und Ereignisse kommunizieren. Globale, untypisierte Eventbus-Nutzung ohne klare Eigentümerschaft ist zu vermeiden. Ereignisse müssen bei Bedarf versionierbar, debugbar und für Mods kontrolliert exponierbar sein.

## 10.8 Konfiguration

Werte mit Balancing- oder Weltgeneratorrelevanz sollen nicht im Code verstreut sein. Sie werden typisiert, versioniert und über geeignete Konfigurations-/Editorwerkzeuge verwaltet. Kritische Werte benötigen Validierungsgrenzen und nachvollziehbare Defaults.

## 10.9 Build- und Releasekonfiguration

Entwicklungs-, Test- und Releasebuilds müssen unterscheidbare Einstellungen besitzen. Debugfunktionen dürfen nicht versehentlich in Releasebuilds verbleiben. Modding-Fähigkeiten, Logging, Assetbundles und Datenvalidierung müssen je Zielplattform überprüft werden.

## 10.10 Architekturentscheidungen

Keine konkrete Unity-Paketversion, ECS-/DOTS-Pflicht, Netzwerkarchitektur, Renderpipeline oder Persistenzbibliothek ist an dieser Stelle endgültig beschlossen. Claude erstellt einen begründeten Architekturentscheid anhand eines realistischen Prototyps und überprüft die Kompatibilität vor dem Ausbau.

## 10.11 Assembly-, Modul- und Abhängigkeitsregeln

Die logischen Layer aus Abschnitt 10.3 müssen in überprüfbare technische Abhängigkeitsregeln überführt werden. Höhere Präsentations- und Toolschichten dürfen Domainregeln nicht zur Laufzeit als alleinige Wahrheitsquelle definieren.

Zu dokumentieren sind:
- Modulverantwortung und öffentliche Schnittstellen;
- erlaubte und verbotene Abhängigkeiten;
- Regeln für gemeinsame Verträge und Datentypen;
- Umgang mit optionalen Modulen und plattformspezifischen Implementierungen;
- Testbarkeit ohne vollständige Unity-Szene;
- Versionierung und Migrationsregeln für Modulverträge.

Zyklische Abhängigkeiten und unkontrollierte Singleton-Verflechtungen sind zu vermeiden. Die konkrete Assembly-Aufteilung ist erst nach einem vertikalen Prototyp verbindlich festzulegen.

## 10.12 Lebenszyklus und Initialisierungsreihenfolge

Kernsysteme benötigen einen definierten Start-, Aktivierungs-, Deaktivierungs- und Shutdown-Lebenszyklus. Reihenfolge und Abhängigkeiten dürfen nicht zufällig von Szenenladefolge oder Script-Ausführungsreihenfolge abhängen.

Zu spezifizieren sind:
- Bootstrap und Prüfung der Laufzeitumgebung;
- Laden von Konfigurationen und Contentdefinitionen;
- Initialisierung von Savegame und Weltzustand;
- Aktivierung von Streaming, Simulation und Gameplay;
- Szenen-/Regionswechsel;
- geordnetes Speichern und Herunterfahren;
- Verhalten bei fehlgeschlagener Initialisierung.

Systeme müssen Abhängigkeiten deklarieren und bei fehlenden Voraussetzungen verständliche Fehler liefern. Teilweise initialisierte Spielzustände dürfen nicht als vollständig spielbereit gelten.

## 10.13 Asynchrone Verarbeitung und Threading

CPU-intensive oder I/O-lastige Aufgaben sind auf geeignete asynchrone bzw. nebenläufige Ausführung zu prüfen. Unity-Objekte und APIs mit Main-Thread-Anforderungen dürfen nicht unkontrolliert aus Hintergrundthreads verwendet werden.

Für jeden nebenläufigen Prozess sind Eingabedaten, Eigentümerschaft, Abbruchverhalten, Ergebnisübergabe und Fehlerbehandlung zu definieren. Dazu zählen insbesondere Weltgenerierung, Asset-/Contentladen, Streaming, Datenvalidierung und Simulationsberechnungen.

Datenrennen, doppelte Verarbeitung und veraltete Ergebnisse nach Szenen-/Regionswechseln müssen durch klare Lebenszyklen und Tests verhindert werden.

## 10.14 Szenen, Weltzustand und Präsentation

Szenen sind primär Präsentations- und Ladecontainer, nicht die alleinige Speicherung fachlicher Weltwahrheit. Dauerhafte Weltzustände müssen unabhängig von der aktuell geladenen Szene referenzierbar und speicherbar bleiben.

Zu prüfen sind:
- Szenenübergänge ohne Verlust persistenter Zustände;
- additive Szenen und Region-/Chunkstreaming;
- Wiederverwendung gemeinsamer Präsentationsobjekte;
- Trennung von statischen und dynamischen Weltinhalten;
- Referenzauflösung bei verzögert geladenen Objekten;
- Verhalten bei fehlenden oder beschädigten Szeneninhalten.

## 10.15 Navigation, Physik und Interaktionsräume

Die räumlichen Systeme müssen einen konsistenten Vertrag für Kollisionsgeometrie, Navigationsflächen, Bewegungsräume und Interaktionsreichweiten besitzen. Vertikale Verbindungen und mehrgeschossige Strukturen sind explizit zu testen.

Ein Objekt kann visuell vorhanden sein, ohne für Navigation oder Interaktion verfügbar zu sein. Solche Abweichungen müssen in Editor und Runtime diagnostizierbar sein. Änderungen an Terrain oder Gebäuden müssen abhängige Kollisions- und Navigationsdaten aktualisieren oder als ungültig markieren.

## 10.16 Logging, Diagnose und Telemetrie

Logs sollen fachliche Ereignisse, technische Fehler und Performanceinformationen unterscheidbar erfassen. Jede Meldung muss genügend Kontext enthalten, um betroffene IDs, Region, Modul, Version und Auslöser einzugrenzen, soweit verfügbar.

Telemetrie ist zweckgebunden, datensparsam und transparent zu gestalten. Externe Übertragung oder personenbezogene Erfassung wird nicht vorausgesetzt und benötigt eine gesonderte Produkt-/Datenschutzentscheidung. Entwicklungsdiagnostik muss auch ohne externe Dienste funktionieren.

## 10.17 Plattform- und Buildvarianten

Plattformabhängige Funktionen müssen über definierte Schnittstellen und geprüfte Implementierungen laufen. Buildprofile legen fest, welche Features, Moddingmöglichkeiten, Debugfunktionen und Contentformate verfügbar sind.

Jede unterstützte Zielplattform benötigt einen dokumentierten Kompatibilitätsstatus für:
- Renderpipeline und Grafikfeatures;
- Speicher- und Streamingverhalten;
- Eingabe und UI;
- Savegamepfade und Dateizugriffe;
- Scripting Backend und Modding;
- Audio, Controller und sonstige Geräteintegration.

Nicht unterstützte Kombinationen müssen früh erkannt und verständlich gemeldet werden.

## 10.18 Technische Prototypen und Architekturfreigabe

Architekturentscheidungen werden anhand kleiner, lauffähiger vertikaler Prototypen getroffen. Mindestens zu prüfen sind ein 3D-Regionsabschnitt mit Streaming, ein persistentes dynamisches Objekt, ein NPC-/Simulationsablauf, ein Content-/Editorworkflow und – soweit technisch möglich – ein Mod-API-Prototyp.

Für jeden Architekturentscheid werden Alternativen, Messwerte, Zielumgebung, Einschränkungen, Migrationskosten und Entscheidung dokumentiert. Ein theoretisch elegantes System gilt nicht als validiert, bevor es im repräsentativen Projektkontext getestet wurde.

## 10.19 Offene Architekturentscheidungen

| ID | Thema | Status |
|---|---|---|
| ARCH-001 | Finale Unity-Version und Upgrade-Politik | Projektstartprüfung erforderlich |
| ARCH-002 | Renderpipeline und Renderfeature-Set | Prototyp/Benchmark erforderlich |
| ARCH-003 | Assembly-/Modulzuschnitt und Abhängigkeitsregeln | Vertikaler Prototyp erforderlich |
| ARCH-004 | Einsatz von ECS/DOTS gegenüber klassischer Unity-Architektur | Profiling und Anwendungsfallprüfung erforderlich |
| ARCH-005 | Threading-/Job-System für Generator und Simulation | Prototyp/Profiling erforderlich |
| ARCH-006 | Szenen-, Streaming- und Weltzustandslebenszyklus | Technische Spezifikation erforderlich |
| ARCH-007 | Physik-, Kollisions- und Navigationslösungen | Prototyp erforderlich |
| ARCH-008 | Zielplattformen, Backends und Buildprofile | Produktentscheidung erforderlich |
| ARCH-009 | Logging-/Telemetrieumfang und Datenschutzgrenzen | Produkt-/Technikentscheidung erforderlich |
| ARCH-010 | Netzwerk-/Onlinefunktionen und Backend-Abhängigkeiten | Produktentscheidung erforderlich |
