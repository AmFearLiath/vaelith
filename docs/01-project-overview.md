# 01 — Vaelith: Gesamtkonzept und Spielvision

> **Dokumenttyp:** Übergeordnetes Produkt- und Game-Design-Leitdokument  
> **Status:** Arbeitsfassung zur gemeinsamen Abstimmung  
> **Geltungsbereich:** Identität, Zielerlebnis, Kernpfeiler, Systemverbund und langfristige Spielvision  
> **Verbindlichkeit:** Als Leitlinie für die nachfolgenden Konzeptdokumente gedacht. Offene Punkte sind ausdrücklich keine beschlossenen Features.  
> **Technische Grundlage:** Eigenständige Entwicklung als vollständiges 3D-Spiel in Unity  
> **Projektregel:** Vaelith bleibt vollständig unabhängig von ASHFALL.

---

## 1.1 Zweck dieses Dokuments

Dieses Dokument beschreibt, was Vaelith als Spiel sein soll, welches Erlebnis es vermitteln möchte und nach welchen übergeordneten Prinzipien seine Inhalte und Systeme zusammenwirken.

Es ist die gemeinsame konzeptionelle Grundlage für Game Design, Story und Lore, Weltgenerierung, Gameplay-Systeme, Simulation, Datenmodelle, Editor-Werkzeuge und spätere technische Architektur.

Es soll insbesondere verhindern, dass einzelne Systeme unabhängig voneinander geplant werden und dadurch ein Spiel entsteht, dessen Bestandteile zwar für sich funktionieren, aber keine glaubwürdige gemeinsame Welt bilden.

Die nachfolgenden Fachkonzepte müssen mit dieser Spielvision vereinbar sein. Wenn ein Fachkonzept eine wesentliche Änderung an der Spielidentität oder am Spielerlebnis erfordert, muss diese Abweichung sichtbar gemacht und gemeinsam entschieden werden.

### Statuskennzeichnung

- **Leitplanke:** Im gemeinsamen Projektkontext klar als Vorgabe festgehalten.
- **Arbeitskonzept:** Eine bereits konkretisierte Richtung, die noch gemeinsam bestätigt oder präzisiert werden muss.
- **Offen:** Benötigt eine spätere inhaltliche, gestalterische oder technische Entscheidung.
- **Abgeleitet:** Eine konzeptionelle Folgerung aus bestehenden Leitplanken, noch keine eigenständige verbindliche Entscheidung.

---

## 1.2 Was ist Vaelith?

**Vaelith ist ein umfangreiches, vollständig dreidimensionales Abenteuer-Rollenspiel mit Action-RPG-Elementen und einer persistenten, lebendigen Welt.**

Im Mittelpunkt steht eine große Welt, die nicht nur als Kulisse für die Handlungen des Spielers dient. Regionen, Siedlungen, Bewohner, Kreaturen, Ökosysteme, Ressourcen, Produktionsketten, Interessen und Ereignisse besitzen eigene Zustände und Zusammenhänge. Sie reagieren auf Veränderungen und entwickeln sich innerhalb der Regeln der Spielwelt weiter – auch dann, wenn der Spieler nicht unmittelbar anwesend ist.

Der Spieler entdeckt diese Welt zunächst als Abenteurer. Er erkundet unbekannte Gebiete, begegnet ihren Bewohnern, erfährt ihre Geschichten, stellt sich Gefahren und entwickelt seine Fähigkeiten. Mit zunehmendem Fortschritt erhält er Möglichkeiten, die weit über die persönliche Charakterentwicklung hinausgehen: Er kann Einrichtungen aufbauen, Siedlungen gestalten, Dungeons betreiben, Kreaturen halten und züchten sowie Einfluss auf wirtschaftliche und gesellschaftliche Zusammenhänge nehmen.

Die Weltgestaltung ist damit kein vom Rollenspiel losgelöster Zusatzmodus. Sie ist eine Erweiterung dessen, was der Spieler innerhalb derselben Spielwelt tun, erreichen und verantworten kann.

### Das zentrale Spielversprechen

Vaelith soll dem Spieler das Gefühl vermitteln, **eine Welt zu entdecken, in der er nicht der Mittelpunkt aller Vorgänge ist – und in der seine Entscheidungen dennoch etwas verändern können.**

Der Spieler soll nicht nur Inhalte freischalten. Er soll Zusammenhänge verstehen, Verantwortung übernehmen, eigene Ziele entwickeln und allmählich erkennen, welche Reichweite seine Handlungen besitzen.

---

## 1.3 Genre und konzeptionelle Einordnung

### Primäres Genre

- 3D-Abenteuer-Rollenspiel.

### Zentrale spielerische Ausprägung

- Action-RPG mit direkter Steuerung, Erkundung, Kampf, Fähigkeiten, Ausrüstung und Charakterentwicklung.
- Story- und questgetriebene Spielerfahrung mit langfristigen Enthüllungen und Konsequenzen.
- Lebendige Welt mit NPCs, Fraktionen, Ökologie, Wirtschaft und persistierenden Zuständen.
- Aufbau- und Managementelemente, die schrittweise innerhalb der Spielwelt erschlossen werden.
- Kreaturen- und Tierhaltung einschließlich Pflege, Ausbildung, Nutzung und Zucht.

### Ergänzende Spielsysteme

- Schloss- und Siedlungsbau.
- Ausbau, Betrieb und Verteidigung befreiter Dungeons.
- Ressourcenwirtschaft, Herstellung, Handel und Logistik.
- Landwirtschaft und Tierhaltung.
- Kreaturenmanagement und Zucht.
- Prozedurale Welt- und Regionsgenerierung.
- Umfangreiche interne Editor- und Entwicklungswerkzeuge.
- Modding und Erweiterbarkeit über eine offizielle Vaelith-Modding-Schnittstelle.

Diese Einordnung beschreibt die Zielrichtung. Sie legt noch keine konkrete Spielzeit, Weltgröße, Anzahl an Regionen, Schwierigkeitskurve oder Veröffentlichungsversion fest.

### Keine Sammlung unabhängiger Spielmodi

Die ergänzenden Systeme dürfen nicht wie voneinander getrennte Minispiele wirken. Sie teilen sich die Welt, ihre Daten, Bewohner, Ressourcen, Zeit, Ereignisse und Konsequenzen.

Ein im Dungeon gewonnener Rohstoff kann beispielsweise in einer Werkstatt verarbeitet werden. Das daraus hergestellte Produkt kann in einer Siedlung benötigt, gehandelt oder für den Ausbau des Schlosses verwendet werden. Die dafür eingesetzten Kreaturen besitzen Bedürfnisse, Fähigkeiten und Beziehungen. Die Produktion hängt von Versorgung, Arbeitskraft, Infrastruktur und Sicherheit ab.

Der Wert eines Systems entsteht damit auch aus seinen Verbindungen zu anderen Systemen.

---

## 1.4 Die Spielerfantasie

Vaelith soll mehrere miteinander verbundene Spielerfantasien bedienen. Sie werden nicht alle gleichzeitig zu Beginn freigeschaltet, sondern entwickeln sich mit dem Fortschritt und den erzählerischen Möglichkeiten.

### 1.4.1 Die Welt entdecken

Der Spieler erkundet eine große, dreidimensionale Welt mit unterschiedlichen Landschaften, Biomen, Regionen, Orten und Kulturen.

Er kann sich nicht nur über ebene Flächen bewegen. Die Welt umfasst Höhenunterschiede, Hänge, steile Felsformationen, mehrstöckige Gebäude, Brücken, Höhlen, Tunnel, unterirdische Räume und weitere vertikale Strukturen.

Erkundung soll Neugier belohnen: durch Orte, Geheimnisse, Ressourcen, Begegnungen, Geschichten und Veränderungen, die nicht ausschließlich über Questmarkierungen vermittelt werden.

### 1.4.2 Die eigene Rolle entwickeln

Der Spieler baut seinen Charakter durch Fähigkeiten, Ausrüstung, Magie, Erfahrungen, Beziehungen und Entscheidungen auf.

Fortschritt soll nicht ausschließlich aus höheren Zahlen bestehen. Neue Fähigkeiten und Möglichkeiten sollen die Art verändern, wie der Spieler Herausforderungen angeht und mit der Welt interagiert.

Die persönliche Entwicklung ist eng mit der Geschichte und der besonderen Herkunft des Spielers verknüpft. Die genaue Ausgestaltung des Charakter-, Fähigkeits- und Magiesystems wird in den jeweiligen Fachkonzepten festgelegt.

### 1.4.3 In der Welt leben

Die Welt soll mehr bieten als Kampf und Questfortschritt. Der Spieler kann sich mit ihrer Infrastruktur, ihren Bewohnern und ihren wirtschaftlichen Zusammenhängen beschäftigen.

Dazu gehören unter anderem Versorgung, Herstellung, Handel, Landwirtschaft, Tierpflege, Ausbildung, Beziehungen, Unterkünfte und die Entwicklung eigener Einrichtungen.

Diese Aktivitäten müssen in die Zeit- und Wirtschaftssysteme der Welt eingebunden sein. Sie dürfen nicht lediglich dekorative Menüs ohne Auswirkungen auf den Weltzustand sein.

### 1.4.4 Die Welt gestalten

Im späteren Verlauf erhält der Spieler zunehmend Möglichkeiten, seine Umgebung aktiv zu verändern.

Dazu zählen der Ausbau einer eigenen Schlossanlage, die Entwicklung einer Siedlung und die Nutzung befreiter Dungeons als ausbaubare Einrichtungen. Bewohner und Kreaturen können Aufgaben übernehmen; Infrastruktur, Versorgung und Sicherheit beeinflussen den Betrieb.

Schloss- und Siedlungsbau werden über den Spielverlauf und die Geschichte erschlossen. Sie sind nicht einfach ab Spielbeginn vollständig verfügbar.

Die endgültige Architektur und Formensprache dieser Einrichtungen muss zur noch gemeinsam zu finalisierenden Weltgestaltung passen. Funktionsbeispiele wie Türme, Werkstätten, Märkte oder Verteidigungsanlagen sind keine verbindliche Festlegung auf eine rein mittelalterliche Ästhetik.

### 1.4.5 Verantwortung übernehmen

Mit wachsendem Einfluss nehmen auch die möglichen Folgen der eigenen Entscheidungen zu.

Der Spieler soll erkennen, dass Macht und Handlungsmöglichkeiten nicht automatisch bedeuten, dass jede Intervention sinnvoll ist. Das gilt für persönliche Beziehungen ebenso wie für Siedlungen, Kreaturen, Wirtschaft, Konflikte und größere Weltzustände.

Diese Spielerfantasie verbindet das Gameplay mit dem zentralen Thema der Geschichte: **Macht, Verantwortung, Zurückhaltung und die Folgen gut gemeinter Eingriffe.**

---

## 1.5 Die zentralen Designpfeiler

Die folgenden Pfeiler bilden die wesentlichen Qualitäts- und Gestaltungsziele von Vaelith. Neue Features müssen mindestens zu einem dieser Pfeiler beitragen und dürfen den Zusammenhang der anderen nicht beschädigen.

### Pfeiler 1 — Eine erkundbare, echte 3D-Welt

Vaelith ist ein vollständig dreidimensionales Spiel. Geografie, Gebäude, Höhlen, Wege und Hindernisse müssen räumlich nachvollziehbar sein.

Die Welt unterstützt Bewegung in allen relevanten Raumdimensionen. Höhenunterschiede und vertikale Verbindungen sind spielerisch und technisch echte Bestandteile der Umgebung, keine bloße optische Darstellung.

**Daraus folgt:**
- Terrain und Bauwerke müssen begehbare und nicht begehbare Bereiche korrekt unterscheiden.
- Navigation muss Höhen, Steigungen, Treppen, Brücken, mehrstöckige Gebäude und unterirdische Bereiche berücksichtigen.
- Kamera, Bewegung, Interaktion und Kampf müssen für die räumliche Welt gemeinsam gestaltet werden.
- Erkundung darf nicht auf eine flache Kartenansicht reduziert werden.

### Pfeiler 2 — Eine lebendige und nachvollziehbare Welt

Die Welt besitzt eigene Abläufe und Interessen. Bewohner, Fraktionen, Tiere, Kreaturen, Siedlungen, Ressourcen und Produktionsketten existieren nicht ausschließlich für den Spieler.

**Daraus folgt:**
- NPCs besitzen je nach Bedeutung und Rolle Bedürfnisse, Aufgaben, Beziehungen und Verhaltensweisen.
- Siedlungen benötigen Versorgung, Arbeitsplätze, Infrastruktur und Ressourcen.
- Tiere und Kreaturen folgen eigenen Verhaltens- und Lebenszyklen.
- Wirtschaft und Ökologie müssen nachvollziehbare Zusammenhänge besitzen.
- Weltzustände und Ereignisse müssen persistent und reproduzierbar fortgeführt werden.
- Die Simulation darf nach Relevanz und Entfernung abgestuft werden, ohne inkonsistente Ergebnisse zu erzeugen.

### Pfeiler 3 — Eine persönliche Entwicklung mit erzählerischer Bedeutung

Charakterentwicklung, Fähigkeiten, Ausrüstung, Magie und Questfortschritt sind mit der Geschichte des Spielers verbunden.

Der Spieler soll nicht nur stärker werden, sondern zunehmend verstehen, welche Rolle er in der Welt einnimmt und welche Verantwortung daraus entstehen kann.

**Daraus folgt:**
- Fortschritt muss neue Möglichkeiten und Entscheidungen eröffnen.
- Quests sollen Weltzustände und Beziehungen verändern können.
- Die Geschichte muss Raum für Entdeckungen, Zweifel und spätere Neubewertungen lassen.
- Die Herkunft des Spielers darf seine Persönlichkeit und Entscheidungsfreiheit nicht ersetzen.

### Pfeiler 4 — Magie und Verantwortung

Magie ist ein wesentlicher Bestandteil der Welt und der Spielerentwicklung. Sie eröffnet besondere Handlungsoptionen, darf aber nicht von der zentralen Thematik der Verantwortung getrennt werden.

Die Geschichte von Vaelith verdeutlicht, dass große Macht kein vollständiges Verständnis und keine sichere Kenntnis aller Folgen bedeutet.

**Daraus folgt:**
- Magie muss in Welt, Geschichte und Gameplay glaubwürdig verankert sein.
- Die Zurückhaltung Vaeliths beruht auf seiner bewussten Entscheidung und seinem Eid, nicht auf einer künstlichen Begrenzung seiner Macht.
- Der Spieler soll eigene Entscheidungen treffen können.
- Konsequenzen müssen aus nachvollziehbaren Weltzusammenhängen entstehen und dürfen nicht nur als beliebige Bestrafung dienen.

### Pfeiler 5 — Eine Welt, die gestaltet und verändert werden kann

Der Spieler entwickelt sich vom Erkundenden zum Gestalter. Schloss, Siedlung und Dungeon sind reale Bestandteile der Welt und nicht voneinander getrennte Managementoberflächen.

**Daraus folgt:**
- Bauwerke besitzen Funktionen und beeinflussen die Welt.
- Bewohner benötigen sinnvolle Aufgaben, Arbeitsplätze und Versorgung.
- Produktion und Lagerung sind mit Ressourcen und Wirtschaft verbunden.
- Verteidigung und Sicherheit wirken auf den Betrieb von Einrichtungen.
- Bau- und Verwaltungssysteme müssen mit der dreidimensionalen Spielwelt kompatibel sein.

### Pfeiler 6 — Lebewesen mit Identität und Funktion

Tiere und Kreaturen sind keine austauschbaren Ressourcenobjekte. Sie besitzen individuelle Eigenschaften und können unterschiedliche Rollen im Spiel übernehmen.

Dazu zählen unter anderem Wildtiere, Haustiere, Nutztiere, Reittiere, Begleiter und besondere Hoftiere. Die Rollen eines Lebewesens können von Eigenschaften, Training, Zuweisung und Situation abhängen.

**Daraus folgt:**
- Ein gemeinsames Grundlagenmodell für Lebewesen ist anzustreben.
- Bedürfnisse, Verhalten, Gesundheit, Alter, Beziehungen und Lebenszyklus müssen berücksichtigt werden.
- Zucht und Vererbung können individuelle Eigenschaften weitergeben.
- Die Rolle eines Tieres darf nicht ausschließlich durch eine starre Kategorie bestimmt sein.
- Lebewesen müssen in Ökologie, Wirtschaft, Animation und Simulation integriert sein.

### Pfeiler 7 — Zusammenhängende Systeme statt isolierter Features

Jedes größere System muss in einem übergreifenden Weltmodell funktionieren.

**Daraus folgt:**
- Gemeinsame Datenmodelle, stabile IDs und explizite Referenzen sind erforderlich.
- NPCs, Items, Gebäude, Quests, Kreaturen, Orte und Fraktionen dürfen keine widersprüchlichen Paralleldefinitionen erhalten.
- Änderungen müssen betroffene Abhängigkeiten erkennen und validieren können.
- Laufzeit, Editor, Speicherung und Simulation müssen denselben relevanten Datenbestand verwenden.

### Pfeiler 8 — Werkzeuge, mit denen die Welt vollständig erstellt werden kann

Die geplante interne Editor- und Tool-Suite ist ein wesentlicher Bestandteil des Projekts.

Ein Werkzeug gilt nicht als fertig, nur weil eine Oberfläche existiert. Es muss den vollständigen fachlichen Arbeitsablauf abdecken und mit den übrigen Werkzeugen und Laufzeitsystemen verbunden sein.

**Daraus folgt:**
- Daten bearbeiten, prüfen, speichern und wieder laden.
- Abhängigkeiten und Referenzen validieren.
- Vorschau und nachvollziehbare Fehlerdiagnose anbieten.
- Ergebnisse zuverlässig in die Spielwelt integrieren.
- Gemeinsame Datenmodelle und konsistente Bedienprinzipien verwenden.
- Arbeitsabläufe aus Sicht der tatsächlichen Content-Produktion prüfen.

### Pfeiler 9 — Erweiterbarkeit ohne Abhängigkeit von Erweiterungen

Vaelith soll von Anfang an auf Erweiterbarkeit vorbereitet werden. Modding ist ein unterstütztes Ökosystem, darf aber keine Voraussetzung für das vollständige Grundspiel sein.

Als Grundlage ist BepInEx vorgesehen; darauf soll eine offizielle Vaelith Mod API in C# aufbauen. Die konkrete technische Kompatibilität muss früh geprüft werden.

Datenbasierte Mods und ausführbare Code-Mods sind unterschiedlich zu behandeln. Für beliebige C#-Plugins darf keine nicht vorhandene Sandbox-Sicherheit versprochen werden.

---

## 1.6 Das Zusammenspiel der Systeme

Die Spielvision lässt sich nicht durch eine Liste einzelner Features erfüllen. Entscheidend ist, wie diese Features gemeinsame Abläufe bilden.

### Beispiel: Von der Erkundung zum eigenen Einflussbereich

Der Spieler entdeckt einen verlassenen oder von einer feindlichen Gruppe kontrollierten Dungeon. Nach einer Quest und einer Auseinandersetzung gelingt es ihm, den Ort zu befreien.

Er kann den Dungeon anschließend untersuchen, seine Räume neu organisieren und geeignete Bereiche für Lagerung, Ressourcenabbau, Kreaturenhaltung, Werkstätten oder Verteidigung einrichten.

Für den Betrieb benötigt er Lebewesen und Bewohner mit passenden Fähigkeiten. Diese müssen versorgt, zugewiesen und geschützt werden. Ressourcen aus dem Dungeon können in Produktionsketten einfließen und an andere Einrichtungen weitergegeben werden.

Das Schloss kann bestimmte Materialien verarbeiten oder lagern. Eine Siedlung kann Arbeitskräfte, Versorgung oder Handelsmöglichkeiten bereitstellen. Ereignisse und Angriffe können die Sicherheit und Produktion beeinflussen. Der Spieler kann persönlich eingreifen oder geeignete Aufgaben delegieren.

Ein einzelner Dungeon verbindet damit:
- Erkundung und Questfortschritt;
- Kampf und Verteidigung;
- Gebäude- und Raumgestaltung;
- Kreaturen- und NPC-Systeme;
- Ressourcen und Wirtschaft;
- Produktion und Lagerhaltung;
- Weltzeit und Ereignisse;
- langfristige Persistenz.

Dieses Beispiel beschreibt die gewünschte Systemintegration. Es ist keine abschließend festgelegte Quest, Produktionsformel oder Belohnungsstruktur.

### Beispiel: Ein Tier als Bestandteil mehrerer Systeme

Ein Tier kann zunächst als wildes Lebewesen in einem Biom auftreten. Es besitzt Eigenschaften, Bedürfnisse und ein Verhalten, das zu seiner Art und Umgebung passt.

Wird es gezähmt oder gezüchtet, kann es abhängig von seinen Eigenschaften und seiner Ausbildung weitere Rollen übernehmen: als Reittier, Begleiter, Arbeitstier oder Teil einer Zuchtlinie.

Seine Ernährung und Gesundheit beeinflussen Pflege und Betrieb. Seine Fähigkeiten können Erkundung, Transport, Verteidigung oder Produktion unterstützen. Seine Nachkommen können bestimmte Eigenschaften erben.

Damit verbindet ein Lebewesen:
- Biome und Ökologie;
- KI und Verhalten;
- Animation und Interaktion;
- Zähmung und Ausbildung;
- Zucht und Genetik;
- Wirtschaft und Versorgung;
- Kampf, Erkundung und Transport;
- persistente Weltzustände.

---

## 1.7 Die Spielerfahrung im Verlauf

Die nachfolgende Gliederung ist eine übergeordnete Progressions- und Dramaturgie-Leitlinie. Sie ist keine endgültige Kapitel-, Quest- oder Freischaltliste.

### Phase 1 — Entdecken

Der Spieler beginnt mit einer persönlichen Geschichte und einem begrenzten Verständnis seiner Herkunft und der Welt.

Er begegnet den ersten Konflikten, erkundet seine unmittelbare Umgebung, lernt grundlegende Spielmechaniken und erhält Hinweise auf Zusammenhänge, die sein bisheriges Leben infrage stellen.

Die ersten Spielstunden sollen die Welt nicht durch eine vollständige Erklärung entzaubern. Informationen werden über Begegnungen, Orte, Dialoge, Ereignisse und Quests vermittelt.

### Phase 2 — Lernen und bestehen

Der Spieler erweitert seine Fähigkeiten und sein Verständnis der Spielwelt. Er lernt, Gefahren zu bewältigen, Beziehungen aufzubauen und die Konsequenzen seiner Entscheidungen einzuschätzen.

Die Welt wird größer und komplexer. Neue Regionen, Systeme und Verantwortlichkeiten werden zugänglich.

### Phase 3 — Möglichkeiten erschließen

Mit zunehmendem Fortschritt werden zusätzliche Systeme freigeschaltet. Dazu gehören die weitergehende Nutzung von Magie, die Verwaltung eigener Einrichtungen sowie der Ausbau von Dungeon, Schloss und Siedlung.

Die Freischaltung erfolgt im vorgesehenen Zusammenhang mit Geschichte und Quests, nicht pauschal allein durch das Erreichen einer Charakterstufe.

### Phase 4 — Gestalten und vernetzen

Der Spieler beginnt, die Welt nicht nur zu nutzen, sondern aktiv zu gestalten.

Einrichtungen werden ausgebaut, Bewohner und Kreaturen übernehmen Aufgaben, wirtschaftliche Abläufe entstehen und die eigenen Entscheidungen beeinflussen zunehmend größere Zusammenhänge.

### Phase 5 — Verantwortung übernehmen

Der Spieler verfügt über weitreichende Handlungsmöglichkeiten. Die Herausforderung besteht nicht mehr nur darin, etwas erreichen zu können, sondern darin, zu entscheiden, was getan werden sollte und welche Folgen vertretbar sind.

Diese Phase führt die mechanische und erzählerische Entwicklung zusammen.

---

## 1.8 Welt, Setting und Atmosphäre

**Aktuelle Arbeitsrichtung:** Science-Fantasy mit futuristischen, technologischen, magischen und mystischen Elementen.

Die Welt soll nicht als konventioneller Weltraum-Shooter verstanden werden. Technologie und Magie existieren in einer gemeinsamen fantastischen Welt. Unterschiedliche Kulturen und Entwicklungsstände können nebeneinander bestehen, sofern sie durch Weltgeschichte, Isolation, Ressourcen, Kultur oder andere nachvollziehbare Umstände erklärt werden.

Denkbar sind beispielsweise:
- technologisch fortgeschrittene Städte und Gesellschaften;
- abgelegene Kolonien und Siedlungen;
- traditionell oder vergleichsweise einfach organisierte Kulturen;
- uralte Zivilisationen und Ruinen;
- magische Orte und mystische Phänomene;
- fremdartige Ökosysteme, Tiere und Kreaturen.

Diese Beispiele sind keine endgültige Festlegung auf bestimmte Völker, Orte, Technologien oder historische Epochen.

Die bereits vorhandenen Begriffe **Oberwelt** und **Unterwelt** sind zentrale Bestandteile der bisherigen Geschichte. Ihre genaue Kosmologie und ihre Beziehung zur übergreifenden Weltstruktur müssen in den Lore-Dokumenten weiter ausgearbeitet werden.

### Atmosphärisches Ziel

Die Welt soll Neugier, Entdeckungsfreude und das Gefühl einer größeren, nicht vollständig verstandenen Geschichte erzeugen. Sie darf Geheimnisse besitzen und Fragen offenlassen, muss aber in ihren Regeln und Konsequenzen nachvollziehbar bleiben.

Die genaue visuelle Identität, Farb- und Materialwelt, musikalische Ausrichtung und das Verhältnis von futuristischen zu traditionellen Architekturen sind noch zu konkretisieren.

---

## 1.9 Qualitätsanspruch

Vaelith soll als hochwertiges 3D-Spiel umgesetzt werden. Visuelle Qualität ist dabei nur ein Teil der Gesamtqualität.

Ein überzeugender Einzelbereich reicht nicht aus, wenn andere grundlegende Aspekte unzuverlässig sind. Weltstreaming, Navigation, Simulation, Persistenz, Datenpflege und Bedienbarkeit müssen gemeinsam funktionieren.

### Visuelle und räumliche Qualität

- Hochwertige und konsistente Darstellung der Welt.
- Glaubwürdige Materialien, Beleuchtung und Umgebungen.
- Räumlich nachvollziehbare Architektur und Landschaft.
- Geeignete Animationen für Spieler, NPCs, Tiere und Kreaturen.
- Konsistente visuelle Identität trotz unterschiedlicher Biome und Kulturen.

### Spielerische Qualität

- Zuverlässige Steuerung und Interaktion.
- Verständliche und faire Spielregeln.
- Nachvollziehbare Quests und Konsequenzen.
- Sinnvoller Fortschritt und verständliche Rückmeldungen.
- Keine künstliche Trennung zusammengehöriger Spielsysteme.

### Technische Qualität

- Stabilität und verlässliche Speicherung.
- Kontrollierbares Welt- und Region-Streaming.
- Skalierbare Simulation.
- Reproduzierbare Generierung.
- Validierbare und versionierbare Daten.
- Fehlerdiagnose und Testbarkeit.
- Wartbare und erweiterbare Architektur.

### Produktionsqualität

- Vollständige, tatsächlich nutzbare Editoren.
- Einheitliche Daten- und Referenzstandards.
- Dokumentierte Assetherkunft und Lizenzbedingungen.
- Nachvollziehbare Änderungen und Migrationen.
- Tests entlang realer Arbeitsabläufe.

Konkrete Qualitätsmetriken, Performancebudgets, Mindesthardware und visuelle Zielbenchmarks werden in den entsprechenden Fachkonzepten festgelegt.

---

## 1.10 Projektumfang und Abgrenzung

### Bestandteil der Zielvision

- Vollständiges 3D-Abenteuer-Rollenspiel mit Action-RPG-Elementen.
- Prozedural erzeugte Weltkarte und schrittweise entwickelte Regionen.
- Erkundung, Kampf, Charakterentwicklung, Magie und Quests.
- Lebendige Welt mit NPCs, Fraktionen, Ökologie und Wirtschaft.
- Schloss-, Siedlungs- und Dungeon-Systeme.
- Tiere, Kreaturen, Pflege, Ausbildung und Zucht.
- Herstellung, Ressourcen, Produktion und Handel.
- Umfangreiche interne Editor- und Entwicklungswerkzeuge.
- Modding als unterstützte Erweiterungsmöglichkeit.
- Website und Administration als eigenständige, mit dem Spiel abgestimmte Bereiche.

### Bewusste Abgrenzungen

- Vaelith ist kein reines Aufbauspiel, kein reiner Dungeon-Manager und kein reiner Wirtschaftssimulator. Diese Elemente ergänzen das zentrale Abenteuer-Rollenspiel.
- Vaelith ist kein konventioneller Weltraum-Shooter. Science-Fantasy ist die aktuelle Setting-Richtung, nicht die Aufgabe des Abenteuer- und Rollenspielkerns.
- Die Welt ist nicht als vollständig handgezeichnete Pflichtkarte vorgesehen. Die geografische Grundlage wird prozedural erzeugt und über geeignete Werkzeuge kontrolliert.
- Die Welt muss nicht von Beginn an in jeder Region vollständig generiert und mit Inhalten gefüllt sein.
- Modding ist keine Voraussetzung für die Funktionalität des Grundspiels.
- Es werden keine ASHFALL-spezifischen Inhalte, Assets, Strukturen, Algorithmen, Szenen, Shader oder sonstigen projektspezifischen Bestandteile übernommen.
- Unbestätigte technische oder quantitative Beispiele werden nicht als verbindliche Produktversprechen behandelt.

### Noch nicht abschließend festgelegter Umfang

Folgende Punkte bleiben offen, bis sie gesondert entschieden und dokumentiert wurden:
- Zielplattformen und Mindesthardware.
- Einzelspieler-, Koop- oder Multiplayer-Zielumfang.
- Online- und Offline-Anforderungen sowie mögliche Backend-Abhängigkeiten.
- Weltmaßstab, Anzahl und Größe der Regionen.
- Umfang und Struktur der Start- und Veröffentlichungsinhalte.
- Konkrete Release- und Erweiterungsplanung.
- Finale Setting- und Lore-Entscheidungen.
- Vollständiges Monetarisierungsmodell.

Frühere Dokumente können zu diesen Themen weiterführende Konzepte enthalten. Sie werden erst nach Quellenprüfung und Abgleich mit dem aktuellen Projektstand als Grundlage übernommen.

---

## 1.11 Grundregeln für alle nachfolgenden Konzepte

Aus dieser Spielvision ergeben sich folgende übergreifende Regeln:

1. **Spielerlebnis vor isolierter Featureliste:** Jedes System muss einen erkennbaren Beitrag zur Gesamtspielerfahrung leisten.
2. **Integration vor Parallelentwicklung:** Gemeinsame Weltzustände und Datenmodelle haben Vorrang vor voneinander unabhängigen Insellösungen.
3. **Nachvollziehbarkeit vor willkürlicher Komplexität:** Simulation und Konsequenzen müssen verständlich und reproduzierbar sein.
4. **Spielerautonomie:** Beratung, Storyführung und Systemregeln dürfen die Entscheidungen des Spielers nicht grundlos entwerten.
5. **Schrittweise Erschließung:** Komplexe Systeme werden im vorgesehenen Spielverlauf freigeschaltet und eingeführt.
6. **Keine stillen Verluste:** Bestehende Inhalte, Daten, IDs, Definitionen und Ideen werden vor Änderungen inventarisiert und nachvollziehbar migriert.
7. **Offene Fragen bleiben offen:** Fehlende Festlegungen werden nicht durch Vermutungen ersetzt.
8. **Vollständige Werkzeuge:** Editor- und Produktionswerkzeuge müssen die realen Arbeitsabläufe abdecken.
9. **Technische Realisierbarkeit:** Architekturentscheidungen müssen anhand der tatsächlichen Zielplattformen, Pakete, Laufzeitumgebung und Performanceanforderungen geprüft werden.
10. **Eigenständigkeit:** Vaelith bleibt ein unabhängiges Projekt und übernimmt keine projektspezifischen ASHFALL-Bestandteile.

---

## 1.12 Offene Entscheidungen für die gemeinsame Freigabe

Die folgenden Fragen sollten im Verlauf der gemeinsamen Konzeptarbeit ausdrücklich beantwortet werden. Sie blockieren nicht die Erarbeitung der übrigen Abschnitte, markieren aber wichtige Weichenstellungen.

| ID | Frage | Vorläufiger Stand |
|---|---|---|
| VISION-001 | Ist Science-Fantasy die endgültige Setting-Richtung? | Bevorzugte Arbeitsrichtung |
| VISION-002 | Welche Plattformen sollen zum ersten Release unterstützt werden? | Offen |
| VISION-003 | Ist Vaelith zunächst als Einzelspieler-Erlebnis konzipiert? | Umfang noch zu bestätigen |
| VISION-004 | Wie stark sollen Aufbau und Management gegenüber dem Abenteuer-RPG gewichtet werden? | Zentrale Ergänzung; Gewichtung offen |
| VISION-005 | Wie viel autonome Simulation soll außerhalb der Spielregion stattfinden? | Abgestufte Simulation als Leitlinie |
| VISION-006 | Welche langfristigen Weltveränderungen durch den Spieler sind vorgesehen? | Grundidee fest; Umfang offen |
| VISION-007 | Welche Monetarisierungsmodelle wurden ursprünglich festgelegt? | Quellenabgleich erforderlich |
| VISION-008 | Welche früheren Multiplayer-Konzepte bleiben Teil der Zukunftsplanung? | Quellenabgleich und Entscheidung erforderlich |

Entscheidungen werden im zentralen Entscheidungsregister festgehalten. Eine offene Frage wird erst dann als entschieden markiert, wenn die gemeinsame Entscheidung dokumentiert wurde.

---

## 1.13 Abhängige Dokumente

Dieses Dokument gibt die übergeordnete Richtung vor. Die Detaildefinitionen gehören in die jeweiligen Fachkonzepte:

- `02-design-principles.md` — konkrete Designprinzipien und verbindliche Gestaltungsregeln.
- `03-world-and-lore.md` — Kosmologie, Setting, Oberwelt, Unterwelt und Geschichte.
- `04-player-progression-and-magic.md` — Spielercharakter, Entwicklung und Magiesystem.
- `05-gameplay-systems.md` — Gameplay, Quests, Kampf, Bau- und Managementsysteme.
- `06-living-world-simulation.md` — NPCs, Wirtschaft, Ökologie und Weltzustände.
- `07-world-generation.md` — prozedurale Welt- und Regionsgenerierung.
- `08-editor-suite.md` — Produktions- und Entwicklungswerkzeuge.
- `09-data-architecture.md` — gemeinsame Datenmodelle, IDs, Referenzen und Persistenz.
- `10-unity-architecture.md` — technische Unity-Architektur.
- `11-modding-api.md` — Modding und Erweiterbarkeit.
- `13-economy-items-crafting.md` — Wirtschaft, Items, Ressourcen und Herstellung.
- `15-monetization.md` — Monetarisierung.
- `20-decisions-and-open-questions.md` — zentrale Entscheidungen, offene Fragen und Quellenlücken.

---

## 1.14 Änderungsprotokoll

| Version | Datum | Änderung |
|---|---|---|
| 0.1 | 2026-11-17 | Bestehenden Projektüberblick zu einem übergeordneten Gesamtkonzept erweitert; Spielerfantasie, Designpfeiler, Systemverbund, Progressionsphasen, Qualitätsanspruch und offene Entscheidungen ergänzt. |

**Nächster Schritt:** Gemeinsame inhaltliche Prüfung dieser Spielvision. Anschließend werden die bestätigten Aussagen in das Entscheidungsregister übernommen und die nachfolgenden Fachkonzepte darauf abgestimmt.

## 1.0 Verbindliche Einordnung: Was wird entwickelt – und wofür dient diese Dokumentation?

**Vaelith ist eine eigenständige Neuentwicklung als vollständiges 3D-Spiel in Unity.** Das Ergebnis ist ein neues Spiel unter dem Namen **Vaelith**. Es wird nicht lediglich ein vorhandenes Emberwild-Projekt umbenannt, portiert oder technisch fortgesetzt. Die technische Umsetzung, Runtime, Welt, Werkzeuge und Projektstruktur werden für Vaelith in Unity neu aufgebaut.

Vorhandene Emberwild-/Vaelith-Konzepte, Regeln, Ideen, Datenbestände, JSON-Strukturen, Kataloge und Funktionen dienen als fachliche Ausgangsquellen. Sie werden geprüft, eingeordnet und – sofern geeignet und freigegeben – in das neue Vaelith-Design und die neue Unity-Architektur übernommen, angepasst oder als Erweiterung weiterentwickelt. Sie schreiben keine alte technische Architektur oder Projektstruktur fest.

### Verbindliche Unterscheidung der Quellen- und Konzeptarten

Nicht jeder beschriebene Inhalt dieser Dokumentation ist ein verbindlicher Implementierungsauftrag. Jeder Inhalt ist sinngemäß einer der folgenden Klassen zuzuordnen:

1. **Projektleitplanke:** Verbindliche Vorgabe für die Neuentwicklung, beispielsweise Spielname Vaelith, Unity als Engine, vollständige 3D-Ausrichtung, Unabhängigkeit von ASHFALL und die festgelegten Entwicklungs-/Qualitätsregeln.
2. **Bestehendes Konzept / fachliche Grundlage:** Ein bereits vorhandenes Emberwild-/Vaelith-Konzept, eine Regel, ein Datenbestand oder eine Funktion. Es ist vor Umsetzung anhand der Originalquelle zu prüfen. Danach wird entschieden, ob es unverändert übernommen, angepasst, erweitert, ersetzt oder bewusst nicht übernommen wird.
3. **Arbeitskonzept:** Eine ausgearbeitete Zielrichtung oder Systemidee, die als Grundlage für weitere Planung dient, aber noch keine vollständige oder endgültig freigegebene Spezifikation darstellt.
4. **Funktionserweiterung:** Eine zusätzliche oder erweiterte Funktion, die das bestehende fachliche Konzept sinnvoll ergänzt. Sie wird erst dann verbindlicher Implementierungsumfang, wenn sie spezifiziert, priorisiert und für ein Arbeitspaket freigegeben wurde.
5. **Vorschlag / Beispiel / Inspiration:** Eine mögliche Lösung, ein Muster, eine beispielhafte Aufzählung oder eine Idee zur Diskussion. Sie ist ausdrücklich keine Baupflicht und darf nicht allein aufgrund ihrer Erwähnung implementiert werden.
6. **Offene Entscheidung / Quellenlücke:** Ein Punkt, für den eine Entscheidung, technische Prüfung oder Originalquelle fehlt. Der Agent muss ihn offen halten, statt ihn selbst als beschlossen festzuschreiben.

### Verbindliche Regel für Entwicklungsagenten

Der Agent muss vor jeder Implementierung erkennen und dokumentieren, welcher dieser Klassen ein betroffener Inhalt angehört. Bei Unsicherheit darf er einen Vorschlag nicht zur verbindlichen Anforderung hochstufen. Er soll die fachlich sinnvollste Empfehlung ausarbeiten und den Punkt zur Entscheidung vorlegen, sofern er den freigegebenen Umfang oder eine Leitplanke berührt.

Eine fachliche Idee kann als Ziel erhalten bleiben, obwohl ihre konkrete technische oder spielmechanische Umsetzung in Unity anders gestaltet wird. Maßgeblich ist das freigegebene Vaelith-Ziel und nicht die unveränderte Nachbildung eines früheren technischen Lösungswegs.

### Ergebnis der Neuentwicklung

- Produkt- und Spielname: **Vaelith**.
- Engine und technische Zielumgebung: **Unity**.
- Spielwelt und Spielerlebnis: **vollständig 3D** mit realer räumlicher Bewegung, Geometrie, Navigation und Interaktion.
- Technische Umsetzung: eigenständige Unity-Projektstruktur und neu entwickelte Runtime/Systemarchitektur.
- Fachliche Grundlage: geprüfte und freigegebene Konzepte, Daten, Funktionen und Inhalte aus den bisherigen Emberwild-/Vaelith-Arbeiten sowie ausdrücklich bestätigte Erweiterungen.
- Nicht-Ziel: die alte technische Implementierung unverändert fortzuführen oder sämtliche erwähnten Ideen ungeprüft zu implementieren.


## Individuelle Spielerfahrung und Wiederentdeckbarkeit — Konzept-Erweiterung

Vaelith soll nicht nur eine große Zahl miteinander verbundener Systeme anbieten. Der Spieler soll selbst bestimmen können, welche Tätigkeiten und Spielweisen er priorisiert und wie intensiv er einzelne Bereiche erlebt. Spielausrichtungen wie Abenteuer, Landwirtschaft, Handel, Transport, Handwerk, Beziehungen oder Verwaltung sind kombinierbare Schwerpunkte, keine exklusiven Klassen oder getrennten Spielmodi.

Für geeignete Funktionsbereiche soll der Spieler eine eigene Simulationstiefe wählen können: vereinfacht, normal, detailliert oder als Tiefensimulation. Diese Stufen beschreiben die gewünschte Detailtiefe, Kontrolle und Automatisierung aus Spielersicht. Sie sind ausdrücklich von der technischen Simulationsauflösung der lebendigen Welt zu unterscheiden, die weiterhin nach Entfernung, Relevanz und Simulationsbudget abgestuft werden kann.

Quest-, Story- und Freischaltfortschritt bleiben unabhängig von der gewählten Spielausrichtung. Quests prüfen reale Welt- und Spielerzustände und sollen – sofern im Questdesign vorgesehen – unterschiedliche Lösungswege unterstützen. Eine Rolle oder ein Profil darf keine Questfortschritte künstlich voraussetzen oder umgehen.

Wiederentdeckbarkeit ist ein eigenständiges Ziel: andere Spielausrichtungen, Detailstufen, Welt- und Ereignisausgänge, Entscheidungen und Erweiterungen sollen neue vollständige Spielerfahrungen ermöglichen. Das dafür vorgeschlagene Player Experience Configuration System (PECS) wird in `26-player-experience-and-replayability.md` als Arbeitskonzept beschrieben. Diese Ergänzung verändert nicht die bestehende Grundidentität des 3D-Abenteuer-RPGs mit lebendiger Welt, sondern erweitert die Freiheit, diese Welt zu erleben.
