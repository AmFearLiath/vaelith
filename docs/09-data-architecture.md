# 09 — Datenarchitektur und Persistenz

## 9.1 Grundregeln

Die Datenarchitektur muss Editor, Runtime, Generator, Modding und Web-/Adminbereiche konsistent verbinden. Kanonische Definitionen werden zentral verwaltet. Editorfenster sind unterschiedliche Sichten auf gemeinsame Daten, keine getrennten Wahrheiten.

## 9.2 Identität und Referenzen

Jeder dauerhaft referenzierbare Datensatz benötigt eine stabile ID. IDs dürfen nicht aus Anzeigenamen, Dateipfaden oder veränderlichen Sortierpositionen abgeleitet werden. Referenzen sollen typisiert und zur Build-/Laufzeit validiert werden.

Zu unterscheiden sind:
- Definitionen/Archetypen (z. B. Itemtyp, NPC-Vorlage, Biomprofil);
- Instanzen (ein konkretes Item, NPC, Tier oder Gebäude in einem Spielstand);
- Welt-/Regionsdaten;
- Laufzeit- und temporäre Zustände;
- Benutzer-/Projektmetadaten;
- Mod-Erweiterungen und deren Herkunft.

## 9.3 Definitionen und Instanzen

Eine Itemdefinition beschreibt beispielsweise statische Eigenschaften und mögliche Varianten. Eine konkrete Iteminstanz besitzt eigene Identität, Zustand, Haltbarkeit, Besitz- oder Inventarreferenz und weitere individuelle Werte. Entsprechendes gilt für NPCs, Tiere, Gebäude und Weltobjekte.

## 9.4 Dateiformate und JSON

Bestehende JSON-Formate sind vor Änderungen vollständig zu inventarisieren. Feldnamen, Typen, Standardwerte, Verschachtelung, IDs, Beziehungen und Semantik müssen erhalten oder über explizite Migrationen überführt werden.

Für jedes Schema sind zu dokumentieren:
- Schema-ID und Version;
- Pflicht-/optionale Felder;
- Datentypen und zulässige Werte;
- Standardwerte;
- Referenzen und Integritätsregeln;
- Validierungsfehler;
- Migrationspfad zwischen Versionen;
- Beispielinstanzen.

Ein Schema darf nicht „vereinfacht“ werden, indem bestehende Felder stillschweigend entfernt werden.

## 9.5 Datenpakete und Content-Pipeline

Daten sollten nach Fachgebiet und Verantwortlichkeit strukturiert sein. Definitionen müssen maschinenlesbar validierbar sein. Import, Export, Versionierung, Diffs und Fehlerberichte gehören zur Pipeline. Große Binärassets werden von kleinen Metadatendefinitionen getrennt.

Konkrete Verzeichnisstruktur und technische Serialisierung sind nach Bestandsaufnahme und Unity-Prototyp festzulegen.

## 9.6 Welt- und Regionspersistenz

Persistiert werden müssen mindestens:
- Weltseed und Generator-/Schema-Versionen;
- Region IDs und Entwicklungsstatus;
- veröffentlichte Regionsgenerierungsdaten;
- dauerhafte Veränderungen an Terrain/Objekten;
- Siedlungs- und Gebäudestatus;
- NPC-/Kreatureninstanzen und relevante Zustände;
- Produktions-/Inventar- und Wirtschaftszustände;
- Quest-/Eventzustände;
- Spielerzustand, Ausrüstung und Beziehungen.

Die konkrete Persistenzgranularität ist durch Streaming und Speichertests zu bestimmen.

## 9.7 Spielstände

Speicherstände müssen versioniert, robust und migrationsfähig sein. Schreibvorgänge sollten gegen Teilabbrüche geschützt werden, beispielsweise durch temporäre Dateien, atomaren Austausch oder ein geprüftes Transaktionskonzept. Beschädigte Daten müssen diagnostizierbar sein. Backup- und Wiederherstellungsabläufe sind zu testen.

## 9.8 Datenmigration

Jede Schemaänderung benötigt:
- alte und neue Version;
- deterministische Migrationsroutine;
- Validierung vor/nach Migration;
- Backup-/Rollbackstrategie;
- Protokollierung geänderter IDs/Referenzen;
- Testdaten für alte Spielstände;
- Dokumentation bekannter Inkompatibilitäten.

## 9.9 Dependency-Graph

Ein zentraler Abhängigkeitsgraph soll Referenzen zwischen Biomen, Regionen, Gebäuden, Siedlungen, NPCs, Quests, Items, Kreaturen, Rezepten, Fraktionen und Events abbilden. Er ermöglicht Impact-Analyse vor Änderungen und verhindert unbemerkte verwaiste Daten.

## 9.10 Datenvergleich und Änderungsverlauf

Für Welt- und Contentdaten werden nachvollziehbare Diffs benötigt. Änderungen sollen Autor, Zeitpunkt, Zweck, betroffene IDs und Migration enthalten. Generatorausgaben müssen mit Seed und Generatorversion reproduzierbar sein.
