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

## 5.9 Einheitliches Interaktionsmodell

Interaktionen sollen über ein gemeinsames, erweiterbares Modell beschrieben werden. Ein Objekt kann abhängig von Zustand, Rolle des Spielers, Questfortschritt, Werkzeugen, Fähigkeiten und Weltbedingungen unterschiedliche Aktionen anbieten.

Zu unterscheiden sind mindestens:
- **Untersuchung:** betrachten, lesen, analysieren, Spuren oder Hinweise erkennen;
- **Benutzung:** Türen, Schalter, Geräte, Werkzeuge, Einrichtungen und Transportmittel bedienen;
- **Dialog/Beziehung:** sprechen, handeln, überzeugen, helfen, bedrohen oder andere kontextabhängige soziale Aktionen;
- **Aufnahme/Verarbeitung:** sammeln, ernten, abbauen, plündern, zerlegen und verwenden;
- **Steuerung/Verwaltung:** Bewohnern, Kreaturen, Gebäuden oder Einrichtungen Aufgaben zuweisen;
- **Kampf/Abwehr:** angreifen, blocken, ausweichen, Fähigkeiten einsetzen und Gefahren neutralisieren.

Die Liste ist eine Funktionsgliederung, keine endgültige UI- oder Eingabebelegung. Konkrete Interaktionen müssen Datenreferenzen und Bedingungen verwenden, statt Quest- oder Weltlogik fest in einzelne Szenen zu schreiben.

Jede relevante Interaktion benötigt nachvollziehbare Voraussetzungen, Ergebniszustände und Rückmeldungen. Abgebrochene oder fehlgeschlagene Aktionen dürfen keine Teilzustände hinterlassen, die Inventar, Questfortschritt, Wirtschaft oder Weltzustand widersprüchlich machen.

## 5.10 Kampf und Fähigkeiten

Kampf ist Teil der begehbaren 3D-Welt und muss mit Bewegung, Gelände, Kollision, Animation, Ausrüstung, Charakterwerten, Fähigkeiten, Kreaturenverhalten und Weltzuständen zusammenarbeiten. Die konkrete Kampfmechanik wird nicht durch dieses Kapitel vorweggenommen; bestehende Regeln und Daten müssen vor einer Festlegung erneut geprüft werden.

Zu prüfen und im späteren Kampfsystem vollständig zu spezifizieren sind:
- Bewegungs- und Aktionszustände einschließlich Übergängen und Unterbrechungen;
- Nah-, Fern- und magische Angriffe, sofern sie durch vorhandene Konzepte bestätigt werden;
- Trefferprüfung, Reichweite, Sichtlinie, Hindernisse und Höhenunterschiede;
- Ausweichen, Blocken, Unterbrechen, Reaktionen und Kontrollverlust;
- Ressourcenverbrauch, Abklingzeiten und sonstige Aktionsgrenzen;
- Zustände, Effekte, Widerstände und Immunitäten;
- Ausrüstung, Waffenprofile, Rüstung, Schilde und Schmuck;
- Gegnerverhalten, Bedrohung, Gruppenkampf und Rückzug;
- Animation Events bzw. andere robuste Synchronisierung von Trefferzeitpunkt, Effekten und Audio;
- Beute, Verletzungen, Tod/Niederlage und Wiederherstellung.

Kampfwerte dürfen nicht unabhängig von Charakter-, Item- und Magiedaten gepflegt werden. Die kanonischen Definitionen müssen referenziert werden. Balancing ist anhand reproduzierbarer Begegnungen und Testcharaktere zu prüfen.

## 5.11 Quest- und Weltzustandsintegration

Quests dürfen nicht als isolierte Skriptsequenzen funktionieren. Ziele und Konsequenzen müssen tatsächliche Weltzustände verändern können, beispielsweise:
- Zugänge, Sperren und Freischaltungen;
- Besitz, Kontrolle und Zustand von Orten;
- NPC-Beziehungen, Zugehörigkeiten und Verfügbarkeit;
- Siedlungszustand, Infrastruktur und Versorgung;
- Ressourcen, Items, Rezepte und Produktionsmöglichkeiten;
- Kreaturenbeziehungen, Populationen und Aufgaben;
- Fraktionsbeziehungen und lokale Ereignisse.

Eine Questentscheidung muss über stabile Zustandsänderungen abgebildet werden. Dialogtext allein gilt nicht als Konsequenz, wenn die Entscheidung laut Inhalt praktische Auswirkungen haben soll. Umgekehrt darf ein einmaliger Dialog nicht unbeabsichtigt dauerhafte Weltänderungen auslösen.

Quest-Editor und Laufzeit benötigen Vorschau bzw. Debugmöglichkeiten, um Voraussetzungen, Ereignisreihenfolge, alternative Pfade und resultierende Zustände nachvollziehen zu können. Die konkrete Questdatenstruktur bleibt bis zum Abgleich mit dem vorhandenen Quest-JSON unbestätigt.

## 5.12 Schloss- und Siedlungsbau: Gameplay-Anforderungen

Die beiden Baumodi benötigen einen verständlichen Wechsel zwischen direktem Spiel und Planungs-/Bauaktionen. Der Wechsel darf den Weltzustand nicht duplizieren oder eine getrennte Simulation starten.

Für beide Modi sind als gemeinsame Grundfunktionen vorzusehen:
- Baugrund und Platzierbarkeit prüfen;
- Gelände, Neigung, Höhenunterschiede, Zugänge und Kollision berücksichtigen;
- Baupläne/Blueprints erstellen, speichern, laden und wiederverwenden;
- Bau-, Ausbau-, Reparatur- und Rückbauzustände verwalten;
- Materialbedarf und Lieferketten aus dem Wirtschaftssystem beziehen;
- Arbeitskräfte, Bauzeit und Zugänglichkeit berücksichtigen;
- Räume, Gebäudefunktionen und Infrastruktur auf Gültigkeit prüfen;
- visuelle Vorschau und klare Fehler-/Warnhinweise anbieten;
- Änderungen persistent speichern und nach erneutem Laden identisch darstellen.

Die konkrete Baukostenformel, Raster-/Freiformplatzierung, Baurechte, Grundstücksgrenzen, Baugeschwindigkeit und Ressourcenlogik sind noch nicht festgelegt.

**Schlossprofil:** Schwerpunkt auf persönlichem Herrschafts-/Operationszentrum, Verteidigung, Lagerung, Forschung, Verwaltung und spezialisierten Einrichtungen.

**Siedlungsprofil:** Schwerpunkt auf bewohnbarer Infrastruktur, Versorgung, Arbeitsplätzen, Produktion, Gemeinschaft und autonomer Entwicklung.

Eine gemeinsame technische Grundlage darf nicht dazu führen, dass beide Modi nur unterschiedliche Namen derselben Gebäudeliste sind. Profile müssen Regeln und Inhalte tatsächlich durchsetzen.

## 5.13 Dungeonbetrieb: Gameplay-Anforderungen

Ein Dungeon muss sowohl als erkundbarer 3D-Ort als auch als verwaltbare Einrichtung funktionieren. Raumfunktionen, Personal/Kreaturen, Versorgung, Lager, Produktion, Verteidigung und Ereignisse greifen auf dieselben persistenten Daten zu.

Für den Betrieb sind zu spezifizieren:
- Freischaltung und Besitz-/Kontrollstatus;
- Raumtypen, Bau- und Ausbauvoraussetzungen;
- verfügbare Arbeiter, Kreaturen und Rollen;
- Rohstoffvorkommen, Lagerkapazitäten und Transport;
- Produktion, Verbrauch, Unterhalt und Stillstand;
- Sicherheitslage, Angriffsarten und Verteidigungszuweisung;
- Schäden, Verluste, Reparatur und Wiederanlauf;
- Besucher, Händler, Gefangene oder andere Funktionen nur, sofern später fachlich beschlossen;
- Auswirkungen auf Quests, Fraktionen, Ökologie und regionale Wirtschaft.

Produktions- und Verteidigungsregeln müssen auch dann konsistent bleiben, wenn der Spieler nicht vor Ort ist. Die reduzierte Simulation ist in Dokument 06 geregelt; dieses Kapitel definiert die spielerischen Anforderungen und verweist für die Ausführung auf dieselben Zustandsmodelle.

## 5.14 Kreaturenrollen, Haltung und Nutzung

Kreaturen und Tiere erhalten keine voneinander unabhängigen Datenmodelle pro Gameplay-Rolle. Ein gemeinsames Lebewesen kann je nach Eignung, Bindung, Training, Alter, Gesundheit und Zuweisung als Reittier, Begleiter, Arbeitstier, Zuchttier oder Verteidiger eingesetzt werden. Nicht jede Art muss jede Rolle unterstützen.

Gameplay-Funktionen müssen den Zustand des konkreten Individuums berücksichtigen:
- Bedürfnisse, Gesundheit, Alter und Belastung;
- Temperament, Bindung und Vertrauen;
- Training, Fähigkeiten und Erfahrung;
- Herkunft, Merkmale und Vererbung;
- Haltung, Futter, Pflege und geeignete Umgebung;
- aktuelle Aufgabe, Verfügbarkeit und Weg-/Geländeeignung.

Ein Rollenwechsel darf keine individuellen Merkmale löschen oder ein neues Tier erzeugen. Zuweisungen müssen Konflikte erkennen, etwa wenn ein Tier gleichzeitig für unvereinbare Aufgaben eingeplant ist.

Die Kategorien Reittier, Begleiter, Wildtier, Haustier, Farmtier und Hoftier sind Gameplay-/Nutzungsperspektiven. Die genaue taxonomische Datenstruktur ist im Kreaturen-/Tiermodell festzulegen und darf nicht allein aus UI-Kategorien abgeleitet werden.

## 5.15 Zucht als spielbarer Prozess

Zucht ist mehr als ein zufälliger Knopf mit Ergebnisobjekt. Sie soll als nachvollziehbarer Vorgang mit Auswahl, Kompatibilität, Voraussetzungen, Zeit, Versorgung, Risiken und individueller Nachkommenschaft umgesetzt werden.

Der Prozess muss mindestens folgende Fragen abbilden können, sobald die Regeln beschlossen sind:
- Welche Individuen können miteinander gezüchtet werden?
- Welche Anforderungen gelten für Art, Geschlecht, Alter, Gesundheit und Umgebung?
- Welche Merkmale können vererbt, kombiniert oder neu ausgeprägt werden?
- Wie werden Abstammung und Generationen dokumentiert?
- Welche Rolle spielen Pflege, Ernährung, Training, Magie oder besondere Orte?
- Welche Grenzen verhindern triviale oder unendliche Optimierung?
- Wie werden Geburt/Schlupf, Aufzucht, Reife und Verluste dargestellt?

Es werden hier bewusst keine Vererbungswahrscheinlichkeiten oder genetischen Formeln festgelegt. Diese müssen gemeinsam entworfen, im Editor konfigurierbar und durch reproduzierbare Tests überprüfbar sein.

## 5.16 Bedienbarkeit, Feedback und Barrierearmut

Gameplay-Systeme müssen ihren Zustand verständlich kommunizieren. Der Spieler soll erkennen können:
- welche Aktion verfügbar ist und warum eine andere nicht verfügbar ist;
- welche Voraussetzung fehlt;
- welche Kosten, Risiken und Konsequenzen vor einer bestätigungspflichtigen Aktion entstehen;
- ob ein Vorgang läuft, pausiert, blockiert oder abgeschlossen ist;
- welche Welt- oder Questzustände sich geändert haben.

Rückmeldungen müssen zur Situation passen und dürfen nicht ausschließlich über Farbe vermittelt werden. Wichtige Verwaltungsaktionen benötigen Bestätigung bzw. eine sichere Rücknahmeoption, sofern irreversible Folgen nicht ausdrücklich Teil der Spielentscheidung sind.

Konkrete Eingabebelegung, UI-Layouts, Accessibility-Zielwerte und Plattformvorgaben werden in den entsprechenden UI-/Plattform- und QA-Dokumenten spezifiziert.

## 5.17 Persistenz, Fehlerbehandlung und Wiederherstellung

Alle gameplayrelevanten Änderungen müssen in den kanonischen Welt-, Charakter-, Quest-, Wirtschafts- oder Kreaturenzuständen landen. Temporäre UI-Zustände dürfen nicht als dauerhafte Spielwahrheit dienen.

Zu berücksichtigen sind:
- Speichern während bzw. nach längeren Aktionen;
- Unterbrechung durch Kampf, Szenenwechsel, Regionwechsel oder Spielende;
- doppelte Ereignisauslösung und wiederholte Belohnungen;
- fehlende oder veraltete Referenzen;
- teilweise fehlgeschlagene Produktions-, Bau- oder Zuchtvorgänge;
- Laden älterer Speicherstände nach Daten-/Versionsänderungen;
- nachvollziehbare Wiederherstellung ohne Duplizieren oder stilles Löschen von Fortschritt.

Aktionen mit mehreren Auswirkungen müssen als konsistente Transaktion oder mit einer gleichwertigen Wiederherstellungsstrategie umgesetzt werden. Ein Fehler darf beispielsweise nicht Items abziehen, ohne den zugehörigen Baufortschritt zu speichern.

## 5.18 Editor- und Testabdeckung

Jedes Gameplay-System benötigt passende Erstellungs-, Konfigurations-, Prüf- und Debugwerkzeuge. Ein Editor gilt nicht als vollständig, wenn er nur Datenfelder anzeigen kann.

Für die Systeme dieses Dokuments sind insbesondere erforderlich:
- Questdefinitionen, Ablaufvorschau, Referenzprüfung und Laufzeitsimulation;
- Interaktionsdefinitionen und Prüfung ihrer Voraussetzungen/Ergebnisse;
- Kampf-/Fähigkeitsdaten, Begegnungsszenarien und reproduzierbare Testläufe;
- Bauprofile, Gebäudefunktionen, Platzierungs- und Kostenvalidierung;
- Dungeonraumprofile, Produktionsketten und Angriffssimulation;
- Kreaturenprofile, Rollenkompatibilität, Haltung und Zuchtlinien;
- Inspektoren für persistente Zustände und Ereignisverläufe.

Alle Systeme müssen in kleinen, eigenständig prüfbaren Arbeitsschritten entstehen. Nach jedem relevanten Schritt ist eine funktionale und visuelle Zwischenversion bereitzustellen. Platzhalter, nicht verbundene Daten und nur simulierte Funktionen sind ausdrücklich zu kennzeichnen.

## 5.19 Abgrenzung und offene Spezifikation

Dieses Dokument beschreibt Gameplay-Ziele und Systemanforderungen. Es ersetzt nicht:
- die Prüfung und Migration bestehender Quest-, Item-, Charakter- und Kreaturendaten;
- die konkrete Unity-Laufzeitarchitektur;
- die technische Simulationsarchitektur aus Dokument 06;
- das kanonische Wirtschafts-/Itemmodell aus Dokument 13;
- die vollständige UI-/Web-/Plattform-Spezifikation;
- konkrete Balancingwerte, Formeln oder endgültige Bedienkonzepte.

Wo bestehende Quellen noch nicht erneut eingelesen wurden, sind Anforderungen als konzeptionell zu behandeln. Vor Implementierung sind Quellenabgleich, Dateninventar, Spezifikation, Testfälle und Migrationsplan vorzulegen.

## 5.20 Offene Entscheidungen

| ID | Thema | Status |
|---|---|---|
| GAME-001 | Vollständige Interaktionsarten, Kontextregeln und Abbruchverhalten | Offen |
| GAME-002 | Bestehende Kampfregeln, Trefferlogik und Aktionszustände | Quellenabgleich erforderlich |
| GAME-003 | Kampfressourcen, Effekte, Widerstände und Niederlagenfolgen | Offen |
| GAME-004 | Verbindliche Verknüpfung von Questentscheidungen mit persistenten Weltzuständen | Offen |
| GAME-005 | Bauplatzierung: Raster, Freiform oder kontextabhängiges Hybridverfahren | Offen |
| GAME-006 | Baukosten, Bauzeit, Materialtransport und Arbeitskräfteberechnung | Offen |
| GAME-007 | Schloss-/Siedlungsrechte, Grenzen und Besitz-/Kontrollmodell | Offen |
| GAME-008 | Dungeonbesitz, Personal, Unterhalt, Angriffe und Wiederherstellung | Offen |
| GAME-009 | Konkrete Raumtypen und Funktionsprofile für Dungeons | Offen |
| GAME-010 | Kreaturenrollen-Kompatibilität und Zuweisungsregeln | Offen |
| GAME-011 | Definition und Abgrenzung von Hoftieren | Gemeinsam festzulegen |
| GAME-012 | Zuchtregeln, Genetik, Wahrscheinlichkeiten und Generationseffekte | Offen |
| GAME-013 | Gameplay-UI, Eingabebelegung und Accessibility-Anforderungen | Offen |
| GAME-014 | Speichern/Wiederherstellen mehrstufiger Gameplay-Aktionen | Technische Spezifikation erforderlich |
| GAME-015 | Vollständiger Abgleich des vorhandenen Quest-JSON und Quest-Editors | Quellenabgleich erforderlich |
