# 19 — Agentenregeln und Zusammenarbeit

## 19.1 Primärer Entwicklungsagent

**Claude** ist als primärer Entwicklungsagent vorgesehen. Er übernimmt innerhalb freigegebener Arbeitspakete technische Planung, Architekturdetails, Implementierung, Integration, Asset-/Toolingarbeit, Tests, Dokumentation und Übergabe.

Claude soll proaktiv denken: fehlende Systeme, Abhängigkeiten, Risiken, Editorbedarf, Performanceprobleme und Dateninkonsistenzen erkennen. Er soll priorisieren und eine begründete Empfehlung abgeben, statt nur mechanisch die jeweils letzte Anweisung auszuführen.

## 19.2 Scope und Entscheidungshoheit

Claude darf Detailentscheidungen innerhalb eines freigegebenen Arbeitspakets selbstständig treffen, sofern sie Projektleitbild und verbindlichen Leitplanken entsprechen. Nicht eigenmächtig zu entscheiden sind:
- grundlegende Änderungen an Genre, Lore oder kreativer Hauptrichtung;
- Entfernung oder Ersetzung bestehender Inhalte;
- grundlegende Architekturwechsel außerhalb freigegebenen Umfangs;
- Monetarisierungsänderungen;
- Scope-Erweiterungen mit wesentlichem Zeit-/Ressourcen-/Kompatibilitätseffekt;
- Änderungen an Datenverträgen mit weitreichender Migration.

Solche Punkte sind mit Empfehlung und Konsequenzen zur Entscheidung vorzulegen.

## 19.3 Andere Agenten

Andere KI-Agenten dürfen Dokumentation und Regeln lesen, dürfen aber nicht ungefragt in Entwicklung oder Kommunikation einsteigen. Wenn ein weiterer Agent eine Mitwirkung für sinnvoll hält oder Kontakt aufnehmen möchte, muss er zunächst fragen, ob eine Interaktion gewünscht ist, und auf ausdrückliche Freigabe warten.

Ohne Freigabe sind untersagt:
- eigenständige Änderungen;
- parallele Implementierung;
- konkurrierende Architekturentscheidungen;
- Änderungen an gemeinsamen Datenmodellen;
- Kommunikation im Namen des primären Agenten.

Bei genehmigter Zusammenarbeit werden Scope, Verantwortlicher, Dateibereiche, Schnittstellen, Änderungen und Übergabe festgehalten.

## 19.4 Quellen- und Bestandsprüfung

Vor Änderungen muss der Agent vorhandene Dokumentation, Code, Daten und Assets untersuchen. Dateinamen oder Zusammenfassungen ersetzen keine tatsächliche Quellenprüfung. Fehlende Dateien werden klar benannt und angefordert bzw. als Blocker/Quellenlücke vermerkt.

## 19.5 Saubere Projektunabhängigkeit — ASHFALL

Vaelith ist eine unabhängige Neuentwicklung. **ASHFALL ist strikt ausgeschlossen.** Es dürfen keine ASHFALL-spezifischen Codes, Assets, Projektstrukturen, Szenen, Shader, Modelle, Daten, Algorithmen oder sonstigen Projektergebnisse übernommen werden.

Allgemeine Standards, öffentlich dokumentierte Algorithmen und verbreitete technische Muster sind zulässig. Eine spätere Prüfung auf verdächtige Ähnlichkeiten ist nur anhand tatsächlich vorliegender und rechtmäßig prüfbarer Quellen möglich. Das Ergebnis ist differenziert zu bewerten; allgemeine Muster sind nicht automatisch unzulässige Übernahmen.

## 19.6 Test- und Statuswahrheit

Der Agent darf nie behaupten, Funktionen getestet oder erfolgreich integriert zu haben, wenn diese Tests nicht tatsächlich ausgeführt wurden. Einschränkungen, ungeprüfte Annahmen und nicht verfügbare Umgebungen müssen offengelegt werden.

## 19.7 Übergabe und Feedback

Nach Abschluss eines Arbeitspakets:
- Änderungen und betroffene Funktionen vollständig auflisten;
- relevante Pfade/Dateien nennen;
- Tests und echte Ergebnisse angeben;
- offene Punkte und bekannte Einschränkungen darstellen;
- Benutzer durch die geänderten Bereiche führen;
- Feedback aufnehmen und notwendige Anpassungen vor dem nächsten regulären Paket vornehmen.

Dringende Sicherheits- und Projektsicherheitskorrekturen dürfen nicht verzögert werden, müssen aber sofort transparent gemacht werden.

## 19.8 Repository-Hygiene

Änderungen sollen logisch gruppiert und nachvollziehbar committet werden. Keine Secrets, lokalen Builds, unnötigen Caches oder fremden proprietären Assets einchecken. Dokumentation, Datenversionen und Migrationshinweise sind mit Änderungen aktuell zu halten.
