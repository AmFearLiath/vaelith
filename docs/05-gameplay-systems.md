# 05 — Gameplay-Systeme

## 5.1 Systemverbund

Die Gameplay-Systeme sind keine voneinander isolierten Spielmodi. Ein Spieler kann in derselben 3D-Welt reisen, kämpfen, Bewohner treffen, Aufgaben erledigen, Einrichtungen verwalten, Tiere versorgen und Ressourcen verarbeiten. Verwaltungsansichten sind Werkzeuge für die Welt, keine separaten Simulationen mit abweichendem Zustand.

## 5.2 Erkundung und Interaktion

Erkundung umfasst Oberflächengebiete, Höhenunterschiede, Gebäude, mehrere Gebäudegeschosse, Höhlen, Tunnel, Brücken und unterirdische Räume. Interaktionen müssen räumlich plausibel und mit Weltobjekten, NPCs, Kreaturen und Questzuständen verknüpft sein.

Zu unterstützende Inhalte:
- POIs, Ruinen, Geheimnisse, Ressourcenorte und Dungeons;
- dynamische Gefahren und Begegnungen;
- Zugangsvoraussetzungen und Questverknüpfungen;
- Entdeckung, Markierung und persistente Weltfunde;
- lokale Ereignisse und Erkundungsbelohnungen.

## 5.3 Quest-System

Das Quest-System muss Daten und Ablauf getrennt behandeln. Eine Questdefinition soll mindestens eine stabile ID, Metadaten, Startbedingungen, Ziele/Schritte, Bedingungen, Trigger, Dialog-/NPC-/Ort-Referenzen, Belohnungen, Abbruch-/Fehlerbedingungen und Konsequenzen unterstützen. Die genaue Struktur muss mit dem vorhandenen Quest-JSON abgeglichen werden; diese Dokumentation ersetzt keine Originalschema-Migration.

Erforderliche Fähigkeiten:
- lineare und verzweigte Abläufe;
- optionale Ziele und alternative Lösungen;
- Dialog- und Interaktionsauslöser;
- Ereignis-/Zustandsbedingungen;
- Questketten und Abhängigkeiten;
- wiederholbare bzw. zeitgebundene Aufgaben, falls bestehende Regeln dies vorsehen;
- Debugging, Simulation und Laufzeitinspektion;
- Referenzprüfung für NPCs, Orte, Items, Fraktionen und andere Inhalte.

Eine Quest darf nicht stillschweigend auf eine nicht existierende ID verweisen. Editor und Buildvalidierung müssen solche Fehler sichtbar machen.

## 5.4 Schloss- und Siedlungsbau

Über Quests werden schrittweise **Castle Build Mode** und **Village Build Mode** erschlossen. Beide nutzen eine gemeinsame Vaelith-Building-Editor-Grundlage und gemeinsame Platzierungs-, Validierungs-, Blueprint- und Dekorationswerkzeuge. Sie besitzen jedoch unterschiedliche Funktionsprofile, Gebäudekataloge und Inhalte. Dekorationen und geeignete Basiskomponenten können geteilt werden.

**Castle Build Mode** konzentriert sich auf Hauptanlage, zentrale Räume, Türme, Mauern/Grenzen, Tore, Verteidigung, Unterkünfte, Lager, Werkstätten, Forschung, Bibliothek, magische Einrichtungen, Gärten und Innenhöfe. Die genannten Beispiele beschreiben Funktionen, keine endgültige mittelalterliche Formensprache.

**Village Build Mode** unterstützt Wohnraum, Versorgung, Produktion, Märkte, Lager, Gemeinschaftsgebäude, Wege, Plätze, Infrastruktur, Landwirtschaft, Ställe, Verteidigung sowie soziale und kulturelle Einrichtungen. Bewohner erhalten Berufe, Bedürfnisse, Beziehungen und Aufgaben. Die Siedlung kann innerhalb definierter Regeln autonom wachsen und sich verändern.

Beide Modi müssen die endgültige Science-Fantasy-Weltgestaltung unterstützen. Gebäudefunktion und Architekturästhetik sind getrennt zu modellieren.

## 5.5 Dungeon-System — Dungeon-Keeper-Inspiration

Ein befreiter Dungeon ist nicht nur ein einmalig zu räumender Schauplatz. Er kann ausgebaut, betrieben, verteidigt und als wirtschaftliche Einrichtung genutzt werden.

Mögliche Raum-/Funktionsprofile:
- Schatz-/Wertlager;
- Mine bzw. Rohstoffgewinnung;
- Kreaturenhort und Brut-/Zuchtkammer;
- Werkstatt und Verarbeitung;
- Forschung und Magie;
- Vorratslager;
- Verteidigungs- und Fallenräume;
- Unterkunft und Versorgung.

Produktion hängt beispielsweise von Vorkommen, Größe/Ausbau, Fähigkeiten der Arbeiter oder Kreaturen, Versorgung, Infrastruktur, Sicherheit und besonderen Dungeon-Eigenschaften ab. Diese Faktoren sind als Designparameter zu prüfen, nicht als fertige Formel festgelegt.

Dungeons können durch zufällige Ereignisse, geplante Angriffe, rivalisierende Gruppen, Kreaturen, Questereignisse oder saisonale/weltweite Ereignisse angegriffen werden. Verteidigung kann durch eigenes Eingreifen, stationierte Einheiten, Kreaturen, Fallen, bauliche Maßnahmen, Magie oder Delegation erfolgen.

Eine Niederlage soll nicht automatisch alle Fortschritte löschen. Mögliche Folgen sind Schäden, Beuteverlust, Verletzungen und zeitweise Produktionsausfälle. Exakte Schadens- und Wiederherstellungsregeln sind offen.

Der Dungeon bleibt Teil derselben Welt: Der Spieler kann ihn betreten, erkunden, kämpfen, mit Bewohnern sprechen und die Einrichtung verwalten.

## 5.6 Kreaturen und Tiere

Das Kreaturen-/Tiersystem wird als gemeinsames Framework konzipiert. Rollen sind nicht zwingend exklusive Artenklassen; ein Lebewesen kann mehrere Rollen besitzen.

### Reittiere
Eigenschaften können Geschwindigkeit, Ausdauer, Traglast, Wendigkeit, Robustheit, Temperament, Geländeeignung und besondere Fähigkeiten umfassen. Zucht und Training können Merkmale beeinflussen.

### Begleittiere
Mögliche Aufgaben sind Kampfunterstützung, Fährtensuche, Entdeckung verborgener Objekte, Ressourcensuche, Gefahrenwarnung und Erkundungshilfe. Bindung, Verhalten und Training sind wichtig.

### Wildtiere
Sie gehören zu regionalen Ökosystemen. Manche Arten regulieren Bestände, jagen gefährliche Kreaturen, halten Schädlinge oder bestimmte Gefahren in Schach oder meiden Eindringlinge. Nicht jedes Wildtier ist domestizierbar. Ökologische Funktionen sollen unabhängig vom Spieler funktionieren.

### Haustiere
Sie leben im unmittelbaren Umfeld des Spielers und ermöglichen Interaktionen wie Füttern, Streicheln, Spielen, Pflege, Training und Ruhe. Bindung und Stimmung können durch Interaktionen wachsen. Situative Effekte sind möglich, sollen an Anwesenheit und tatsächliche Interaktion gebunden sein und nicht bloß wie ein passiver Schmuckbonus wirken.

### Farmtiere
Sie können Milch, Eier, Wolle, Fleisch, Leder und Nebenprodukte liefern, Dünger erzeugen oder Transport- und landwirtschaftliche Arbeit leisten. Individuelle Leistungsmerkmale, Robustheit und Futterbedarf sollen berücksichtigt werden.

### Hoftiere
Hoftiere sind eine eigenständige Kategorie und nicht lediglich Farmtiere mit anderer Bezeichnung. Denkbare Besonderheiten sind seltene Zuchtlinien, außergewöhnliche Produktqualität, magische Merkmale, besondere Sozialverhalten, Reputation oder spezielle Beiträge zu Arbeits- und Wohnbereichen. Die exakte Bedeutung und Abgrenzung des Begriffs muss gemeinsam festgelegt werden.

## 5.7 Zucht und Vererbung

Das gemeinsame Framework soll individuelle Identität, Attribute, Genetik, Alter, Gesundheit, Bedürfnisse, Verhalten, Beziehungen, Persönlichkeit, Animation, Fortpflanzung und Vererbung unterstützen. Zucht soll nachvollziehbare Merkmalsweitergabe ermöglichen; konkrete Genetik, Wahrscheinlichkeiten, Generationseffekte und Grenzen sind offen.

## 5.8 Zusammenspiel — beispielhafter Kreislauf

Der Spieler befreit einen Dungeon, richtet eine Zuchtkammer ein, entdeckt eine seltene Spezies und züchtet gewünschte Merkmale. Einige Kreaturen verteidigen den Dungeon, andere werden Begleiter. Rohstoffe und Produkte werden in Schloss oder Siedlung verarbeitet. Die Siedlung gewinnt Arbeitskraft oder Versorgung; die Wirtschaft reagiert. Vaelith kann Wissen vermitteln und die Folgen bestimmter Entscheidungen kommentieren.

Dieses Beispiel beschreibt das Integrationsziel, nicht eine verpflichtende Questabfolge.
