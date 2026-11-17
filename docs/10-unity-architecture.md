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
