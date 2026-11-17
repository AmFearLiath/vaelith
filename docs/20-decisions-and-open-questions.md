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
