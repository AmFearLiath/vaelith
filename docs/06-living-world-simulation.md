# 06 — Lebendige Welt und Simulation

## 6.1 Ziel

Die Welt soll glaubwürdig weiterexistieren, auch wenn der Spieler nicht in jedem Gebiet anwesend ist. NPCs, Siedlungen, Fraktionen, Tiere, Ressourcen und Ereignisse besitzen Zustände und Beziehungen. Die Simulation muss aber skalierbar sein und darf nicht für jedes entfernte Objekt dieselbe Detailtiefe wie in unmittelbarer Spielernähe berechnen.

## 6.2 Simulationsstufen nach Relevanz

Als Architekturprinzip wird eine abgestufte Simulation verwendet:
- **Vollsimulation:** Nähe zum Spieler, aktive Quests, wichtige Figuren, Kampf- oder Interaktionssituationen.
- **Reduzierte Simulation:** bekannte und erschlossene Regionen mit vereinfachten Zeit-, Bedürfnis-, Produktions- und Ereignisupdates.
- **Abstrakte Simulation:** entfernte, aktuell nicht relevante Regionen werden über aggregierte Zustände und Ereignisschritte fortgeschrieben.
- **Nicht entwickelte Regionen:** besitzen nur minimale geografische/planerische Metadaten. Es existieren dort noch keine vollständigen Terrain-, Gebäude-, NPC- oder Wirtschaftssimulationen.

Die konkreten Radien, Taktungen und Updatebudgets sind durch Profiling festzulegen.

## 6.3 NPC-Grundmodell

NPCs benötigen stabile Identität und Referenzen, Attribute, Erscheinungsbild, Ausrüstung, Persönlichkeit, Bedürfnisse, Tagesabläufe, Aufgaben/Berufe, Beziehungen, Zugehörigkeiten, Dialogzustände und Verhaltenslogik. Nicht jeder NPC muss alle Details besitzen. Bedeutung und Entfernung dürfen die Simulationskomplexität steuern.

NPCs sollen:
- Aufgaben und Arbeitsplätze zugewiesen bekommen;
- Wege und Tagesabläufe verfolgen;
- auf Bedürfnisse, Gefahren, Ereignisse und soziale Beziehungen reagieren;
- mit Wirtschaft, Quests und Weltzuständen verbunden sein;
- persistente Identität und relevante Erinnerungen/Zustände behalten.

## 6.4 Siedlungsleben

Siedlungen bestehen aus Bevölkerung, Wohnraum, Arbeitsplätzen, Infrastruktur, Versorgung, Ressourcen, sozialen Einrichtungen, Sicherheit und Beziehungen zu anderen Orten. Wachstum und Veränderung hängen von nachvollziehbaren Faktoren ab. Autonomes Wachstum darf nicht aus dem Nichts unbegrenzte Ressourcen oder Bevölkerung erzeugen.

## 6.5 Wirtschaftssimulation

Produktion, Lager, Verbrauch, Transport, Handel, Arbeitskraft, Nachfrage und Ereignisse werden in gemeinsamen Regeln abgebildet. Ein Dungeon, eine Farm, eine Werkstatt und ein Markt sind keine unabhängigen Minispiele, sondern Produzenten/Verbraucher innerhalb eines gemeinsamen Wirtschaftssystems.

## 6.6 Ökologie

Wildtiere, Beutetiere, Räuber, gefährliche Kreaturen, Vegetation und Ressourcen bilden regionale Zusammenhänge. Ökologische Simulation kann stark abstrahiert werden, muss aber konsistente Trends und Spielerwirkungen abbilden. Artenverhalten und Biomzugehörigkeit dürfen nicht allein von einem Schwierigkeitswert abgeleitet werden.

## 6.7 Zeit, Ereignisse und Persistenz

Es wird eine kontrollierte Weltzeit benötigt. Ereignisse können geplant, zufällig ausgelöst oder durch Bedingungen aktiviert werden. Zeitfortschritt und Simulationsergebnisse müssen gespeichert werden, damit ein Neustart keine widersprüchlichen Zustände erzeugt.

Für entfernte Regionen sind Zeitdifferenzen bzw. aggregierte Fortschreibung vorzusehen. Lang andauernde Produktions- oder Zuchtvorgänge dürfen beim Laden nicht unkontrolliert mehrfach ausgeführt werden.

## 6.8 Debugbarkeit

Entwickler benötigen Inspektoren für NPC-Zustände, Tagesabläufe, Pfadfindung, Bedürfniswerte, Beziehungen, Produktionsketten, Weltzeit und Eventhistorie. Eine Simulation muss sich reproduzierbar anhalten, beschleunigen, fortsetzen und mit Testwelten untersuchen lassen.

## 6.9 Simulationsobjekte, Zuständigkeit und Zustandswahrheit

Jedes simulierte Objekt besitzt eine eindeutige Identität und einen klaren Zustandsverantwortlichen. NPC, Tier, Gebäude, Lager, Produktionsstätte, Fraktion und Region dürfen denselben Sachverhalt nicht unabhängig voneinander speichern und verändern.

Es ist zwischen folgenden Ebenen zu unterscheiden:
- **Definition:** unveränderliche oder versionierte Vorlage mit Regeln und Ausgangswerten;
- **Instanz:** konkretes Objekt in einer Welt oder einem Spielstand;
- **Zustand:** veränderliche Werte wie Gesundheit, Vorrat, Beziehung, Aufgabe oder Besitz;
- **Ereignis:** protokollierte Ursache einer Zustandsänderung;
- **abgeleitete Ansicht:** berechnete Darstellung, die aus kanonischen Zuständen erzeugt wird.

Die Simulation darf keine zweite, abweichende Wahrheit neben Gameplay, Quest-System, Wirtschaft oder Persistenz erzeugen. Dokument 09 definiert Identität, Referenzen und Speicherverantwortung; dieses Dokument beschreibt, wie diese Daten fortgeschrieben werden.

## 6.10 NPC-Bedürfnisse und Prioritäten

Bedürfnisse sollen Verhalten beeinflussen, ohne jeden NPC zu einer unüberschaubaren Sammlung unabhängiger Zahlen zu machen. Zu prüfende Bedürfnisgruppen sind Versorgung, Sicherheit, Erholung, soziale Kontakte, Zugehörigkeit, Beschäftigung und persönliche Ziele. Welche davon tatsächlich als eigene Werte geführt werden, ist noch festzulegen.

Ein NPC muss aus seiner Situation heraus nachvollziehbar handeln:
- verfügbare Ressourcen und Wege berücksichtigen;
- dringende Bedürfnisse gegenüber optionalen Tätigkeiten priorisieren;
- Arbeitsaufträge und persönliche Ziele gegeneinander abwägen;
- auf Gefahren, Ausfälle, Konflikte und Veränderungen reagieren;
- bei unerfüllbaren Aufgaben einen definierten Alternativzustand erreichen.

Prioritäten müssen konfigurierbar und debugbar sein. Eine Routine darf nicht dauerhaft blockieren, wenn ihr Ziel unerreichbar, zerstört, gesperrt oder nicht mehr relevant ist. Abbruch, Neuplanung und Eskalation sind explizite Verhaltensfälle.

## 6.11 Tagesabläufe, Aufgaben und Arbeitsplätze

Tagesabläufe sind keine starren Animationslisten. Sie beschreiben zeitliche Präferenzen, Aufgaben, Orte und Bedingungen. Ein NPC kann von seiner Routine abweichen, wenn Gefahr, Krankheit, Questereignisse, Versorgungsausfälle, soziale Verpflichtungen oder andere relevante Zustände dies erfordern.

Arbeitsplätze und Aufgaben benötigen:
- definierte Anforderungen und Rollenkompatibilität;
- erreichbare Arbeitsorte und benötigte Infrastruktur;
- erforderliche Werkzeuge, Materialien oder Versorgung;
- Arbeitszeit, Pausen und Unterbrechungsregeln;
- Ergebniszustände und Rückmeldung an das Wirtschaftssystem.

Ein Arbeitsplatz darf nicht mehrere NPCs mit voller Produktivität beschäftigen, wenn die Kapazität dies nicht erlaubt. Umgekehrt müssen Ausfälle durch Krankheit, Abwesenheit, Verletzung oder Gefahr in Produktions- und Versorgungszuständen sichtbar werden.

## 6.12 Beziehungen, Gruppen und Fraktionen

Soziale Beziehungen und Zugehörigkeiten sollen Verhalten und Weltzustände beeinflussen. Mögliche Beziehungen umfassen persönliche Bindungen, Familie, Freundschaft, Rivalität, Vertrauen, Feindschaft, berufliche Zusammenarbeit und Abhängigkeiten. Fraktionen können politische, kulturelle, wirtschaftliche, religiöse oder andere gemeinsam definierte Interessen vertreten; konkrete Kategorien bleiben Teil der Welt- und Lore-Spezifikation.

Die Simulation muss unterscheiden zwischen:
- individueller Beziehung zweier Figuren;
- Zugehörigkeit einer Figur zu Gruppe oder Fraktion;
- Beziehungen zwischen Gruppen und Fraktionen;
- öffentlichem Ruf bzw. regionaler Wahrnehmung;
- temporären Zuständen wie Waffenstillstand, Fehde oder Bündnis.

Änderungen müssen aus nachvollziehbaren Ereignissen oder Entscheidungen hervorgehen. Beziehungen dürfen nicht allein durch einen globalen Rufwert ersetzt werden. Welche Details dauerhaft gespeichert und welche bei Bedarf abgeleitet werden, ist anhand von Umfang und Performance zu bestimmen.

## 6.13 Erinnerungen und Reaktionen auf den Spieler

Wichtige NPCs und Systeme sollen relevante Handlungen des Spielers wiedererkennen können. Eine Erinnerung muss nicht jede einzelne Aktion dauerhaft speichern. Sie soll bedeutsame Ereignisse, deren betroffene Personen/Orte und daraus resultierende Zustände erfassen.

Beispiele für relevante Ereignisse:
- Hilfe, Verrat, Gewalt oder Schutz;
- Handel, Versorgung und wirtschaftliche Unterstützung;
- Befreiung, Besetzung oder Zerstörung eines Ortes;
- Questentscheidungen und deren sichtbare Folgen;
- wiederholte Zusammenarbeit oder Konflikte.

Reaktionen müssen zum Kenntnisstand der Figur passen. Ein NPC darf nicht auf Ereignisse reagieren, von denen er weder selbst betroffen war noch glaubwürdig erfahren haben kann. Informationswege wie Beobachtung, Erzählung, Nachrichten oder Fraktionskommunikation sind bei Bedarf zu modellieren.

## 6.14 Siedlungsentwicklung und Bevölkerung

Bevölkerungsentwicklung muss an Kapazitäten und Lebensbedingungen gebunden sein. Wohnraum, Nahrung, Wasser/Versorgung, Sicherheit, Arbeitsplätze, Infrastruktur, Gesundheit und äußere Einflüsse können Wachstum, Abwanderung oder Verluste beeinflussen. Die konkrete Gewichtung ist offen.

Siedlungen sollen erkennbare Entwicklungszustände besitzen, ohne dass diese zwingend als starre Levelleiter umgesetzt werden. Veränderungen können beispielsweise entstehen durch:
- neue oder verlorene Arbeitsplätze;
- bessere oder schlechtere Versorgung;
- neue Gebäude und Infrastruktur;
- Handel und Transportverbindungen;
- Konflikte, Gefahren und politische Veränderungen;
- saisonale Bedingungen und regionale Ressourcen;
- Entscheidungen des Spielers und abgeschlossene Quests.

Autonomes Wachstum muss auf realen oder abstrahiert nachvollziehbaren Inputs beruhen. Bevölkerungszuwachs erzeugt zugleich zusätzlichen Bedarf und darf nicht als kostenloser Produktionsmultiplikator dienen.

## 6.15 Wirtschaftliche Rückkopplung und Lieferketten

Die Wirtschaftssimulation verarbeitet Erzeugung, Verbrauch, Lagerung, Transport, Handel, Arbeitskraft und Nachfrage nach gemeinsamen Regeln. Produktionsstätten benötigen verfügbare Inputs, geeignete Arbeitskräfte und funktionierende Zugänge. Ergebnisse müssen an Lager, Auftraggeber oder nachgelagerte Produktionsschritte übergeben werden.

Die Simulation muss insbesondere erkennen:
- fehlende Rohstoffe oder Zwischenprodukte;
- volle oder nicht erreichbare Lager;
- fehlende Arbeitskräfte oder Werkzeuge;
- blockierte Wege und unterbrochene Handelsverbindungen;
- Überproduktion, Knappheit und Verderb, sofern entsprechende Regeln beschlossen werden;
- Auswirkungen von Ereignissen, Saison und regionaler Sicherheit.

Produktionsketten dürfen keine Ressourcen erzeugen, nur weil ein Zeitintervall vergangen ist. Offline- und Fernsimulation müssen dieselben fachlichen Regeln verwenden wie die aktive Spielwelt, gegebenenfalls mit aggregierter Berechnung.

## 6.16 Ökologische Dynamik und Populationsgrenzen

Ökosysteme sollen regional nachvollziehbar funktionieren. Tierpopulationen, Nahrung, Lebensraum, Räuber-Beute-Beziehungen, Konkurrenz, Krankheit, Jagd und menschliche Eingriffe können Bestände beeinflussen. Nicht jede Interaktion muss auf Individuenebene simuliert werden.

Für jede relevante Art bzw. Population sind geeignete Grenzen und Bedingungen zu definieren, beispielsweise Lebensraum, Nahrung, Fortpflanzung, Sterblichkeit und Wanderung. Konkrete Formeln und Parameter sind offen und müssen mit Testregionen kalibriert werden.

Die Ökologie darf weder unbegrenzt wachsen noch ohne Ursache kollabieren. Seltene oder questrelevante Arten benötigen Schutzregeln, die ihre Bedeutung erhalten, ohne die Weltreaktion unglaubwürdig zu machen. Ob eine Art geschützt, domestizierbar, gefährlich oder ressourcenrelevant ist, darf nicht pauschal aus ihrer Biomzugehörigkeit abgeleitet werden.

## 6.17 Ereignisse, Ursachen und Kettenreaktionen

Welt-Ereignisse können zeitgesteuert, zufällig innerhalb definierter Regeln oder durch Zustandsbedingungen ausgelöst werden. Sie können lokal, regional oder weltübergreifend wirken. Ereignisse sollen Ursache, betroffene Objekte, Zeitpunkt, Auswirkungen und Bearbeitungsstatus nachvollziehbar erfassen.

Beispiele für Ereigniskategorien:
- Wetter- und Umweltveränderungen;
- Versorgungsengpässe und Produktionsausfälle;
- Krankheiten, Tierwanderungen und Populationsveränderungen;
- Überfälle, Konflikte, politische Entwicklungen und Katastrophen;
- Feste, Märkte und saisonale Aktivitäten;
- Quest- und storyrelevante Ereignisse.

Ereignisse dürfen nicht unkontrolliert rekursiv neue Ereignisse erzeugen. Kettenreaktionen benötigen Begrenzungen, Abklingregeln oder andere Mechanismen, damit ein einzelner Auslöser nicht zu einer endlosen Ereignisschleife führt. Zufallsereignisse müssen für Debugging und Reproduktion nachvollziehbar sein.

## 6.18 Weltzeit, Offline-Fortschritt und Zeitdifferenzen

Weltzeit ist eine zentrale Referenz für Tagesabläufe, Produktion, Zucht, Bedürfnisse, Ereignisse, Wetter und saisonale Prozesse. Die Spielzeit muss von der realen Systemzeit getrennt sein. Pausieren, Beschleunigen und kontrolliertes Fortschreiten müssen eindeutige Auswirkungen besitzen.

Beim Laden eines Spielstands oder einer Region darf vergangene Spielzeit nur einmal verarbeitet werden. Die Fortschreibung muss:
- den zuletzt verarbeiteten Zeitstand speichern;
- bereits angewendete Ereignisse erkennen;
- lange Zeiträume in begrenzten, reproduzierbaren Schritten verarbeiten;
- abhängige Prozesse in konsistenter Reihenfolge ausführen;
- Überläufe und ungültige Zustände verhindern;
- bei Unterbrechung sicher fortsetzbar sein.

Ob und in welchem Umfang Weltzeit während eines vollständig geschlossenen Spiels weiterläuft, ist eine offene Produktentscheidung. Es darf keine unbeabsichtigte Echtzeitstrafe entstehen, solange dies nicht ausdrücklich beschlossen ist.

## 6.19 Simulationsbudget und Aktualisierungsplanung

Die Simulationsstufe bestimmt nicht nur Detailgrad, sondern auch Aktualisierungshäufigkeit und Berechnungskosten. Aufgaben sollen priorisiert und gebündelt werden, statt alle Objekte in jedem Frame zu aktualisieren.

Zu prüfen sind:
- ereignisgesteuerte Aktualisierung statt permanenter Polling-Schleifen;
- zeitlich gestaffelte Updates;
- räumliche und fachliche Gruppierung;
- Aggregation entfernter Populationen und Produktionsketten;
- Priorisierung aktiver Quests und spielrelevanter Akteure;
- kontrollierter Wechsel zwischen Simulationsstufen;
- Messung von CPU-, Speicher- und I/O-Kosten.

Konkrete Tickraten, Updateintervalle, Simulationsradien und Budgets werden nicht vor Profiling festgelegt. Ein Wechsel in eine höhere Detailstufe muss aus aggregierten Zuständen einen konsistenten aktiven Zustand herstellen; der Wechsel zurück darf keine Ergebnisse verlieren oder doppelt anwenden.

## 6.20 Determinismus und Reproduzierbarkeit

Simulationsergebnisse müssen für Debugging, Fehleranalyse und Tests ausreichend reproduzierbar sein. Zufallsentscheidungen sollen aus nachvollziehbaren Seed-/Zustandsquellen stammen und dürfen nicht unkontrolliert von Lade-Reihenfolge, Frame-Timing oder zufälliger Objektiteration abhängen.

Für relevante Simulationsschritte sollen protokollierbar sein:
- Ausgangszustand bzw. Zustandsversion;
- Simulationszeit und betroffener Bereich;
- verwendete Regeln und Versionen;
- Zufallsseed bzw. Ereignisursprung;
- resultierende Zustandsänderungen;
- Fehler oder verworfene Aktionen.

Vollständige deterministische Reproduktion über alle Plattformen wird nicht ohne technische Prüfung zugesagt. Ziel ist zunächst eine für Entwicklung und QA belastbare Nachvollziehbarkeit.

## 6.21 Übergänge zwischen Simulationsstufen

Wenn ein Gebiet oder Akteur in die Nähe des Spielers, in eine aktive Quest oder in eine andere höhere Relevanzstufe gelangt, muss der Übergang ohne sichtbaren Zustandsbruch erfolgen.

Dafür sind klare Regeln erforderlich:
- aggregierte Populationen bei Bedarf in konkrete Individuen überführen;
- abstrakte Produktionsstände in reale Lager-/Auftragszustände überführen;
- NPC-Aufgaben und Orte konsistent initialisieren;
- laufende Ereignisse und Zeitpläne übernehmen;
- bereits verarbeitete Zeiträume nicht erneut simulieren;
- nicht mehr relevante Details kontrolliert wieder abstrahieren.

Die Umwandlung muss nachvollziehbar und testbar sein. Sie darf weder künstlich zusätzliche Ressourcen erzeugen noch bereits gespeicherte Individuen, Gebäude oder Ereignisse duplizieren.

## 6.22 Debugging, Beobachtung und Testwelten

Neben den in 6.8 genannten Inspektoren benötigt die Entwicklung Werkzeuge, um Ursachen und Folgen über mehrere Systeme hinweg zu verfolgen.

Erforderliche Debugmöglichkeiten:
- Weltzeit pausieren, schrittweise fortschreiben und beschleunigen;
- Simulationsstufe einzelner Regionen und Akteure anzeigen/temporär überschreiben;
- NPC-Ziele, Bedürfnisse, Beziehungen und Entscheidungsgründe einsehen;
- Produktionsketten, Lagerbewegungen und Ressourcenflüsse verfolgen;
- Populationen, Geburten, Verluste und Wanderungen untersuchen;
- Ereignisse auslösen, zurücksetzen und ihre Folgen protokollieren;
- Simulationsläufe mit festem Seed wiederholen und vergleichen;
- Engpässe, Endlosschleifen, verwaiste Aufgaben und ungültige Zustände erkennen.

Temporäre Debug-Overrides dürfen nicht unbemerkt in reguläre Spielstände gelangen. Testwelten müssen reproduzierbar erstellt und von produktiven Spielständen getrennt werden können.

## 6.23 Zusammenspiel mit Quests und Spielerhandlungen

Quests und Spielerhandlungen sind Auslöser und Folgen der Simulation, nicht getrennte Skriptwelten. Eine Handlung kann lokale und verzögerte Auswirkungen auf NPCs, Wirtschaft, Ökologie, Fraktionen und Siedlungen haben.

Die Simulation muss jedoch zwischen direkter Kausalität und bloßer zeitlicher Nähe unterscheiden. Ein Ereignis darf nicht automatisch dem Spieler zugeschrieben werden, nur weil es nach einer seiner Handlungen eintritt. Questbedingungen können auf tatsächliche Zustände und Ereignisse reagieren; die Simulation darf keine Questfortschritte ohne erfüllte Bedingungen vergeben.

## 6.24 Abgrenzung und offene Spezifikation

Dieses Dokument beschreibt fachliche Simulationsanforderungen. Es legt keine konkrete Unity-Technologie, Datenbank, Job-System-Implementierung, Netzwerkarchitektur oder verbindliche Zahlenwerte fest. Diese Entscheidungen erfolgen in Dokumenten 09, 10 und 18 anhand realer Prototypen, Messungen und Zielplattformen.

Die Simulationsregeln müssen mit den Gameplay-Anforderungen aus Dokument 05, den Wirtschafts-/Itemregeln aus Dokument 13 und den kanonischen Daten-/Persistenzregeln aus Dokument 09 übereinstimmen.

## 6.25 Offene Entscheidungen

| ID | Thema | Status |
|---|---|---|
| SIM-001 | Finale NPC-Bedürfnisgruppen und deren Priorisierung | Offen |
| SIM-002 | Detailgrad und Speicherumfang persönlicher Erinnerungen | Offen |
| SIM-003 | Informationsverbreitung zwischen NPCs und Fraktionen | Offen |
| SIM-004 | Beziehungsmodell und Fraktionsdynamik | Offen |
| SIM-005 | Faktoren und Grenzen des Siedlungswachstums | Offen |
| SIM-006 | Konkrete Produktions-, Verbrauchs- und Transportregeln | Quellenabgleich/Design erforderlich |
| SIM-007 | Ökologische Populationsmodelle und Schutz seltener Arten | Offen |
| SIM-008 | Weltzeit bei geschlossenem Spiel und Offline-Fortschritt | Produktentscheidung erforderlich |
| SIM-009 | Simulationsintervalle, Radien und CPU-/Speicherbudgets | Profiling erforderlich |
| SIM-010 | Determinismus-Anforderungen über Plattformen und Spielstände hinweg | Technische Prüfung erforderlich |
| SIM-011 | Übergang von aggregierten Populationen zu individuellen NPCs/Tieren | Technische Spezifikation erforderlich |
| SIM-012 | Ereignisketten, Zufallssteuerung und globale Ereignisgrenzen | Offen |
| SIM-013 | Konkrete Rollen von Krankheiten, Verletzungen und Sterblichkeit in der Simulation | Offen |
| SIM-014 | Simulation politischer Konflikte, Bündnisse und territorialer Kontrolle | Lore-/Gameplay-Abgleich erforderlich |
| SIM-015 | Umgang mit Questfiguren und geschützten Populationen in Fernsimulation | Offen |


## 6.26 Ökologische Populationen und Genetik — Quellenkonkretisierung

Die Emberwild-Konzeptquellen erweitern das bisherige Ökologiemodell um explizite Populationsdynamik, Artenrollen, Nahrungsketten, Zuchtmerkmale und Mutationen. Für Vaelith wird daraus ein gemeinsames ökologisches Simulationsmodell abgeleitet; die ursprüngliche Asche-/Korruptionsthematik wird nicht automatisch als Vaelith-Weltmechanik übernommen.

Das Modell soll mindestens abbilden:
- Artenidentität, Lebensraum und regionale Verbreitung;
- Population, Geburten, Sterblichkeit und Zu-/Abwanderung;
- Nahrung, Wasser, Deckung und Tragfähigkeit eines Lebensraums;
- Räuber-Beute-Beziehungen und Konkurrenz;
- Jagd- und Sammeldruck durch Spieler/NPCs;
- Krankheiten, Verletzungen und Umweltgefahren;
- Domestizierung, Haltung, Zucht und Nachkommen;
- individuelle Merkmale, Abstammung und Generationen;
- seltene Arten und Schutz-/Erholungsmechanismen.

Genetik wird als nachvollziehbares Merkmalssystem ausgelegt. Die Originalkonzepte nennen mehrere Kernmerkmale, Zuchtlinien und Mutationen. Konkrete Merkmalsliste, Vererbungsformeln, Wahrscheinlichkeiten und Mutationsauslöser werden erst nach vollständiger Sichtung der Datenquellen und Balancingtests festgelegt. Ein genetischer Wert darf nicht ohne definierte Auswirkung als bloße Zahl existieren.

## 6.27 Meister, Vorarbeiter und Berufsentwicklung

Produktionsstätten können eine verantwortliche Meister- oder Vorarbeiterrolle besitzen. Diese Rolle ist von einem gewöhnlichen Arbeitsplatz zu unterscheiden: Sie umfasst fachliche Spezialisierung, Produktionsfokus, Qualitätssicherung, Anleitung und nachvollziehbare Betriebsberichte.

NPC-Berufsentwicklung soll eine mehrstufige Laufbahn unterstützen. Die Quelle beschreibt eine vierstufige Karriereidee; die konkrete Benennung und Werte sind noch zu prüfen. Berufserfahrung entsteht durch tatsächliche Arbeit, Training und geeignete Aufgaben. Meisterprägungen oder individuelle Spezialisierungen sind mögliche charakteristische Merkmale, dürfen aber nicht zu undurchsichtigen pauschalen Prozentboni werden.

Bedürfnisse, Moral und Arbeitsleistung sind getrennt zu modellieren. Eine Siedlungsmoral ist ein nachvollziehbarer aggregierter Zustand aus Versorgung, Sicherheit, Wohnqualität, sozialen Beziehungen und Ereignissen, nicht ein willkürlicher Einzelwert.

## 6.28 Ereignis- und Krisensteuerung

Ein übergeordnetes Ereignissystem kann ökologische, wirtschaftliche, soziale und sicherheitsbezogene Krisen koordinieren. Es beobachtet Weltindikatoren, erkennt Schwellen und erzeugt passende Ereignisketten. Es ersetzt nicht die Fachsimulation und darf keine unplausiblen Krisen allein zur Beschäftigung des Spielers erzeugen.

Jedes Ereignis benötigt Auslöser, betroffene Region/Akteure, Eskalationsstufen, Reaktionsfenster, Folgen, Auflösungsbedingungen und Schutz vor Wiederholungsschleifen. Ökologische Bedrohungen, organisierte Angriffe, Versorgungskrisen und politische Konflikte bleiben unterscheidbare Ereignisklassen.

Die in älteren Konzepten verwendete Asche-/Korruptionsmechanik wird nicht pauschal übernommen. Übertragbar ist das Prinzip eines transparenten, systemübergreifenden Krisen-Direktors; die konkrete Vaelith-Weltgefahr muss aus dem freigegebenen Setting entstehen.