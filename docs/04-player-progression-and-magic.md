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
