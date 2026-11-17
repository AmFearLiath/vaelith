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
