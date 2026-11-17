# 16 — VAELITH Modular Development Pipeline (MDP)

## 16.1 Zweck

Die **VAELITH Modular Development Pipeline (MDP)** organisiert die Entwicklung in nachvollziehbare, überschaubare und integrierbare Arbeitspakete. Große Themenbereiche bzw. „Monolithen“ werden in Arbeitspakete und diese wiederum in Aufgaben und Unteraufgaben zerlegt.

MDP soll verhindern, dass riesige Systeme ungeplant parallel entstehen, dass Architektur ohne realen Spielkontext übermäßig theoretisch wird oder dass fertige Teilbereiche nicht integrierbar sind.

## 16.2 Hierarchie

1. **Projektleitbild und Manifest:** Gesamtziel, Grenzen und Prioritäten.
2. **Policies:** verbindliche Prozess-, Qualitäts-, Sicherheits- und Designregeln.
3. **System-Spezifikationen:** Verantwortlichkeiten, Daten, Schnittstellen und Verhalten eines Systems.
4. **Monolithen/Themenbereiche:** große fachliche Entwicklungsbereiche.
5. **Arbeitspakete:** abgrenzbare, integrierbare Liefergegenstände.
6. **Aufgaben/Unteraufgaben:** konkrete Implementierung, Dokumentation und Tests.

Die Zuordnung und Priorität müssen nachvollziehbar sein.

## 16.3 Vorbereitungsphase eines Arbeitspakets

Vor Implementierung:
- vorhandene Dokumentation und relevante Quellmaterialien prüfen;
- Ziel und Nicht-Ziele festhalten;
- Abhängigkeiten und betroffene Systeme ermitteln;
- bestehende Daten/Assets inventarisieren;
- erforderliche Entscheidungen identifizieren;
- Architektur und Daten-/API-Verträge konkretisieren;
- Risiken und Teststrategie definieren;
- Aufgaben und Abnahmekriterien erstellen;
- Umfang mit Projektleitung abstimmen, wenn er grundlegende Auswirkungen hat.

Erst danach beginnt die Umsetzung im freigegebenen Umfang.

## 16.4 Durchführung

Während der Entwicklung:
- kleine, nachvollziehbare Änderungen;
- projektweite Konventionen und Architektur einhalten;
- gemeinsame Datenmodelle verwenden;
- Abhängigkeiten und Änderungen dokumentieren;
- keine ungeprüften Placeholder als fertige Funktionen ausgeben;
- bei Konflikten oder neuen Risiken früh informieren;
- innerhalb genehmigter Grenzen eigenständig sinnvolle Entscheidungen treffen.

## 16.5 Fertigstellung und Übergabe

Ein Arbeitspaket gilt erst als fertig, wenn:
- spezifizierter Funktionsumfang umgesetzt ist;
- Integration mit abhängigen Systemen geprüft ist;
- Datenpersistenz und Migration berücksichtigt sind;
- Tests ausgeführt und Ergebnisse dokumentiert sind;
- bekannte Fehler und Einschränkungen offengelegt sind;
- Dokumentation und Bedien-/Entwicklerhinweise aktuell sind;
- Änderungen nachvollziehbar übergeben wurden.

Der Agent führt die Projektleitung nach Abschluss durch die geänderten Bereiche und Funktionen, damit diese bewertet werden können. Feedback und notwendige finale Anpassungen werden vor dem nächsten regulären Entwicklungsschritt aufgenommen. Dringende Sicherheits- oder Projektsicherheitskorrekturen dürfen sofort erfolgen, müssen aber transparent dokumentiert werden.

## 16.6 Eigenständigkeit und Entscheidungshoheit

Claude soll nicht nur mechanisch Aufträge ausführen. Der Agent soll fehlende Systeme, Abhängigkeiten, Datenlücken, Editoranforderungen, Performanceprobleme und Sicherheitsrisiken erkennen, priorisieren und Empfehlungen aussprechen.

Innerhalb eines genehmigten Arbeitspakets darf Claude die technische Umsetzung und Detailentscheidungen eigenständig organisieren. Grundlegende Richtungsentscheidungen, kreative Kernfragen, Scope-Erweiterungen und finale Abnahme verbleiben bei der Projektleitung.

Keine endlose Sammlung gleichwertiger Alternativen: Claude soll eine begründete Empfehlung aussprechen und eine klare Entscheidungsvorlage liefern.

## 16.7 Änderungsmanagement

Abweichungen von Spezifikation müssen mit Grund, Auswirkung, betroffenen Systemen und Migrationsbedarf dokumentiert werden. Scope-Erweiterungen werden priorisiert und abgestimmt, statt stillschweigend in ein Arbeitspaket einzufließen.

## 16.8 Statusmodell

Vorgeschlagene Statuswerte:
- Geplant;
- Spezifikation in Arbeit;
- Zur Entscheidung;
- Freigegeben;
- In Umsetzung;
- In Integration;
- In QA;
- Abnahmebereit;
- Abgenommen;
- Zurückgestellt;
- Blockiert.

Ein Status darf nur gesetzt werden, wenn die zugehörigen Bedingungen erfüllt sind. „Abnahmebereit“ bedeutet nicht „abgenommen“.

## 16.9 Artefakte je Arbeitspaket

Mindestens:
- Paketbeschreibung und Ziel;
- betroffene Systeme und Abhängigkeiten;
- Daten-/Schnittstellenspezifikation;
- Aufgabenliste;
- Test- und Abnahmekriterien;
- Änderungsprotokoll;
- offene Punkte/Risiken;
- Testnachweise;
- Übergabe-/Reviewnotizen.

## 16.10 Kommunikation

Projektentscheidungen und Statusmeldungen sollen präzise sein. Unausgeführte Tests dürfen nicht als bestanden gemeldet werden. Fehlende Quelldaten und unklare Absprachen müssen sichtbar bleiben. Agenten dürfen keine Änderungen an anderen Verantwortungsbereichen vornehmen, ohne Freigabe.


## 16.11 Inkrementelle Lieferung und laufende Sichtprüfung

Die MDP ist so auszuführen, dass die Projektleitung den Entwicklungsfortschritt jederzeit in funktionalen und visuellen Zwischenständen prüfen kann. Große Systeme werden deshalb nicht als ein einziger langer Entwicklungsblock umgesetzt.

Verbindlicher Ablauf:

1. Einen kleinen, fachlich sinnvollen und überprüfbaren Schritt aus dem freigegebenen Arbeitspaket bestimmen.
2. Vorab festlegen, welches konkrete Ergebnis dieser Schritt liefert und wie es geprüft werden kann.
3. Den Schritt implementieren und in den erforderlichen Systemkontext integrieren.
4. Die vorgesehenen automatisierten und manuellen Prüfungen tatsächlich ausführen.
5. Einen geeigneten Prüfstand bereitstellen: beispielsweise eine lauffähige Funktion, eine Editor-Arbeitsstrecke, eine Vorschau, eine Testszene oder einen reproduzierbaren Testfall.
6. Ergebnis, Prüfmethode, Testergebnisse, Einschränkungen und noch fehlende Teile verständlich übergeben.
7. Feedback der Projektleitung aufnehmen und erforderliche Korrekturen durchführen.
8. Erst danach den nächsten regulären Schritt beginnen, der auf diesem Ergebnis aufbaut.

### Anforderungen an prüfbare Zwischenstände

- Funktionale Änderungen müssen praktisch ausprobierbar sein, nicht nur im Quellcode nachvollziehbar.
- Visuelle Änderungen müssen in einer geeigneten Vorschau oder laufenden Anwendung sichtbar sein.
- Für nicht direkt zugängliche oder technisch noch nicht vollständig integrierte Funktionen ist ein reproduzierbarer Testweg bereitzustellen.
- Provisorische Zustände sind eindeutig als Prototyp, Platzhalter oder Teilimplementierung zu kennzeichnen.
- Ein Zwischenschritt darf notwendige Qualitäts-, Sicherheits- oder Datenintegritätsprüfungen nicht überspringen.
- Der Agent darf keine Abnahme unterstellen. „Geliefert“, „prüfbar“, „abnahmebereit“ und „abgenommen“ bleiben unterschiedliche Zustände.

Wenn technische Abhängigkeiten eine unmittelbare Sichtprüfung verhindern, muss der Agent die Ursache, die fehlende Voraussetzung und den frühestmöglichen sinnvollen Prüfpunkt benennen. Er soll den Umfang so schneiden, dass unnötig lange Phasen ohne sichtbaren oder funktionalen Fortschritt vermieden werden.

Die Projektleitung erhält damit regelmäßig Gelegenheit, tatsächliches Verhalten und Erscheinungsbild zu bewerten, bevor weitere Systeme oder Inhalte darauf aufbauen.
