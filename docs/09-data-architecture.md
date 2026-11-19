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

## 9.11 Weltgenerierungsdaten und Versionsbindung

Weltgenerierungsdaten müssen die zur Reproduktion und sicheren Weiterentwicklung erforderlichen Eingaben und Versionen speichern. Dazu gehören mindestens Welt-/Regionsidentität, Seed-Kontext, Generatorversion, Regelsatz-/Profilversion und Referenzen auf verwendete Datenkataloge.

Zu unterscheiden sind:
- globale geografische Planungsdaten;
- regionale Generierungsergebnisse;
- technische Chunk-/Streamingdaten;
- persistente Änderungen nach der Generierung;
- Laufzeitzustände aus Simulation und Gameplay.

Eine Generatoraktualisierung darf persistente Spieleränderungen nicht als bloße Generatorabweichung behandeln oder überschreiben. Die genaue Speicherung und Granularität ist durch Prototypen festzulegen.

## 9.12 Herkunft, Provenienz und Content-Import

Importierte Inhalte benötigen nachvollziehbare Herkunft. Für externe Karten, Assets und Contentpakete sollen Quelle, Autor/Urheber soweit bekannt, Lizenz, Importdatum, Originalversion, Transformationen und lokale Änderungen dokumentiert werden.

Bei Datenimporten müssen Originalquelle und Vaelith-Datensatz unterscheidbar bleiben. Ein erneuter Import darf lokale Anpassungen nicht stillschweigend überschreiben. Zusammenführen, Ersetzen und Verwerfen sind explizite Operationen mit Vorschau und Protokoll.

## 9.13 Transaktionen und Zustandsänderungen über Systeme hinweg

Aktionen, die mehrere Fachbereiche verändern, benötigen eine konsistente Ausführungs- und Wiederherstellungsstrategie. Beispiele sind Questbelohnungen, Bauaufträge, Produktionszyklen, Zuchtvorgänge und Regionsfreigaben.

Es muss erkennbar sein:
- welche Zustände gemeinsam geändert werden;
- welche Vorbedingungen gelten;
- wann eine Änderung als abgeschlossen gilt;
- wie Teilfehler erkannt und behandelt werden;
- wie doppelte Ausführung verhindert wird;
- wie Wiederholung, Rücknahme oder Reparatur erfolgt.

Eine universelle technische Transaktionslösung wird hier nicht vorgeschrieben. Die Architektur muss jedoch Datenverlust, doppelte Belohnungen und widersprüchliche Teilzustände verhindern.

## 9.14 Ereignisprotokoll und Änderungsverfolgung

Für wichtige dauerhafte Zustandsänderungen ist ein geeignetes Änderungs-/Ereignisprotokoll vorzusehen. Es soll Ursachen und Folgen für Debugging, QA, Savegame-Reparatur und Modding nachvollziehbar machen.

Nicht jede Frame- oder Animationsänderung muss protokolliert werden. Umfang und Aufbewahrung richten sich nach fachlicher Bedeutung, Speicherbudget und Datenschutz-/Plattformanforderungen.

## 9.15 Datenverträge zwischen Editoren und Runtime

Editoren, Generator und Runtime müssen dieselben kanonischen Definitionen und Validierungsregeln verwenden. Ein Editor darf keine Daten freigeben, die die Runtime anders interpretiert oder nicht laden kann.

Datenverträge umfassen:
- stabile IDs und Typen;
- Schema- und Paketversionen;
- Pflichtfelder und zulässige Werte;
- Referenz- und Kompatibilitätsregeln;
- Standardwerte und Fallbackverhalten;
- Migrations- und Fehlerregeln.

Validierung muss möglichst früh erfolgen und sowohl im Editor als auch vor Build/Runtime verfügbar sein.

## 9.16 Offene Datenarchitektur-Entscheidungen

| ID | Thema | Status |
|---|---|---|
| DATA-001 | Kanonische Serialisierung für Definitionen, Weltzustände und Spielstände | Technische Evaluierung erforderlich |
| DATA-002 | Speichertechnologie und Datenbankbedarf | Architekturentscheidung erforderlich |
| DATA-003 | Granularität von Welt-/Regions-/Chunkpersistenz | Prototyp/Profiling erforderlich |
| DATA-004 | Ereignisprotokoll: Umfang, Aufbewahrung und Kompaktierung | Offen |
| DATA-005 | Transaktions-/Wiederherstellungsmodell für systemübergreifende Aktionen | Technische Spezifikation erforderlich |
| DATA-006 | Schema- und Paketversionierung für Mod-Inhalte | Abgleich mit Dokument 11 erforderlich |
| DATA-007 | Provenienzmodell für externe Karten, Assets und Contentimporte | Offen |
| DATA-008 | Umgang mit Konflikten zwischen Generatorupdates und Spieleränderungen | Technische Spezifikation erforderlich |


## 9.17 Namensräume, Eigentümerschaft und Herkunft von Inhalten

Stabile IDs müssen auch dann eindeutig bleiben, wenn Grundspiel, Datenmods, importierte Pakete und projektspezifische Werkzeuge Inhalte beitragen. Vor der endgültigen Festlegung des ID-Formats ist ein explizites Namensraum- und Eigentümerschaftsmodell zu definieren.

Das Modell muss mindestens unterscheiden:
- Inhalte des Grundspiels;
- Inhalte eines eindeutig identifizierten Mods bzw. Contentpakets;
- importierte externe Datensätze mit erhaltener Quellenreferenz;
- lokal erstellte oder lokal angepasste Inhalte;
- Laufzeitinstanzen, die auf eine Definition verweisen.

Ein Anzeigename oder Dateipfad ist keine Identität. Umbenennen und Verschieben dürfen Referenzen nicht brechen. Kollisionen müssen vor Aktivierung eines Pakets erkannt und verständlich gemeldet werden. Eigentümerschaft und Herkunft bleiben auch bei abgeleiteten oder lokal angepassten Datensätzen nachvollziehbar.

Das konkrete ID-Format, die Regeln für Übernahmen zwischen Namensräumen und die Behandlung gelöschter bzw. nicht mehr verfügbarer Moddefinitionen bleiben technische Entscheidungen.

## 9.18 Einheitlicher Änderungs- und Freigabelebenszyklus

Editoren, Importer, Generator und administrative Contentpflege müssen denselben fachlichen Lebenszyklus für Änderungen unterstützen. Die konkrete Benutzeroberfläche darf je Werkzeug variieren; die Datenintegritätsregeln dürfen es nicht.

Ein Änderungsablauf unterscheidet mindestens:
1. Entwurf bzw. lokale Arbeitskopie;
2. Validierung einschließlich Referenzen, Schemas, Berechtigungen und Abhängigkeiten;
3. Vorschau und Impact-Analyse;
4. explizite Übernahme in den vorgesehenen Datenbestand;
5. Protokollierung von Urheber, Zeitpunkt, Anlass und betroffenen IDs;
6. Wiederherstellung oder Migration, falls die Änderung fehlerhaft ist.

Nicht jede Änderung benötigt einen mehrstufigen Freigabeprozess. Die erforderliche Kontrolle richtet sich nach Risiko, Reichweite und Persistenzwirkung. Ungeprüfte Entwürfe dürfen jedoch nicht unbemerkt in veröffentlichte Inhalte oder bestehende Spielstände gelangen.

## 9.19 Trennung von Definition, Weltzustand und Präsentation

Kanonische Contentdefinitionen, persistenter Welt-/Spielstand und rein visuelle bzw. abgeleitete Laufzeitdaten müssen getrennt behandelt werden. Eine Änderung an einer Definition darf nicht automatisch bestehende Instanzen oder Spieleränderungen überschreiben.

Für Änderungen ist festzustellen, ob sie:
- nur eine Definition für neu erzeugte Instanzen betreffen;
- bestehende Instanzen gezielt migrieren;
- persistenten Weltzustand verändern;
- ausschließlich abgeleitete Laufzeit-/Darstellungsdaten neu berechnen.

Die jeweilige Wirkung muss vor Übernahme sichtbar und testbar sein. Das gilt insbesondere für Items, Gebäude, NPCs, Kreaturen, Regionen und Produktionsdaten.


## 9.20 Quest-, Decision- und Knowledge-Persistenz

Questdefinitionen, Dialoge, Knowledge-Einträge, World Actions und Spielerfortschritt sind getrennte versionierte Datenbereiche. Der Spielstand speichert Queststatus, Run-ID, Objective-Fortschritt, Entscheidungen, Belohnungsnachweise, ausgeführte Weltaktionen, Cooldowns und erforderliche Versionsinformationen. Questdefinitionen werden nicht als veränderliche Laufzeitinstanzen gespeichert.

World State bleibt die kanonische Wahrheit für NPC-, Fraktions-, Regions-, Gebäude-, Siedlungs- und globale Zustände. Die Quest Runtime liest diese Zustände über Services und beantragt Änderungen über autorisierte World Actions. Sie führt keine parallelen Kopien derselben Weltfakten.

Events und Aktionen benötigen stabile IDs, Deduplizierung und Idempotenz. Mehrteilige Aktionen müssen atomar oder kompensierbar sein. Save-/Load- und Migrationsregeln stehen in Dokument 25.

## 9.21 Katalog- und Produktionsdatenmigration

Emberwild-Itemdaten werden als versionierte Stammdatenfamilien migriert. Definitionen, konkrete Instanzen, Stacks, Rezepte, Produktionsaufträge und Facilities sind getrennte Datenkonzepte. IDs und Referenzen bleiben erhalten, sofern eindeutig; Schemaänderungen benötigen Mapping, Validierung und Migrationshistorie. Details stehen in Dokument 24.

## 9.22 Eventherkunft und Auditierbarkeit

Systemübergreifende Ereignisse tragen Quelle, Event-ID, Welt-/Spielzeit, Schema-Version und fachlichen Kontext. Relevante Änderungen an Quest-, Inventar-, Wirtschafts-, NPC-, Regions- und Produktionszuständen müssen bis zum auslösenden Vorgang nachvollziehbar sein. Dies dient Debugging, Save-Recovery, Reproduzierbarkeit und Schutz vor doppelten Belohnungen oder Ressourcenbuchungen.

## Spielerprofile und Gameplay-Konfigurationen

Das Arbeitskonzept PECS sieht vor, Spielausrichtungen, Simulationstiefen pro Funktionsbereich, Automatisierungspräferenzen und aktivierte Regel-/Mod-Pakete nachvollziehbar zu speichern. Diese Konfiguration ist von der persistenten Weltwahrheit zu trennen.

Profile dürfen keine zweite Quelle für Quest-, NPC-, Wirtschafts-, Inventar- oder Freischaltzustände bilden. Sie beschreiben Präferenzen und gültige Konfigurationen. Fachzustände bleiben in ihren zuständigen Systemen.

Änderungen an Profilen müssen versioniert und validiert werden. Laufende Aktionen und mehrteilige Transaktionen dürfen durch einen Wechsel nicht dupliziert, gelöscht oder rückwirkend verfälscht werden. Bei ungültigen oder inkompatiblen Konfigurationen muss ein sicherer Rückfall auf die letzte gültige Fassung möglich sein. Details stehen in `26-player-experience-and-replayability.md`.
