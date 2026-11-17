# 24 — Item-, Material- und Produktionsmigration

> Status: Migrationsgrundlage aus dem bereitgestellten Emberwild-Archiv. Kein endgültiger Vaelith-Katalog und keine Freigabe sämtlicher Draft-Werte.

## 24.1 Ziel

Die vorhandenen Emberwild-Item-, Material-, Werkzeug-, Lebensmittel-, Verbrauchsgüter-, Ausrüstungs- und Produktionsdaten werden als fachlicher Bestand erhalten und kontrolliert in Vaelith überführt. Die technische Implementierung wird für Unity neu erstellt. Original-IDs, Bedeutungen, Beziehungen und Migrationshistorie sind soweit möglich zu bewahren.

## 24.2 Inventarisierter Umfang

Das Archiv enthält 240 JSON-Dateien insgesamt. Alle 240 ließen sich syntaktisch parsen. 283 Dateien/Einträge liegen unter Items/; dazu gehören Kataloge, Planungsunterlagen und Migration Notes. Mehrere Dateien bilden aufeinanderfolgende Versionen derselben Katalogfamilie ab. Einträge verschiedener Versionen dürfen nicht addiert werden, bevor Identität und Migrationsstatus geklärt sind.

Vorhandene Datenfamilien:
- Ressourcen und Rohstoffe, einschließlich pflanzlicher und tierischer Ressourcen;
- verarbeitete Materialien und Metalle;
- Nahrung, Rohzutaten, verarbeitete Lebensmittel, Mahlzeiten und Getränke;
- Verbrauchsgüter wie Munition, Medizin, Gifte, Tränke und Wartungsgegenstände;
- Werkzeuge für Landwirtschaft, Jagd, Fischerei, Tierhaltung, Stein-/Metall-/Holzbearbeitung und Handwerk;
- Waffen, Rüstungen, Schilde und Schmuck;
- Ausrüstung, Sets, Verzauberungen und Sockel;
- Produktionsstätten, Rezepte und Verarbeitungsketten.

## 24.3 Kanonisches Datenmodell

Vaelith trennt:
1. Definition: versionierte Stammdaten eines Item-/Materialtyps.
2. Instanz: konkretes Exemplar mit Zustand, Menge, Haltbarkeit, Qualität, Herkunft oder individuellen Merkmalen.
3. Stack: Zusammenfassung kompatibler Instanzen nach den Stackregeln der Definition.
4. Rezept: Verarbeitungsvorschrift mit Inputs, Outputs, Nebenprodukten, Station und Bedingungen.
5. Produktionsauftrag: konkreter Vorgang mit reservierten Inputs, Fortschritt, Ergebnis und Fehler-/Abbruchstatus.
6. Facility: Produktionsstätte mit Typ, Zustand, Kapazität, Arbeitsplätzen und Spezialisierungen.

Eine Itemdefinition ist keine Inventarinstanz. Laufzeitveränderungen dürfen Stammdaten nicht mutieren.

## 24.4 Migrationsregeln

- Vorhandene IDs bleiben erhalten, sofern sie eindeutig und dauerhaft verwendbar sind.
- Doppelte IDs werden nicht automatisch umbenannt; Herkunft, Version und Referenznetz sind zuerst zu prüfen.
- Veraltete Felder werden über explizite Mappingregeln migriert.
- Unbekannte Felder werden im Migrationsbericht ausgewiesen.
- Übersetzungen, Beschreibungen, Tags, Kategorien und Unterkategorien bleiben erhalten.
- Materialreferenzen zeigen auf kanonische Materialdefinitionen.
- Rezepte referenzieren auflösbare Inputs, Outputs, Nebenprodukte und Facilities.
- Ausrüstungsdefinitionen halten Slots, Typen, Effekte und visuelle Referenzen konsistent.
- Migrationen sind wiederholbar und idempotent.
- Originaldateien werden nie überschrieben; Zielartefakte erhalten Migrationsversion und Quellenbezug.

## 24.5 Materialgrenzen und Produktionsarchitektur

Die Material-Boundary-Register und Architekturentscheidungen sind vor dem Zusammenführen von Rohstoffen, Zwischenprodukten und Fertigwaren auszuwerten. Gleich klingende Begriffe dürfen nicht ohne Prüfung zusammengeführt werden.

Die vorhandenen Produktionsarchitekturen für Lebensmittel, Metallurgie und Holzverarbeitung sowie Recipe-/Facility-Schemas sind konkrete Ausgangsmodelle. Sie werden in ein gemeinsames Produktionsvertragsmodell überführt, ohne fachspezifische Eigenschaften zu verlieren.

Ein Rezept definiert mindestens stabile ID und Version, Inputs, Mengen und Qualitätsbedingungen, Outputs, Nebenprodukte/Verluste, Facility-Anforderungen, Zeit-/Arbeitsaufwand, Fähigkeiten/Berufe sofern vorhanden, Bedingungen und Abbruchregeln.

Ein Produktionsauftrag reserviert Inputs atomar. Beim erfolgreichen Abschluss werden Outputs genau einmal erzeugt. Abbruch und Fehler besitzen definierte Rückgabe-/Verlustregeln. Detailproduktion und Fernsimulation verwenden dieselben fachlichen Regeln.

## 24.6 Ausrüstung und Gegenstandsregeln

Die vorhandenen Konzepte zu Waffenbeherrschung, Attributwirkung, Ausrüstungsslots, Haltbarkeit, Qualität, Seltenheit, Verzauberung und Sockeln sind einzeln zu inventarisieren.

Qualität, Seltenheit, Zustand und visuelle Variante bleiben getrennte Dimensionen, sofern die Quelle nicht ausdrücklich eine andere Bedeutung definiert. Die vorhandene Designrichtung freier Waffenwahl wird als Arbeitsgrundlage übernommen: Attribute beeinflussen Effektivität, sperren aber nicht ohne begründete Spielregel ganze Waffenfamilien. Waffenbeherrschung und Techniken werden mit Progression und Kampf verknüpft. Exakte Werte und Freischaltregeln bleiben bis zum vollständigen Katalogabgleich offen.

Haltbarkeit ist pro Itemdefinition konfigurierbar. Nicht jedes Item muss Verschleiß besitzen.

## 24.7 Inventar, Lager und Transport

Spielerinventar, Ausrüstung, persönliche Lager, Siedlungslager, Händlerbestände, Produktionslager, Dungeonlager und Transportcontainer referenzieren dieselben Itemdefinitionen. Sie dürfen unterschiedliche Zugriffs- und Kapazitätsregeln besitzen, aber keine getrennten Itemidentitäten erzeugen.

Transportvorgänge können Quelle, Ziel, Fracht, Menge, Träger/Fahrzeug, Route, Start, Ankunft, Verlust und Unterbrechung abbilden, sofern die jeweilige Spielmechanik diese Daten benötigt.

## 24.8 Validierung und Abnahme

Vor Katalogfreigabe sind JSON-/Schema-Validierung, eindeutige IDs und Namespaces, Referenzintegrität, Versions-/Migrationskonsistenz, Dubletten-/Aliasprüfung, Materialgrenzen, Rezept-/Facility-Konsistenz, Ausrüstungsslots, Lokalisierung, Import-/Export-Rundlauf, Spielstandkompatibilität und repräsentative Produktions-/Loot-Szenarien zu prüfen.

## 24.9 Verbleibende Arbeiten

Dieses Dokument behauptet nicht, dass alle 240 JSON-Dateien semantisch und feldweise vollständig ausgewertet wurden. Noch erforderlich sind dateiweises Inventar mit Kategorie, Version, Status und Eintragszahl, Vergleich aller Versionen einer Katalogfamilie, Prüfung eingebetteter Archive, kanonische ID-/Referenzmatrix, Rezept-/Produktionskettenmatrix, Migrationsmapping sowie Abgleich mit Charakter-, Kampf-, Wirtschafts-, Simulations- und Moddingdaten.

Originalwerte werden nicht pauschal verändert. Abweichungen benötigen eine nachvollziehbare Designentscheidung und Migration.
