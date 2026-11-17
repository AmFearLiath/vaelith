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
