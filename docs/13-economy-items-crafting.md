# 13 — Wirtschaft, Items und Crafting

## 13.1 Ziel

Die Wirtschaft verbindet Spielerinventar, NPC-Bedarf, Siedlungen, Handel, Landwirtschaft, Dungeon-Produktion, Ressourcen, Handwerk und Kreaturenhaltung. Produktionsketten sollen sowohl im Gameplay als auch in der abstrakten Simulation konsistente Regeln verwenden.

## 13.2 Bestehende Itemdaten erhalten

Es gab frühere Gespräche und Archive zu Itemdaten, darunter Waffen, Rüstungen, Schilde und Schmuck. Die tatsächlichen Archivdateien und vollständigen JSON-Strukturen liegen für diese Fassung nicht erneut als inspizierbare Quelle vor. Daher werden hier keine Feldlisten, IDs oder vollständigen Kataloge erfunden.

Vor weiterer Implementierung ist zwingend:
1. Originalarchive und Verzeichnisse vollständig einlesen.
2. Dateinamen, Kategorien, IDs, Felder, Werte und Referenzen inventarisieren.
3. Doppelte, inkonsistente und fehlende Einträge markieren.
4. bestehende JSON-Strukturen als Ausgangsbasis dokumentieren.
5. Unity-/3D-Erweiterungen als additive oder migrierte Änderungen abbilden.
6. vollständige Migrationsanweisung und Beispiel-JSON erstellen.
7. alle neuen und geänderten Daten gegen Schema und Runtime prüfen.

## 13.3 Itemmodell — konzeptionell

Ein Itemsystem muss Definitionsdaten und individuelle Iteminstanzen trennen. Zu prüfen sind Felder für Identität, Anzeigename, Beschreibung, Kategorie, Unterkategorie, Seltenheit, Werte, Anforderungen, Effekte, Herstellung, Gewicht/Volumen, Stackverhalten, Icons, Modelle, Varianten und Modding-Metadaten. Diese Liste ist eine Prüfliste, kein Ersatz für das vorhandene Schema.

## 13.4 Ausrüstung und modulare Darstellung

Waffen, Rüstungen, Schilde und Schmuck müssen an Charakterwerte und Ausrüstungslogik angebunden sein. Visuelle Varianten können aus modularen Komponenten und Materialvarianten entstehen. Werte und visuelle Seltenheit dürfen nicht unkontrolliert gekoppelt werden.

## 13.5 Ressourcen und Produktionsketten

Ressourcen besitzen Vorkommen, Qualität, Verarbeitungsschritte, Lager- und Handelsregeln. Produktionsgebäude und Dungeonräume sind Produzenten oder Verbraucher. NPCs/Kreaturen benötigen zugewiesene Aufgaben und Versorgung. Produktion darf nicht aus unendlichen Inputs entstehen.

## 13.6 Crafting

Crafting-/Rezeptdefinitionen müssen Inputs, Outputs, Mengen, Werkstatt-/Stationsanforderungen, Fähigkeiten, Zeit, Qualitätsregeln und ggf. Nebenprodukte abbilden. Die tatsächlichen Felder und Formeln sind anhand vorhandener Datenquellen zu übernehmen.

## 13.7 Landwirtschaft und Tierprodukte

Farmtiere können Produkte und Nebenprodukte liefern. Die Produktion hängt von individuellen Merkmalen, Haltung, Alter, Gesundheit, Versorgung und geeigneter Infrastruktur ab. Hoftiere können besondere Qualitäten oder Eigenschaften besitzen. Der Wirtschaftssimulator muss dieselben Regeln verwenden wie die direkte Spielerinteraktion.

## 13.8 Balancing

Balancing benötigt nachvollziehbare Tabellen, Referenzszenarien und Simulationen. Preis, Verfügbarkeit, Produktionszeit, Ressourcenknappheit, NPC-Nachfrage und Spielerprogression müssen gemeinsam getestet werden. Konkrete Werte werden nicht aus dem Bauch heraus festgeschrieben.

## 13.9 Quellenlücke und Importpflicht

Das frühere Gespräch „Wirtschaftsbalancing besprechen“ und die genannten Item-Archive müssen als Originalquellen erneut herangezogen werden, bevor das endgültige Wirtschafts-/Itemkapitel als vollständig gelten kann. Diese Fassung ist die Systemhülle, nicht die vollständige Migration der historischen Kataloge.


## 13.10 Kanonische Definitionen und individuelle Instanzen

Itemdefinitionen sind zentrale, versionierte Stammdaten. Eine konkrete Iteminstanz in Welt, Inventar, Lager oder Ausrüstung referenziert ihre Definition und trägt nur instanzbezogene Zustände. Laufzeitkopien dürfen keine voneinander abweichenden Stammdaten erzeugen.

Die endgültige Trennung und Feldstruktur wird erst nach Prüfung der vorhandenen JSON-Quellen festgelegt. Bei der Migration müssen bestehende IDs und Referenzen soweit möglich erhalten bleiben. Unvermeidbare Änderungen benötigen Mapping, Validierung und einen nachvollziehbaren Migrationspfad.

## 13.11 Inventar, Lagerung und Transport

Inventar, persönliche Truhen, Siedlungslager, Händlerbestände, Produktionslager und Dungeonlager verwenden konsistente Regeln für Itemstapel, Mengen, Kapazitäten und Besitz. Unterschiedliche Lagerarten dürfen eigene Zugriffsbeschränkungen oder Kapazitätsprofile besitzen, aber keine voneinander abweichenden Itemidentitäten.

Transport ist ein eigener wirtschaftlicher Vorgang: Waren müssen zwischen Quelle und Ziel bewegt werden können. Soweit das Spielsystem Transportzeiten, Träger, Fahrzeuge, Routen oder Verlustrisiken verwendet, müssen diese Größen in direkter Interaktion und Simulation dieselbe fachliche Bedeutung haben.

## 13.12 Handel, Preise und Marktverhalten

Handel verbindet Spieler, Händler, NPCs, Siedlungen, Fraktionen und Produktionsstätten. Preise und Verfügbarkeit können von Angebot, Nachfrage, Lagerbestand, Entfernung, Transportaufwand, Qualität, regionalen Bedingungen und Ereignissen beeinflusst werden. Welche Faktoren tatsächlich gelten und wie stark sie wirken, bleibt eine Balancingentscheidung.

Ein Markt darf nicht unabhängig von der Weltwirtschaft unbegrenzt Waren erzeugen oder aufnehmen. Händlerbestände und Geldflüsse benötigen nachvollziehbare Quellen und Grenzen. Preisänderungen müssen reproduzierbar diagnostizierbar sein; der Spieler soll erkennbare Ursachen für relevante Marktveränderungen erhalten.

## 13.13 Produktions- und Verbrauchsverträge

Jede Produktionskette beschreibt ihre Eingänge, Ausgänge, Verluste/Nebenprodukte, benötigte Stationen, Arbeitskräfte, Dauer und Abhängigkeiten. Verbraucher sind unter anderem NPC-Haushalte, Siedlungen, Tiere, Werkstätten, Bauvorhaben und der Spieler.

Produktion darf nur stattfinden, wenn erforderliche Inputs und Voraussetzungen vorhanden sind. Fehlende Materialien, unbesetzte Arbeitsplätze, beschädigte Infrastruktur oder unterbrochene Transportwege müssen sich nachvollziehbar auf den Produktionsstatus auswirken. Die Simulation kann Vorgänge aggregieren, muss aber dieselben fachlichen Ergebnisse liefern wie eine detailliert simulierte Interaktion.

## 13.14 Qualität, Seltenheit und Varianten

Qualität, Seltenheit, Herkunft, Zustand und visuelle Variante sind getrennt zu modellieren, sofern die vorhandenen Datenquellen keine abweichende verbindliche Struktur vorgeben. Eine seltene Optik darf nicht automatisch bessere Werte bedeuten. Materialqualität, Handwerksfähigkeit, Rohstoffmerkmale und Herstellungsbedingungen können als Balancingfaktoren geprüft werden.

Varianten benötigen stabile Identitäten oder eindeutig auflösbare Variantendaten. Inventaricon, Weltmodell, Ausrüstungsmodell und Tooltip müssen dieselbe Iteminstanz und ihre relevanten Eigenschaften darstellen.

## 13.15 Crafting, Werkstätten und Fähigkeiten

Werkstätten und Craftingstationen sind echte Weltobjekte bzw. Funktionsorte mit Verfügbarkeit, Zustand und möglichen Spezialisierungen. Rezepte referenzieren kanonische Inputs und Outputs. Fähigkeiten oder Berufe können Herstellungsqualität, Effizienz oder Freischaltungen beeinflussen, sofern dies durch die bestehenden Regeln gedeckt ist.

Der Craftingablauf muss Materialprüfung, Stationsprüfung, Start, Fortschritt, Abbruch, Abschluss, Ergebnisverbuchung und Fehlerbehandlung definieren. Ein Vorgang darf bei Abbruch oder Fehlern keine Materialien duplizieren oder ungewollt verlieren. Persistenz und Transaktionsverhalten sind mit der Datenarchitektur abzustimmen.

## 13.16 Systemintegration

Wirtschaft, Items und Crafting sind keine isolierten Minispiele. Zu berücksichtigen sind mindestens:

- Spielerinventar, Ausrüstung, Beute und Belohnungen;
- NPC-Bedürfnisse, Berufe, Löhne und Haushalte;
- Siedlungen, Händler, Lager, Märkte und Handelsrouten;
- Landwirtschaft, Tierhaltung, Zucht und Tierprodukte;
- Gebäude, Baukosten, Reparatur und Infrastruktur;
- Dungeonräume, Personal, Ressourcenabbau und Produktion;
- Quests, Ereignisse, Fraktionen und Weltzustände;
- Mods, Datenversionierung und Spielstandmigration.

Änderungen an Definitionen oder Rezepten müssen Auswirkungen auf bestehende Spielstände und Mod-Inhalte berücksichtigen.

## 13.17 Wirtschaftsdiagnose und Balancingwerkzeuge

Die Editor-/Diagnosewerkzeuge sollen Produktionsketten, Warenflüsse, Lagerbestände, Engpässe, Preisverläufe, Verbrauchsraten und nicht erfüllte Bedürfnisse sichtbar machen. Testläufe müssen mit kontrollierten Ausgangsdaten und reproduzierbaren Parametern wiederholbar sein.

Balancingänderungen werden nicht nur anhand einzelner Itemwerte beurteilt. Zu prüfen sind komplette Produktions- und Versorgungsketten über unterschiedliche Regionen, Siedlungsgrößen, Entwicklungsstände und Spielphasen. Abweichungen zwischen Detail- und Fernsimulation sind gezielt zu testen.

## 13.18 Abnahmekriterien

Ein Teilbereich ist erst abnahmebereit, wenn Definitionen und Instanzen konsistent sind, Referenzen validiert werden, Persistenz und Migration geprüft sind, Produktions- und Handelsflüsse keine unbeabsichtigten Duplikate oder Quellen erzeugen und repräsentative Szenarien praktisch getestet wurden. Editoransichten müssen die relevanten Daten bearbeiten, validieren und nachvollziehbar speichern können.

## 13.19 Offene Entscheidungen

Die zugehörigen offenen Punkte ECON, ITEM und CRAFT sind im Entscheidungsregister unter Dokument 20 geführt. Die endgültigen Schemas, Zahlen und Formeln bleiben bis zur Prüfung der historischen Quelldaten ausdrücklich offen.


## 13.20 Originalkataloge und Migrationsgrundlage

Das bereitgestellte Emberwild-Archiv enthält umfangreiche Item-, Material-, Werkzeug-, Lebensmittel-, Verbrauchsgüter-, Ausrüstungs-, Rezept- und Produktionsdaten sowie Planungs- und Migration Notes. Die JSON-Dateien sind syntaktisch parsebar; daraus folgt keine automatische Freigabe ihrer Inhalte oder Werte. Mehrere Katalogversionen und Migrationsstände müssen familienweise verglichen werden.

Die Migration erhält IDs, Bedeutungen, Übersetzungen, Materialgrenzen und Referenzen soweit möglich. Itemdefinition, Iteminstanz, Stack, Rezept, Produktionsauftrag und Facility werden getrennt modelliert. Originaldateien bleiben unverändert. Die vollständigen Regeln und Abnahmekriterien stehen in Dokument 24.

## 13.21 Produktionsarchitektur und physische Warenflüsse

Die vorhandenen Produktionsarchitekturen für Lebensmittel, Metallurgie und Holzverarbeitung sowie Recipe-/Facility-Schemas sind konkrete fachliche Ausgangsquellen. Sie werden in ein gemeinsames Produktionsvertragsmodell überführt, ohne fachspezifische Eigenschaften zu verlieren. Inputs werden bei Auftragsstart kontrolliert reserviert; Outputs und Nebenprodukte werden bei erfolgreichem Abschluss genau einmal verbucht. Fehler, Abbruch und Wiederaufnahme besitzen definierte Regeln.

Transport, Lager, Händler, Produktionsstätten und Siedlungen verwenden dieselben kanonischen Itemdefinitionen und Warenmengen. Fernsimulation darf Ergebnisse aggregieren, aber keine abweichenden Produktions- oder Verbrauchsregeln erfinden.