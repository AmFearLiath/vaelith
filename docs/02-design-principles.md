# 02 — Designprinzipien und Leitplanken

> **Dokumenttyp:** Übergreifende Design- und Projektleitlinien  
> **Status:** Arbeitsfassung zur gemeinsamen Abstimmung  
> **Geltungsbereich:** Spielgestaltung, Systemintegration, Datenkontinuität, Weltlogik, technische Entscheidungen und Produktionsqualität  
> **Verbindlichkeit:** Diese Prinzipien konkretisieren die Spielvision aus `01-project-overview.md`. Grundlegende Richtungsänderungen benötigen eine dokumentierte Entscheidung.

---

## 2.1 Zweck und Anwendung

Dieses Dokument beschreibt die Regeln, nach denen Vaelith konzipiert, erweitert und später umgesetzt werden soll. Es ergänzt die Spielvision um konkrete Leitplanken für Entscheidungen.

Die Prinzipien gelten für:
- Gameplay- und Progressionssysteme;
- Welt, Lore und Erzählung;
- NPCs, Kreaturen und Simulation;
- Wirtschaft, Herstellung und Ressourcen;
- Weltgenerierung und Persistenz;
- Gebäude, Siedlungen und Dungeons;
- Editor- und Entwicklungswerkzeuge;
- Datenmodelle und technische Architektur;
- Modding und Erweiterbarkeit;
- Arbeitsabläufe und Qualitätssicherung.

Die Prinzipien sind nicht als Checkliste zu verstehen, die unabhängig vom Kontext mechanisch abgearbeitet wird. Bei Zielkonflikten müssen Auswirkungen auf das Spielerlebnis, die Weltkonsistenz, die vorhandenen Daten, die technische Tragfähigkeit und den Produktionsaufwand gemeinsam betrachtet werden.

### Statuskennzeichnung

- **Leitplanke:** Im bisherigen Projektkontext klar als Vorgabe festgehalten.
- **Arbeitsprinzip:** Aus bestehenden Entscheidungen abgeleitet und zur gemeinsamen Bestätigung vorgesehen.
- **Offen:** Benötigt eine spätere Entscheidung oder fachliche Spezifikation.

---

## 2.2 Verbindliche Arbeitsgrundsätze

### 2.2.1 Vollständigkeit vor Schein-Fertigstellung

Ein System gilt erst dann als umgesetzt, wenn es seinen vorgesehenen Zweck vollständig und zuverlässig erfüllt.

Bei einem fachlichen System umfasst dies – soweit für das System relevant:
- vollständiges Datenmodell;
- definierte Eingaben, Ausgaben und Zustände;
- fachlich vollständige Bedien- und Arbeitsabläufe;
- Validierung und verständliche Fehlermeldungen;
- Speichern, Laden und Versionsbehandlung;
- Integration in abhängige Systeme;
- Laufzeitverhalten;
- Fehlerbehandlung;
- Tests;
- Dokumentation.

Ein Editorfenster mit einigen Buttons ist kein fertiger Editor. Eine Datenstruktur ohne funktionierenden Import, Validierung und Verwendung in der Runtime ist kein vollständiges Gameplay-System. Ein NPC, der nur sichtbar in einer Szene steht, erfüllt noch keine Anforderungen an einen simulierten Bewohner.

Der konkrete Fertigstellungsumfang muss pro Arbeitspaket festgelegt werden. Nicht jedes System benötigt dieselben Funktionen, aber ausgelassene Bestandteile müssen bewusst begründet und dokumentiert werden.

### 2.2.2 Durchgängige Integration

Systeme werden nicht isoliert geplant, wenn sie im Spiel miteinander interagieren müssen.

Beispiele:
- Ein NPC aus dem NPC-System kann einer Siedlung zugeordnet sein, einen Beruf ausüben, Beziehungen besitzen, Bedürfnisse haben und in Quests referenziert werden.
- Ein Gebäude kann im World- oder Settlement-Kontext platziert werden, Räume und Funktionen bereitstellen, Navigation beeinflussen und mit Wirtschaft und Interaktionen verbunden sein.
- Ein Tier kann einem Biom entstammen, Bedürfnisse besitzen, gezähmt oder gezüchtet werden und später als Reittier, Begleiter oder Arbeitstier eingesetzt werden.
- Ein Questziel kann einen Weltzustand verändern, der wiederum NPC-Verhalten, Zugang, Wirtschaft oder Ereignisse beeinflusst.

Integration bedeutet nicht, dass jedes System jedes andere direkt kennen muss. Abhängigkeiten sollen fachlich sinnvoll und technisch kontrolliert über gemeinsame Datenmodelle, Referenzen, Schnittstellen oder Ereignisse abgebildet werden.

### 2.2.3 Gemeinsame Daten statt Insellösungen

Editoren und Runtime-Systeme verwenden gemeinsame kanonische Datenmodelle, stabile IDs und explizite Referenzen.

Zu vermeiden sind:
- voneinander abweichende Kopien derselben Definition;
- lokale Ersatz-IDs ohne nachvollziehbare Zuordnung;
- implizite Abhängigkeiten über Dateinamen oder UI-Zustände;
- Daten, die nur in einem Editor existieren und von der Runtime nicht verarbeitet werden können;
- nicht dokumentierte Sonderformate einzelner Werkzeuge.

Spezialisierte Profile dürfen unterschiedliche Inhalte, Regeln und Oberflächen besitzen. Sie sollen jedoch gemeinsame Grundlagen nutzen, wo dieselbe fachliche Entität gemeint ist.

### 2.2.4 Determinismus und Nachvollziehbarkeit

Prozedurale Systeme verwenden kontrollierte Seeds und dokumentierte Generatorversionen. Generierte Ergebnisse müssen reproduzierbar sein, soweit das jeweilige System deterministische Ergebnisse verspricht.

Änderungen an Generatoren dürfen bereits gespeicherte oder veröffentlichte Weltinhalte nicht unbeabsichtigt überschreiben oder verschieben.

Für generierte und persistente Inhalte muss nachvollziehbar sein:
- mit welcher Generator- und Datenversion sie erstellt wurden;
- welche Seed- und Konfigurationswerte relevant waren;
- welche Inhalte nach der Generierung verändert wurden;
- welche Änderungen dauerhaft gespeichert werden;
- welche Migration bei einer Versionsänderung erforderlich ist.

### 2.2.5 Konsequenzen statt bloßer Kulisse

Wirtschaftliche, ökologische, soziale und erzählerische Aktionen sollen in verbundenen Systemen nachvollziehbare Auswirkungen erzeugen.

Ein Ereignis muss nicht immer die gesamte Welt verändern. Seine Folgen sollen jedoch in dem Bereich sichtbar sein, in dem es fachlich relevant ist.

Beispiele:
- Ein Mangel an Nahrung kann Versorgung, Gesundheit, Zufriedenheit oder Migration beeinflussen.
- Eine Veränderung der Tierpopulation kann Ressourcenverfügbarkeit und Verhalten anderer Arten beeinflussen.
- Eine Questentscheidung kann Beziehungen, Zugang, Fraktionszustände oder spätere Ereignisse verändern.
- Ein beschädigtes Gebäude kann seine Funktion verlieren und Reparatur oder Ersatz erfordern.

Auswirkungen dürfen abgestuft simuliert werden, müssen aber konsistent bleiben. Vereinfachungen sind zulässig, wenn ihre Grenzen bekannt sind und keine widersprüchlichen Weltzustände erzeugen.

### 2.2.6 Spielerautonomie

Die Geschichte darf den Spieler führen, aber seine Entscheidungen nicht vollständig entwerten.

Vaelith kann beraten, widersprechen, provozieren, warnen oder Informationen zurückhalten, darf jedoch nicht die Entscheidungen des Spielers ersetzen. Seine Persönlichkeit und seine Sichtweisen sollen erkennbar sein, ohne dass er dadurch zum allwissenden Erzähler wird.

Spielerautonomie bedeutet nicht, dass jede Handlung möglich oder folgenlos sein muss. Grenzen können aus Weltlogik, Fähigkeiten, Ressourcen, Beziehungen und Ereignissen entstehen. Sie müssen nachvollziehbar sein.

### 2.2.7 Keine künstliche Komplexität

Komplexität ist nur dann sinnvoll, wenn sie ein relevantes Spielerlebnis, eine glaubwürdige Welt oder einen notwendigen Produktionsablauf unterstützt.

- Systeme sollen verständliche Zuständigkeiten besitzen.
- Wiederkehrende Regeln sollen konsistent funktionieren.
- Automatisierung und Delegation sollen dort möglich sein, wo sie zum Spielverlauf passen.
- Detaillierte Simulation muss nicht jederzeit vollständig sichtbar oder steuerbar sein.
- Zusätzliche Optionen dürfen keine bloße Verwaltungslast erzeugen.

Vereinfachung darf allerdings nicht dazu führen, dass ein Kernsystem nur oberflächlich vorhanden ist.

---

## 2.3 Erhalt bestehender Projektinhalte

### 2.3.1 Grundsatz

Vor jeder Konsolidierung, Umstrukturierung oder Migration vorhandener Inhalte ist ein Inventar der Originalquellen anzulegen.

Zu erhalten sind – soweit in den Quellen vorhanden:
- Namen und Begriffe;
- Definitionen und Beschreibungen;
- JSON-Strukturen und Schemas;
- IDs und Referenzen;
- Kategorien und Attribute;
- Kataloge und Listen;
- Questlogik und Bedingungen;
- wirtschaftliche Regeln und Produktionsketten;
- Item- und Ausrüstungsdaten;
- Kreaturen-, Tier- und NPC-Definitionen;
- Monetarisierungsideen;
- dokumentierte Entscheidungen und Begründungen.

Ein Inhalt darf nicht allein deshalb entfallen, weil seine bisherige technische Umsetzung nicht zur neuen Unity-Architektur passt.

### 2.3.2 Zulässige Anpassungen

Technische Anpassungen an Unity, 3D, neue Datenmodelle oder neue Produktionsabläufe sind zulässig und können notwendig sein.

Jede relevante Änderung muss nachvollziehbar dokumentiert werden:
- Quelle und ursprüngliche Bezeichnung bzw. Struktur;
- Änderungstyp: umbenennen, verschieben, ergänzen, bearbeiten, ersetzen, aufteilen oder löschen;
- Begründung und technische bzw. spielerische Auswirkung;
- Zielstruktur und Migrationsregel;
- Umgang mit bestehenden IDs und Referenzen;
- Auswirkungen auf abhängige Dokumente und Systeme.

### 2.3.3 Quellenlücken

Nicht vorliegende Quelldaten werden als Quellenlücke markiert. Sie werden nicht durch plausibel klingende Vermutungen ersetzt.

Wenn eine frühere Idee nur in einer Zusammenfassung oder einer nicht mehr zugänglichen Unterhaltung erwähnt wird, darf sie als Hinweis auf einen Prüfbedarf dienen. Sie ersetzt nicht die Originalquelle, wenn konkrete Details, Regeln oder Daten übernommen werden sollen.

### 2.3.4 Eigenständigkeit von Vaelith

Vaelith bleibt ein eigenständiges Projekt.

ASHFALL-spezifische Inhalte werden nicht übernommen. Das betrifft insbesondere projektspezifischen Code, Assets, Strukturen, Algorithmen, Daten, Szenen, Shader, Modelle und sonstige Implementierungsbestandteile.

Allgemeine technische Standards, frei verfügbare Werkzeuge und übliche Architekturprinzipien sind davon nicht betroffen, sofern ihre Nutzung rechtlich und technisch zulässig ist.

---

## 2.4 Keine stillen Festlegungen

Zahlen und technische Parameter, die noch nicht ausdrücklich entschieden sind, bleiben konfigurierbar oder als offen markiert.

Beispiele:
- Weltmaßstab und Kartenauflösung;
- Region- und Chunkgrößen;
- Anzahl und Verteilung der Biome;
- Schwierigkeitsstufen;
- Simulationsintervalle und Detailstufen;
- Zielplattformen und Mindesthardware;
- Spielerzahl und Netzwerkmodell;
- Performancebudgets;
- Download- und Installationsgröße;
- Releaseumfang und Zeitplanung.

Illustrative Beispielwerte dürfen zur Erklärung verwendet werden. Sie müssen klar als Beispiele gekennzeichnet sein und dürfen nicht unbemerkt in verbindliche Spezifikationen übergehen.

Eine technische Empfehlung ist ebenfalls noch keine Projektentscheidung. Empfehlungen müssen mit Begründung, Auswirkungen und offenen Risiken vorgelegt werden.

---

## 2.5 Wissenschafts-Fantasy-Arbeitsrichtung

Die aktuell erwogene Science-Fantasy-Ausrichtung soll vielfältige Kulturen und Entwicklungsstände ermöglichen.

Futuristische Städte, technologisch fortgeschrittene Gesellschaften, traditionell organisierte Gemeinschaften, uralte Ruinen und magische Orte können koexistieren, wenn Weltgeschichte und Kultur dies plausibel erklären.

Das Setting darf nicht zu einem reinen Science-Fiction-Shooter werden. Magie, Mystik, Abenteuer und fantastische Kreaturen bleiben wesentliche Bestandteile der aktuellen Spielvision.

Diese Ausrichtung ist eine Arbeitsrichtung und wird erst nach gemeinsamer Bestätigung als endgültige Setting-Entscheidung geführt.

---

## 2.6 Trennung von Identität, Gefahr und Fortschritt

Biom, Gefahr, Schwierigkeit und Spielerfortschritt sind eigenständige Dimensionen. Sie dürfen nicht zu einer einzigen Gebiets- oder Levelklassifizierung zusammengezogen werden.

- **Biom:** Beschreibt ökologische und geografische Eigenschaften eines Gebietes.
- **Gefahr:** Beschreibt Risiken durch Kreaturen, Fraktionen, Umweltbedingungen und Ereignisse.
- **Schwierigkeit:** Beschreibt die erwartete Herausforderung bzw. die dafür relevanten Skalierungsregeln.
- **Spielerfortschritt:** Beschreibt Fähigkeiten, Questzustände und Freischaltungen des Spielers.
- **Zugänglichkeit:** Beschreibt, ob und unter welchen Bedingungen ein Gebiet erreichbar oder betretbar ist.

Ein Wald ist daher nicht automatisch gefährlich oder hochstufig. Ein friedliches Gebiet kann gefährliche Ereignisse erleben; ein gefährliches Gebiet kann verschiedene Biome enthalten.

Diese Trennung muss sich in Weltgenerierung, Editor-Oberflächen, Questbedingungen und Laufzeitlogik widerspiegeln.

---

## 2.7 Weltgenerierung und dauerhafte Weltzustände

### 2.7.1 Geografische Stabilität

Die geografische Grundstruktur der Welt wird prozedural erzeugt. Bereits festgelegte Koordinaten, Regions-IDs und Generatorstände müssen langfristig nachvollziehbar bleiben.

Spätere Generatoränderungen dürfen nicht unbeabsichtigt:
- Flüsse verlegen;
- Gebirge oder Küstenlinien verschieben;
- Biomgrenzen verändern;
- Siedlungen oder Straßen versetzen;
- gespeicherte Spielerbauten überschreiben;
- Quest- und POI-Referenzen ungültig machen.

### 2.7.2 Geplante und entwickelte Regionen

Die geografische Gesamtwelt kann von Anfang an geplant sein, ohne alle Regionen sofort vollständig zu generieren oder auszuliefern.

Geplante Regionen können zunächst mit minimalen Metadaten und Platzhaltern geführt werden. Vollständige 3D-Umgebung, Inhalte und Simulation werden erst im vorgesehenen Entwicklungs- oder Freigabeprozess erzeugt.

### 2.7.3 Abgestufte Simulation

Nicht jeder Teil der Welt muss jederzeit mit derselben Detailtiefe simuliert werden.

Die Simulation darf nach Relevanz, Entfernung, Aktivität und fachlichem Bedarf abgestuft werden. Die Ergebnisse müssen jedoch mit den Regeln der detaillierten Simulation vereinbar bleiben.

Die konkreten Stufen, Intervalle und Übergangsregeln werden im Simulationskonzept festgelegt. Es werden hier keine Zahlen vorweggenommen.

---

## 2.8 Spielerführung, Freischaltung und Progression

### 2.8.1 Freischaltungen mit Bedeutung

Größere Systeme sollen im vorgesehenen Zusammenhang mit Geschichte, Quests und Spielerentwicklung erschlossen werden.

Insbesondere Schloss- und Siedlungsbau werden nicht pauschal allein durch Charakterstufen freigeschaltet. Die Welt und die Handlung sollen erklären, warum der Spieler Zugang zu neuen Möglichkeiten erhält.

### 2.8.2 Verständliche Einführung

Komplexe Systeme müssen in einem sinnvollen Zeitpunkt eingeführt werden. Die Spielerführung soll die notwendigen Zusammenhänge vermitteln, ohne die Entdeckung und Eigeninitiative zu ersticken.

### 2.8.3 Vollständiges Potenzial und tatsächliche Beherrschung

Bei Fähigkeiten und Magie ist zwischen dem grundsätzlichen Zugang zu einem Potenzial und dessen sicherer, kontrollierter Anwendung zu unterscheiden.

Die Geschichte sieht vor, dass der Spieler nach der Befreiung Vaeliths Zugang zu seinem vollständigen magischen Potenzial erhält. Die Beherrschung und Kontrolle entwickeln sich anschließend weiter.

Diese Unterscheidung darf nicht durch eine künstliche Behauptung ersetzt werden, Vaelith selbst sei zu schwach oder könne seine Macht nicht einsetzen. Seine Zurückhaltung ist eine bewusste Entscheidung.

---

## 2.9 NPCs, Tiere und Kreaturen

### 2.9.1 Individuen statt austauschbarer Kulisse

Wichtige NPCs, Tiere und Kreaturen sollen eine erkennbare Identität besitzen. Welche Eigenschaften im Detail simuliert werden, hängt von Rolle, Relevanz und Entfernung ab.

### 2.9.2 Gemeinsame Grundlagen, unterschiedliche Rollen

Für Tiere und Kreaturen ist ein gemeinsames Grundlagenframework vorgesehen. Unterschiedliche Rollen wie Wildtier, Haustier, Nutztier, Reittier, Begleiter oder Hoftier sollen nicht zu vollständig getrennten und inkompatiblen Systemen führen.

Die jeweilige Rolle ergibt sich aus den fachlich passenden Eigenschaften, Fähigkeiten, Ausbildung, Zuweisung und Situation.

### 2.9.3 Glaubwürdige Bedürfnisse und Grenzen

Bedürfnisse, Gesundheit, Verhalten, Alter, Beziehungen und Lebenszyklus sollen sich gegenseitig beeinflussen, soweit dies für die jeweilige Rolle relevant ist.

Ein Lebewesen darf nicht gleichzeitig als unerschöpfliche Ressource und als glaubwürdiges Individuum behandelt werden. Nutzung, Pflege und Zucht müssen in einem nachvollziehbaren Verhältnis stehen.

---

## 2.10 Wirtschaft, Ressourcen und Produktion

### 2.10.1 Nachvollziehbare Produktionsketten

Ressourcen und Produkte sollen in nachvollziehbaren Zusammenhängen entstehen, verarbeitet, gelagert, transportiert und verbraucht werden.

### 2.10.2 Abhängigkeiten sichtbar machen

Produktion kann von Rohstoffen, Arbeitskraft, Fähigkeiten, Infrastruktur, Versorgung, Sicherheit und besonderen Eigenschaften eines Ortes abhängen.

Diese Abhängigkeiten müssen für Spieler und Entwickler in geeigneter Form erkennbar und prüfbar sein.

### 2.10.3 Keine bedeutungslosen Ressourcen

Eine Ressource sollte einen klaren Zweck, eine Funktion oder einen nachvollziehbaren Platz in einem Systemverbund besitzen. Reine Sammelobjekte ohne erkennbaren Nutzen sind bewusst zu begründen.

Die konkrete Wirtschaftsbalance, Preisbildung, Verbrauchsrate und Produktionsformeln gehören in die Wirtschaftsspezifikation und dürfen nicht aus diesem Grundsatz abgeleitet oder erfunden werden.

---

## 2.11 Editoren und Produktionswerkzeuge

### 2.11.1 Fachlich vollständige Arbeitsabläufe

Ein Editor muss den vollständigen vorgesehenen fachlichen Ablauf unterstützen. Dazu gehören je nach Werkzeug Erstellung, Bearbeitung, Vorschau, Validierung, Speicherung, Referenzprüfung, Import/Export und Integration.

### 2.11.2 Gemeinsame Datenbasis

Editoren dürfen keine voneinander unabhängigen Wahrheiten über dieselben Entitäten pflegen. Ein NPC, Gebäude, Item oder Ort muss über stabile Identität und nachvollziehbare Referenzen systemübergreifend verwendet werden können.

### 2.11.3 Fehler früh erkennen

Fehlerhafte Daten und ungültige Referenzen sollen möglichst bereits während der Bearbeitung erkannt werden, nicht erst beim Laden einer Spielszene oder während einer Quest.

### 2.11.4 Bedienbarkeit für reale Produktionsaufgaben

Die Qualität eines Editors wird an realen Arbeitsabläufen gemessen. Eine Oberfläche ist nicht ausreichend, wenn wichtige Aufgaben nur durch manuelle Dateibearbeitung, externe Skripte oder nicht dokumentierte Workarounds erledigt werden können.

---

## 2.12 Modding und Erweiterbarkeit

Modding wird von Beginn an architektonisch berücksichtigt, ist aber keine Voraussetzung für das Grundspiel.

Die vorgesehene Grundlage ist BepInEx mit einer darauf aufbauenden offiziellen Vaelith Mod API in C#.

Dabei gelten folgende Leitlinien:
- Keine zweite Mod-Loader-Infrastruktur parallel entwickeln, wenn BepInEx die benötigte Aufgabe erfüllt.
- Datenbasierte Mods und ausführbare Code-Mods klar unterscheiden.
- Öffentliche Schnittstellen, Events und Erweiterungspunkte dokumentieren und versionieren.
- Kompatibilität, Abhängigkeiten und Konflikte nachvollziehbar behandeln.
- Keine Sandbox-Sicherheit für beliebige C#-Plugins behaupten, wenn diese im Prozess mit weitreichenden Rechten laufen.
- Laufzeit- und Plattformkompatibilität früh prüfen; insbesondere darf nicht ungeprüft angenommen werden, dass alle Modding-Funktionen mit jedem Scripting Backend und jeder Zielplattform funktionieren.

Die genaue API und die unterstützten Erweiterungspunkte werden im Modding-Konzept definiert.

---

## 2.13 Technische Entscheidungen und Architektur

### 2.13.1 Spielanforderungen vor Technologiepräferenz

Technologien werden anhand der tatsächlichen Anforderungen von Vaelith ausgewählt. Bekanntheit oder persönliche Vorliebe allein reichen nicht als Begründung.

### 2.13.2 Stabilität und Kompatibilität prüfen

Vor Projektbeginn und bei wesentlichen Technologieentscheidungen sind aktuelle stabile Versionen, Paketkompatibilität, Renderpipeline, Plattformanforderungen und relevante Laufzeitbedingungen zu prüfen.

### 2.13.3 Keine ungeprüften Architekturversprechen

Eine Architekturentscheidung muss ihre Annahmen, Vorteile, Nachteile, Abhängigkeiten und Risiken offenlegen.

Insbesondere bei sehr großen Welten, persistenter Simulation, Modding und Streaming sind Prototypen oder technische Nachweise vorzusehen, bevor weitreichende Festlegungen getroffen werden.

### 2.13.4 Wartbarkeit und Diagnose

Systeme müssen so strukturiert sein, dass Fehler lokalisiert, Zustände untersucht und Datenprobleme nachvollzogen werden können.

Entwicklungswerkzeuge wie Debug-Ansichten, Inspektoren, Generator-Diagnostik, Simulationssteuerung und Referenzprüfungen sind als Teil der Produktionsqualität zu betrachten.

---

## 2.14 Entscheidungen und Prioritäten

Bei Konflikten ist nicht automatisch die technisch bequemste Lösung richtig.

Die Bewertung muss mindestens berücksichtigen:
- Übereinstimmung mit der Spielvision;
- Erhalt vorhandener Projektinhalte;
- Auswirkungen auf das Spielerlebnis;
- Konsistenz mit anderen Systemen;
- technische Tragfähigkeit;
- Performance und Skalierbarkeit;
- Wartbarkeit und Erweiterbarkeit;
- Produktionsaufwand und Risiken.

Claude bzw. ein beauftragter Entwicklungsagent soll Lücken, Konflikte und Risiken sichtbar machen, priorisierte Empfehlungen mit Begründung aussprechen und innerhalb des genehmigten Umfangs arbeiten.

Grundlegende Richtungsänderungen, Streichungen wichtiger Funktionen und Änderungen an bestätigten Projektentscheidungen bleiben Sache der Projektleitung.

### Keine stillen Änderungen

Ein Agent darf nicht:
- bestehende Inhalte ohne Inventar und Begründung entfernen;
- offene Entscheidungen eigenmächtig als beschlossen markieren;
- Anforderungen durch eine einfachere, aber fachlich andere Funktion ersetzen;
- Tests als erfolgreich ausgeben, die nicht ausgeführt wurden;
- Abweichungen von freigegebenen Arbeitspaketen verschweigen.

---

## 2.15 Qualitätssicherung und Nachweisbarkeit

Qualität wird nicht allein durch eine erfolgreiche Kompilierung oder eine sichtbare Oberfläche nachgewiesen.

Tests müssen dem Risiko und Zweck des jeweiligen Systems entsprechen. Dazu können gehören:
- Daten- und Schema-Validierung;
- Unit- und Integrationstests;
- Generierungs- und Reproduzierbarkeitstests;
- Speicher- und Ladezyklen;
- Referenz- und Abhängigkeitstests;
- Laufzeit- und Performanceprüfungen;
- Tests realer Arbeitsabläufe in Editoren;
- Tests aus Sicht des Spielers.

Jede Übergabe eines Arbeitspakets muss tatsächliche Änderungen, betroffene Pfade, ausgeführte Tests, Ergebnisse, bekannte Einschränkungen und offene Probleme nennen.

Nicht ausgeführte Tests werden als nicht ausgeführt gekennzeichnet. Vermutete Ergebnisse sind keine Testergebnisse.

---

## 2.16 Umgang mit Zielkonflikten

Wenn zwei Prinzipien oder Anforderungen miteinander kollidieren, wird der Konflikt sichtbar dokumentiert.

Der Lösungsweg:
1. Betroffene Anforderungen und Quellen benennen.
2. Den tatsächlichen Konflikt beschreiben.
3. Auswirkungen auf Spielvision, Datenbestand, Systeme und technische Umsetzung ermitteln.
4. Realistische Lösungsoptionen mit Vor- und Nachteilen darstellen.
5. Eine begründete Empfehlung abgeben.
6. Erforderliche Projektentscheidung einholen.
7. Entscheidung und Auswirkungen im Entscheidungsregister festhalten.
8. Betroffene Dokumente aktualisieren.

Ein Konflikt darf nicht dadurch verschwinden, dass eine Seite stillschweigend weggelassen wird.

---

## 2.17 Offene Präzisierungen

Die folgenden Punkte sind noch nicht vollständig spezifiziert:

| ID | Thema | Benötigte Präzisierung |
|---|---|---|
| PRINCIPLE-001 | Simulationsstufen | Welche Stufen, Übergänge und Konsistenzregeln gelten? |
| PRINCIPLE-002 | Datenversionierung | Wie werden Schema-, Inhalts- und Savegame-Versionen unterschieden? |
| PRINCIPLE-003 | Editor-Abnahme | Welche Mindestkriterien gelten je Editor-Typ? |
| PRINCIPLE-004 | Teststandard | Welche Testarten und Nachweise sind pro Arbeitspaket verpflichtend? |
| PRINCIPLE-005 | Modding-Vertrauen | Welche Vertrauens-, Warnungs- und Berechtigungsmodelle werden für Code-Mods verwendet? |
| PRINCIPLE-006 | Plattformkompatibilität | Welche Plattformen und Laufzeitmodelle müssen berücksichtigt werden? |
| PRINCIPLE-007 | Zugänglichkeit | Welche Accessibility- und Bedienstandards sollen verbindlich gelten? |

Diese offenen Punkte werden in den jeweiligen Fachkonzepten vertieft und bei Bedarf im Entscheidungsregister geführt.

---

## 2.18 Abhängige Dokumente

- `01-project-overview.md` — übergeordnete Spielvision.
- `03-world-and-lore.md` — Welt, Kosmologie, Lore und Geschichte.
- `04-player-progression-and-magic.md` — Spielerentwicklung und Magie.
- `05-gameplay-systems.md` — Gameplay-Systeme und Spielmechaniken.
- `06-living-world-simulation.md` — Simulation, NPCs und Ökologie.
- `07-world-generation.md` — prozedurale Weltgenerierung.
- `08-editor-suite.md` — Editor- und Produktionswerkzeuge.
- `09-data-architecture.md` — Datenmodelle, IDs, Referenzen und Persistenz.
- `10-unity-architecture.md` — Unity-Architektur und technische Grundlagen.
- `11-modding-api.md` — Modding und Erweiterbarkeit.
- `13-economy-items-crafting.md` — Wirtschaft, Items und Herstellung.
- `16-mdp-development-process.md` — Modular Development Pipeline.
- `18-qa-security-performance.md` — Qualitätssicherung, Sicherheit und Performance.
- `19-agent-operating-rules.md` — Regeln für Entwicklungsagenten.
- `20-decisions-and-open-questions.md` — Entscheidungen und offene Fragen.

---

## 2.19 Änderungsprotokoll

| Version | Datum | Änderung |
|---|---|---|
| 0.1 | 2026-11-17 | Bestehende Leitplanken strukturiert und erweitert; Datenkontinuität, Weltpersistenz, Progression, Systemintegration, Modding, technische Entscheidungen, Qualitätssicherung und Konfliktbehandlung präzisiert. |

**Nächster Schritt:** Gemeinsame Prüfung der Designprinzipien. Anschließend wird die Welt- und Lore-Grundlage in `03-world-and-lore.md` ausgearbeitet.


## 2.20 Schrittweise Entwicklung und kontinuierliche Prüfbarkeit

Vaelith wird in überschaubaren, nachvollziehbaren und regelmäßig überprüfbaren Schritten entwickelt. Es ist ausdrücklich zu vermeiden, über lange Zeit große Funktionsbereiche im Hintergrund aufzubauen, ohne der Projektleitung zwischendurch tatsächlich prüfbare Ergebnisse bereitzustellen.

Daraus folgen verbindliche Regeln:

- **Kleine, abgrenzbare Liefergegenstände:** Große Systeme werden in fachlich sinnvolle Arbeitspakete und überprüfbare Zwischenschritte zerlegt.
- **Früh nutzbare Ergebnisse:** Jeder Schritt soll so früh wie sinnvoll einen lauffähigen, bedienbaren oder anderweitig praktisch prüfbaren Zwischenstand liefern.
- **Funktionale Prüfbarkeit:** Die Projektleitung muss betroffene Funktionen selbst ausprobieren können. Dazu gehören geeignete Testdaten, nachvollziehbare Start-/Testwege und erforderliche Entwicklungswerkzeuge.
- **Visuelle Prüfbarkeit:** Sichtbare Ergebnisse wie Spielbereiche, Charaktere, Gebäude, Oberflächen und Editoren müssen frühzeitig in einer geeigneten Vorschau oder in einer lauffähigen Anwendung betrachtet werden können.
- **Regelmäßige Zwischenabnahmen:** Nach jedem sinnvoll abgeschlossenen Schritt werden Ergebnis, Umfang, bekannte Einschränkungen und Prüfmöglichkeiten vorgestellt.
- **Feedback vor Aufbau weiterer Komplexität:** Rückmeldungen und notwendige Korrekturen werden grundsätzlich aufgenommen, bevor der nächste reguläre Schritt auf dem Ergebnis aufbaut.
- **Keine Sammelübergabe:** Ein umfangreicher Bereich darf nicht bis zu einem vermeintlichen Gesamtabschluss verborgen bleiben, wenn vorher bereits sinnvolle Teilstände prüfbar wären.
- **Abhängigkeiten bewusst behandeln:** Falls ein Schritt noch nicht eigenständig ausführbar ist, muss der Agent erklären, welche konkrete Abhängigkeit fehlt und welcher kleinste sinnvolle Prüfstand trotzdem bereitgestellt werden kann.

Ein Zwischenstand muss nicht bereits releasefertig sein. Er muss aber ehrlich als Prototyp, Vorschau, Teilfunktion oder abnahmefähiger Liefergegenstand gekennzeichnet werden. Nicht vorhandene Funktionen dürfen nicht durch Attrappen oder rein visuelle Platzhalter als fertig dargestellt werden.

Die Projektleitung soll jederzeit erkennen können, was bereits funktioniert, was nur demonstriert wird, was noch fehlt und worauf der nächste Schritt aufbaut. Die konkrete Taktung und Größe der Arbeitspakete richtet sich nach Risiko und fachlichem Zusammenhang; ein starres Zeitintervall wird nicht vorgegeben.
