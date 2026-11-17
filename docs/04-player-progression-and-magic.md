# 04 — Spieler, Progression und Magie

## 4.1 Spielercharakter

Der Spieler ist ein individuell entwickelbarer Charakter mit außergewöhnlicher Herkunft. Die hybride Abstammung ist ein zentraler Erzählfaktor, ersetzt aber nicht die persönliche Entwicklung und Entscheidungen.

Das Spiel muss Herkunft, Charakterwerte, Fähigkeiten, Ausrüstung, Zustände, Beziehungen, Questfortschritt und spielweltrelevante Berechtigungen als unterscheidbare Datenbereiche behandeln. Konkrete Attribute, Klassen, Skilltrees und Werteformeln sind anhand vorhandener Character-/Item-Spezifikationen zu ergänzen.

## 4.2 Progression durch Geschichte und Entdeckung

Besondere Systeme sollen nicht ausschließlich durch das Erreichen einer Charakterstufe freigeschaltet werden. Quests, Entdeckungen, Beziehungen, Training, Entscheidungen und Vaeliths Unterricht sind geeignete Freischaltbedingungen.

Mögliche Meilensteine, ausdrücklich nur als Arbeitsstruktur:
- erste ungewöhnliche Magieerfahrungen im frühen Spiel;
- grundlegende Kontrolle und Verständnis der eigenen Kräfte;
- Befreiung Vaeliths am Ende des ersten großen Handlungsbogens;
- Vaelith als körperlich anwesender Begleiter und Mentor;
- spätere Freischaltung von Schloss- und Siedlungsbau, erweiterten Dungeon-Funktionen, Zucht und fortgeschrittener Weltgestaltung.

Konkrete Questzuordnungen, Kapitelgrenzen und Bedingungen sind offen.

## 4.3 Magie und vollständiges Potenzial

In den Gesprächen wurde festgehalten, dass der Spieler nach Vaeliths Befreiung Zugang zu dessen vollständigen magischen Fähigkeiten erhalten soll. Dieses Ziel darf nicht durch eine gegenteilige Designannahme ersetzt werden, nach der der Spieler nur eine kleine Auswahl erhält.

Für ein spielbares Fortschrittssystem ist zwischen **Zugang/Potenzial** und **Beherrschung/Anwendung** zu unterscheiden:
- Die Befreiung kann das vollständige Potenzial bzw. den Zugang zu den Fähigkeiten eröffnen.
- Präzision, Kontrolle, Verständnis, verantwortungsvolle Anwendung und neue Einsatzmöglichkeiten können durch Unterricht und Erfahrung wachsen.
- Einschränkungen dürfen nicht nachträglich als künstliche Schwäche Vaeliths oder als unbegründete Sperre des Spielerpotenzials eingeführt werden.

Die genaue Mechanik ist noch zu entscheiden und muss die erzählerische Aussage erhalten.

## 4.4 Vaelith als Begleiter und Mentor

Nach seiner Befreiung ist Vaelith ein aktiver Charakter:
- Er begleitet den Spieler in der Welt.
- Er kann auf Situationen, Orte, Fraktionen, Magie, Entscheidungen und Erinnerungen reagieren.
- Er kann Wissen vermitteln, Fähigkeiten erklären oder Training anbieten.
- Er darf Meinungsverschiedenheiten ausdrücken und Entscheidungen kritisieren.
- Er besitzt eigene Ziele und eine Vergangenheit.
- Er ersetzt weder den Spieler im Kampf noch trifft er dessen grundlegende Entscheidungen.

Seine scheinbare Allmacht erfordert eine klare narrative und technische Rollenbeschreibung. Er kann außergewöhnliche Kräfte besitzen und dennoch aufgrund seines Eides nicht beliebig in Ereignisse eingreifen.

## 4.5 Charakter- und Fähigkeitsdaten

Die konkrete Datenstruktur muss aus bestehenden Spieler-, Klassen-, Attribut- und Itemdefinitionen abgeleitet werden. Mindestens getrennt zu modellieren sind:
- dauerhafte Grundattribute;
- abgeleitete Werte;
- erlernte Fähigkeiten und Freischaltbedingungen;
- aktive/passive Effekte;
- temporäre Statuswirkungen;
- Ausrüstung und Modifikatoren;
- Beziehungen und storyrelevante Flags;
- Magiepotenzial, Kontrolle und bekannte Anwendungen;
- Speichern und Wiederherstellen aller spielrelevanten Zustände.

Keine bestehenden JSON-Felder, Formeln, IDs oder Kategorien dürfen ohne dokumentierte Migration entfernt werden.

## 4.6 Kampf und Bewegung

Die Welt ist vollständig 3D. Spielerbewegung, Sprünge, Klettern bzw. Höhenwechsel, Nah- und Fernkampf, Magie, Kollisionsabfrage, Navigation und Animation müssen reale räumliche Verhältnisse berücksichtigen. Die genauen Kampfmodi, Waffenformeln, Eingabebelegung, Trefferlogik und Gegnerarchetypen sind aus dem existierenden Kampfsystem zu übernehmen bzw. gesondert zu spezifizieren.

## 4.7 Entscheidungen und Konsequenzen

Relevante Spielerentscheidungen sollen in Weltzuständen und Reaktionen abbildbar sein: Beziehungen, Ruf, Fraktionsstatus, Siedlungsentwicklung, Questvarianten, Zugang, Handel, Gefahr oder langfristige Ereignisse. Nicht jede Dialogoption muss ein globaler Branch sein; Auswirkungen sind nach Reichweite und narrativer Bedeutung zu klassifizieren und zu testen.


---

## 4.8 Grundmodell der Charakterentwicklung

Die Charakterentwicklung muss mehrere voneinander unterscheidbare Ebenen abbilden. Herkunft, persönliche Eigenschaften, erlernte Fähigkeiten, Ausrüstung, temporäre Zustände und spielweltbezogene Berechtigungen dürfen nicht zu einem einzigen, undifferenzierten Fortschrittswert zusammengefasst werden.

Für die Konzeption und spätere Datenmodellierung sind mindestens folgende Bereiche getrennt zu betrachten:

- **Herkunft und Identität:** Abstammung, erzählerische Herkunft und damit verbundene Besonderheiten.
- **Grundattribute:** dauerhafte Charaktereigenschaften, sofern das bestehende Character-System solche Werte vorsieht.
- **Abgeleitete Werte:** Werte, die aus Attributen, Fähigkeiten, Ausrüstung oder Zuständen berechnet werden.
- **Fähigkeiten:** erlernte aktive und passive Anwendungen.
- **Beherrschung:** Übung, Verständnis und Zuverlässigkeit bei der Anwendung einer Fähigkeit.
- **Ausrüstung:** Gegenstände und deren Modifikatoren.
- **Zustände:** zeitlich begrenzte oder situationsabhängige Wirkungen.
- **Beziehungen und Weltstatus:** Ruf, Fraktionsbeziehungen, Questzustände und andere relevante Flags.
- **Berechtigungen und Freischaltungen:** Zugänge zu Spielsystemen, Orten, Bauweisen oder besonderen Interaktionen.

Diese Trennung ist zunächst eine konzeptionelle Anforderung. Die konkreten Felder, Wertebereiche, Formeln und IDs müssen aus den vorhandenen Spieler-, Klassen-, Attribut- und Itemdefinitionen abgeleitet werden.

## 4.9 Fortschritt durch unterschiedliche Quellen

Progression soll nicht ausschließlich an Charakterstufen gebunden sein. Unterschiedliche Fortschrittsquellen können je nach Fähigkeit und Spielsystem relevant sein:

- Story- und Questfortschritt;
- Entdeckungen und besondere Begegnungen;
- Unterricht und Training durch geeignete Figuren;
- praktische Anwendung und Erfahrung;
- Beziehungen und Vertrauen;
- Zugang zu Orten, Einrichtungen oder Wissensquellen;
- Entscheidungen und deren Konsequenzen.

Welche Quelle für eine konkrete Fähigkeit oder Freischaltung maßgeblich ist, muss fachlich begründet werden. Es wird keine universelle Fortschrittsformel vorausgesetzt.

### Freischaltung ist nicht gleich Beherrschung

Das Erhalten einer Fähigkeit, der Zugang zu einem Potenzial und die sichere Beherrschung einer Anwendung sind unterschiedliche Zustände. Diese Unterscheidung ist besonders für die Magie des Spielers relevant, gilt aber auch dort, wo es das bestehende Fortschrittssystem sinnvoll unterstützt.

## 4.10 Magie — konzeptionelle Leitplanken

Magie ist sowohl ein Gameplay-System als auch ein Teil der Weltgeschichte. Ihre konkrete Klassifikation, Bedienung und Balance müssen später gemeinsam mit Lore, Kampf, Animation, Effekten, Audio und Datenarchitektur festgelegt werden.

Aus dem bisherigen Projektstand ergeben sich folgende Leitplanken:

- Magie ist ein wesentlicher Bestandteil der Welt und der Spielerentwicklung.
- Die hybride Herkunft des Spielers ist mit einer außergewöhnlichen Verbindung zu Machtströmen verbunden.
- Die Aura des Spielers beeinflusst diese Ströme unbewusst.
- Vaelith erkennt diese Besonderheit und beobachtet den Spieler seit dessen Geburt.
- Vaelith verfügt über nahezu grenzenlose magische Macht, ist aber nicht allwissend.
- Vaeliths Zurückhaltung beruht auf seinem Eid und seiner Einsicht in die Folgen früherer Eingriffe, nicht auf einer künstlich erfundenen Machtlosigkeit.
- Nach Vaeliths Befreiung soll der Spieler Zugang zu dessen vollständigem magischen Potenzial erhalten.

Nicht festgelegt sind die genaue Herkunft der Magie, ihre Kategorien, Kosten, Ressourcen, Reichweiten, Grenzen, Lernmethoden oder konkrete Fähigkeiten. Diese Punkte bleiben offen, bis ein konsistentes Modell gemeinsam ausgearbeitet wurde.

## 4.11 Zugang, Potenzial, Kontrolle und Meisterschaft

Das Fortschrittsmodell muss ausdrücklich zwischen vier Begriffen unterscheiden:

1. **Zugang:** Der Spieler erhält grundsätzlich die Möglichkeit, eine Fähigkeit oder einen Bereich magischer Anwendungen zu nutzen.
2. **Potenzial:** Der Umfang der grundsätzlich verfügbaren Möglichkeiten. Im Fall der Befreiung Vaeliths soll das vollständige magische Potenzial zugänglich werden.
3. **Kontrolle:** Die Fähigkeit, eine Anwendung gezielt, präzise und verlässlich auszuführen.
4. **Meisterschaft:** Ein vertieftes Verständnis, das eine sichere, differenzierte und situationsgerechte Anwendung ermöglicht.

Diese Begriffe beschreiben unterschiedliche Entwicklungsdimensionen und sind keine bereits festgelegten Spielwerte oder technischen Attribute.

### Konsequenz für die Befreiung Vaeliths

Die Befreiung darf nicht als bloße Freischaltung einer kleinen, willkürlich begrenzten Auswahl dargestellt werden. Das vereinbarte Ziel ist der Zugang zum vollständigen Potenzial. Eine anschließende Entwicklung kann sich auf Verständnis, Kontrolle, Präzision, verantwortungsvolle Anwendung und die praktische Meisterung konzentrieren.

Die konkrete Umsetzung muss vermeiden, dass eine künstliche Sperre lediglich unter einem anderen Namen wieder eingeführt wird. Wenn bestimmte Anwendungen besondere Voraussetzungen benötigen, müssen diese aus der inneren Logik der Fähigkeit, der Situation oder der erlernten Kontrolle folgen und gemeinsam festgelegt werden.

## 4.12 Vaeliths Unterricht und Mentorenrolle

Nach seiner Befreiung kann Vaelith als Mentor Wissen vermitteln und die Entwicklung des Spielers begleiten. Seine Rolle muss dabei zu seiner Persönlichkeit, seinem Eid und seiner Vergangenheit passen.

Mögliche Formen der Vermittlung, deren konkrete Ausgestaltung noch offen ist:

- Erklärungen zu entdeckten magischen Phänomenen;
- Hinweise auf Zusammenhänge zwischen Herkunft und Machtströmen;
- gezieltes Training;
- Unterstützung beim Verständnis komplexer Anwendungen;
- Kommentare zu verantwortungsvoller oder riskanter Nutzung;
- Reaktionen auf Entscheidungen und deren Folgen.

Vaelith soll nicht zum automatischen Lösungsgeber werden. Er kann Wissen, Einschätzungen und Alternativen anbieten, muss aber Irrtümer besitzen dürfen und darf die Entscheidungen des Spielers nicht ersetzen.

Die Mentorenfunktion soll außerdem nicht jede Fähigkeit ausschließlich an Dialoge binden. Welche Inhalte durch Entdeckung, Übung, Gegenstände, Orte oder andere Figuren zugänglich werden, ist später zu definieren.

## 4.13 Kampf, Bewegung und räumliche Anwendung

Spielerbewegung und Kampf finden in einer vollständig dreidimensionalen Welt statt. Das betrifft nicht nur die Darstellung, sondern die tatsächliche räumliche Logik.

Zu berücksichtigen sind:

- Bewegung auf unterschiedlichen Höhen und Geländeformen;
- Sprünge und sonstige Höhenwechsel;
- Klettern oder vergleichbare Fortbewegungsformen, sofern das Gameplay-Konzept sie vorsieht;
- Nah- und Fernkampfsituationen;
- räumliche Reichweite und Wirkung von Fähigkeiten;
- Sichtlinien, Hindernisse und Kollisionsabfragen;
- Navigation und Positionierung;
- Animationen und Übergänge zwischen Bewegungs- und Kampfzuständen;
- Synchronisierung von Trefferlogik, Effekten und Rückmeldungen.

Die konkrete Bewegungs- und Kampfmechanik ist noch nicht vollständig spezifiziert. Insbesondere dürfen keine bestimmten Waffenformeln, Eingabebelegungen, Klassen, Trefferregeln oder Gegnerarchetypen ohne Abgleich mit den bestehenden Systemen als beschlossen behandelt werden.

## 4.14 Ausrüstung und Charakterwerte

Ausrüstung kann die Charakterentwicklung beeinflussen, muss aber als eigener Daten- und Funktionsbereich behandelt werden. Die bestehenden Itemdefinitionen sind maßgeblich für die spätere Konsolidierung.

Zu prüfen und zu dokumentieren sind insbesondere:

- bestehende Ausrüstungskategorien und Slots;
- Attribute und Modifikatoren;
- Anforderungen und mögliche Einschränkungen;
- Effekte und Statuswirkungen;
- Kompatibilität mit Fähigkeiten und Magie;
- Verbesserungen, Varianten und Qualitätsstufen, sofern vorhanden;
- Darstellung und Animation im 3D-Spiel;
- Speichern, Laden und Migration bestehender Gegenstandsdaten.

Es dürfen keine vorhandenen Kategorien, Felder, IDs oder Balancingregeln stillschweigend ersetzt werden. Vor einer Änderung ist ein Abgleich mit den Originaldaten und den bestehenden Item-Dokumenten erforderlich.

## 4.15 Entscheidungen und Konsequenzen

Spielerentscheidungen können über Dialoge hinaus Auswirkungen auf die Welt besitzen. Je nach Reichweite und Bedeutung können sie unter anderem folgende Bereiche betreffen:

- persönliche Beziehungen;
- Vertrauen und Ruf;
- Status gegenüber Fraktionen;
- Questverläufe und alternative Lösungen;
- Zugänge zu Orten, Personen oder Einrichtungen;
- Handel und wirtschaftliche Möglichkeiten;
- Gefahren und Reaktionen in einer Region;
- langfristige Ereignisse und Weltzustände.

Nicht jede Dialogoption muss einen globalen Handlungszweig erzeugen. Auswirkungen müssen nach Reichweite, Dauer, Reversibilität und erzählerischer Bedeutung klassifiziert werden. Die konkreten Regeln gehören in die Quest-, NPC- und Simulationskonzepte.

## 4.16 Datenintegrität und Kompatibilität

Die Daten des Spielercharakters müssen konsistent gespeichert, geladen, validiert und versioniert werden können. Die Laufzeit darf keine abweichende Paralleldefinition zu den Daten verwenden, die in den Editoren und Quelldateien gepflegt werden.

Verbindliche Anforderungen:

- stabile IDs für persistente Inhalte und Fähigkeiten;
- explizite Referenzen auf Items, Fähigkeiten, Effekte und Questzustände;
- Validierung fehlender oder ungültiger Referenzen;
- definierte Versionierung der Datenstrukturen;
- dokumentierte Migrationen bei Änderungen;
- nachvollziehbare Berechnung abgeleiteter Werte;
- Wiederherstellbarkeit gespeicherter Charakterzustände;
- Tests für Speichern, Laden und Versionswechsel.

Die konkrete technische Struktur wird im Datenarchitektur-Dokument festgelegt. Dieses Konzept nimmt keine nicht geprüften JSON-Felder oder bestehenden Datenmodelle vorweg.

## 4.17 Offene Entscheidungen zur Spielerentwicklung und Magie

| ID | Thema | Offene Frage |
|---|---|---|
| PROG-001 | Attribute | Welche Grundattribute und abgeleiteten Werte existieren im bisherigen Character-System? |
| PROG-002 | Klassen/Rollen | Gibt es Klassen, freie Spezialisierungen oder ein anderes bestehendes Modell? |
| PROG-003 | Fortschritt | Welche Stufen-, Erfahrungs- und Fortschrittsregeln sind bereits festgelegt? |
| PROG-004 | Fähigkeiten | Welche aktiven und passiven Fähigkeiten existieren und wie sind sie gruppiert? |
| PROG-005 | Magiestruktur | Welche Magieformen, Schulen oder Kategorien sind in den Originalquellen definiert? |
| PROG-006 | Machtströme | Wie funktionieren Machtströme und die besondere Aura des Spielers konkret? |
| PROG-007 | Vollständiges Potenzial | Wie wird der vollständige Zugang nach Vaeliths Befreiung spielmechanisch dargestellt? |
| PROG-008 | Meisterschaft | Wie entwickeln sich Kontrolle, Präzision und verantwortungsvolle Anwendung? |
| PROG-009 | Ressourcen | Verwendet Magie Ressourcen, Kosten, Abklingzeiten oder andere Begrenzungen? |
| PROG-010 | Kampf | Welche Kampf-, Bewegungs- und Trefferregeln bestehen bereits? |
| PROG-011 | Ausrüstung | Wie greifen bestehende Itemattribute und Ausrüstungsslots in Charakterwerte ein? |
| PROG-012 | Konsequenzen | Welche Entscheidungswirkungen sind persistent und wie werden sie klassifiziert? |
| PROG-013 | Vaelith | Welche Unterrichts-, Begleiter- und Reaktionsfunktionen sind konkret vorgesehen? |
| PROG-014 | Quellenabgleich | Welche vorhandenen Charakter-, Skill-, Magie- und Kampfdaten müssen übernommen oder migriert werden? |

## 4.18 Abhängigkeiten zu anderen Dokumenten

- 01-project-overview.md — Spielvision und übergeordnete Progressionsphasen.
- 02-design-principles.md — Designregeln und Spielerautonomie.
- 03-world-and-lore.md — Herkunft, Kosmologie, Vaelith und erzählerische Grundlagen.
- 05-gameplay-systems.md — Kampf, Interaktion, Quests und Freischaltungen.
- 06-living-world-simulation.md — Beziehungen, Fraktionen und Weltreaktionen.
- 09-data-architecture.md — Datenmodelle, IDs, Referenzen und Persistenz.
- 10-unity-architecture.md — technische Laufzeit- und Systemintegration.
- 12-assets-animation-audio.md — Darstellung, Animation, Effekte und Audio.
- 13-economy-items-crafting.md — Items, Ausrüstung und Gegenstandsdaten.
- 20-decisions-and-open-questions.md — offene Entscheidungen und Quellenstatus.

## 4.19 Änderungsprotokoll

| Version | Datum | Änderung |
|---|---|---|
| 0.1 | 2026-11-17 | Spielerherkunft, Progressionsgrundlagen, vollständiges magisches Potenzial, Vaeliths Mentorenrolle, Kampfbezug und offene Datenfragen festgehalten. |
| 0.2 | 2026-11-17 | Charakterentwicklungsbereiche, Fortschrittsquellen, Zugang/Potenzial/Kontrolle/Meisterschaft, Magieleitplanken, Unterricht, räumlicher Kampf, Ausrüstung, Konsequenzen, Datenintegrität und offene Entscheidungen ergänzt. |
