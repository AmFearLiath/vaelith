# 26 — Player Experience, Simulation Profiles und Wiederentdeckbarkeit

> **Dokumenttyp:** Übergreifendes Game-Design- und Systemkonzept  
> **Status:** Neue Konzept-Erweiterung zur gemeinsamen Abstimmung  
> **Geltungsbereich:** Spielerorientierung, individuelle Spielweisen, Simulationstiefe, Funktionsdarstellung, Wiederholbarkeit, Gameplay-Konfiguration und Spieler-Modding  
> **Verbindlichkeit:** Dieses Dokument erweitert die bestehende Vaelith-Vision. Es ist noch keine pauschale Implementierungsfreigabe. Begriffe und Zielprinzipien sind als Arbeitskonzept formuliert; technische Details und konkrete Balancingwerte bleiben offen.

---

## 26.1 Zweck und Einordnung

Dieses Dokument beschreibt eine Erweiterung des bestehenden Vaelith-Konzepts: Der Spieler soll nicht nur innerhalb einer vorgegebenen RPG-Spielweise agieren, sondern selbst bestimmen können, welche Aspekte der Welt er in den Mittelpunkt stellt, wie detailliert er einzelne Systeme erlebt und wie weit er die Spielerfahrung an seine eigenen Interessen anpasst.

Die Erweiterung ersetzt weder das bestehende Abenteuer-Rollenspiel noch dessen Geschichte, Welt, Charakterentwicklung oder zusammenhängende Simulation. Sie baut darauf auf und macht die vorhandenen Systeme zu einer flexibleren Grundlage für unterschiedliche, jeweils vollständige Spielerfahrungen.

**Kernthese:** Vaelith stellt eine gemeinsame lebendige Welt und zusammenhängende Spielsysteme bereit. Der Spieler entscheidet, welche Tätigkeiten, Systeme und Spielweisen er in dieser Welt priorisiert und mit welcher Detailtiefe er sie erleben möchte.

Vaelith soll dadurch viele Gründe bieten, eine bestehende Welt erneut zu entdecken, eine neue Welt anders zu beginnen oder eine bekannte Spielweise durch veränderte Regeln und Schwerpunkte neu zu erleben.

## 26.2 Übergeordnetes Spielversprechen

Vaelith soll dem Spieler keine einzelne korrekte Spielweise vorschreiben.

Der Spieler kann beispielsweise:
- als Abenteurer, Krieger oder Magier spielen;
- Landwirtschaft, Tierhaltung oder Handwerk in den Mittelpunkt stellen;
- als Händler, Kaufmann, Kutscher oder Transporteur leben;
- als Verwalter, Herold, Siedler oder späterer Herrscher wirken;
- mehrere Tätigkeiten miteinander verbinden;
- eine weitgehend automatisierte, entspannte Spielerfahrung bevorzugen;
- einzelne Systeme bewusst sehr detailliert und kontrollintensiv erleben;
- seine Spielerfahrung durch Konfigurationen und Mods grundlegend verändern.

Diese Ausrichtungen sind keine voneinander getrennten Spielmodi und keine starren Charakterklassen. Sie beschreiben Interessen und Schwerpunkte des Spielers. Sie dürfen ihn nicht daran hindern, andere Systeme zu nutzen, sofern deren reguläre Voraussetzungen erfüllt sind.

## 26.3 Drei getrennte Konfigurationsebenen

Die Begriffe Spielausrichtung, Spieler-Simulationstiefe und technische Simulationsdetailstufe müssen ausdrücklich getrennt bleiben.

### 26.3.1 Spielausrichtung (Playstyle)

Die Spielausrichtung beschreibt, welche Tätigkeiten und Themen der Spieler bevorzugt erleben möchte.

Beispiele:
- Abenteuer und Erkundung;
- Kampf und Magie;
- Landwirtschaft und Tierhaltung;
- Handel und Unternehmertum;
- Transport und Logistik;
- Handwerk und Produktion;
- Siedlungsentwicklung und Verwaltung;
- Beziehungen und gesellschaftliches Leben;
- Forschung, Entdeckung und Wissen.

Spielausrichtungen dienen der Priorisierung, Präsentation und optionalen Vorkonfiguration. Sie dürfen keine exklusiven Klassen, künstlichen Zugangssperren oder permanenten Bindungen erzeugen.

Mehrere Ausrichtungen können kombiniert und im Verlauf verändert werden. Eigene Kombinationen müssen möglich sein.

### 26.3.2 Spieler-Simulationstiefe (Player Simulation Depth)

Die Spieler-Simulationstiefe beschreibt, wie viel Detail, Kontrolle, Interaktion und Informationszugriff der Spieler in einem bestimmten System erhalten möchte.

Als Arbeitsmodell werden vier Stufen vorgeschlagen:

1. **Vereinfacht:** Routineabläufe sind weitgehend automatisiert oder zusammengefasst. Der Spieler trifft nur wesentliche Entscheidungen.
2. **Normal:** Der Spieler übernimmt übliche Entscheidungen und nutzt die regulären Kernfunktionen.
3. **Detailliert:** Zusätzliche Parameter, Zwischenschritte, Zustände und Eingriffsmöglichkeiten werden sichtbar und steuerbar.
4. **Tiefensimulation:** Das System bietet die höchste vorgesehene fachliche Detailtiefe, erweiterte Kontrolle und umfassende Auswertungen.

Die Stufen sind keine Schwierigkeitsgrade. Höhere Stufen dürfen nicht lediglich mehr Klickarbeit bedeuten. Sie müssen sinnvolle zusätzliche Kontrolle, Erkenntnis und Gestaltungsmöglichkeiten bieten.

Die Einstellung erfolgt pro geeignetem Funktionsbereich. Ein globales Profil kann Startwerte oder Presets anbieten, darf aber individuelle Systemwerte nicht ersetzen.

### 26.3.3 Technische Simulationsauflösung der lebendigen Welt

Die bestehende Simulation benötigt abgestufte Aktualisierung nach Entfernung, Relevanz, Aktivität und Simulationsbudget. Diese technische Auflösung bestimmt, wie Weltobjekte im Hintergrund effizient fortgeführt werden.

Sie ist **nicht** identisch mit der vom Spieler gewählten Simulationstiefe.

Beispiel: Ein Spieler kann eine detaillierte Wirtschaftssimulation wünschen, obwohl entfernte Regionen technisch aggregiert berechnet werden. Umgekehrt kann ein NPC-System in unmittelbarer Nähe hochauflösend laufen, obwohl der Spieler für die NPC-Verwaltung eine vereinfachte Bedienung gewählt hat.

Die technische Auflösung muss die fachlichen Ergebnisse und zugesicherten Regeln erhalten. Sie darf nicht willkürlich den Inhalt oder die Konsequenzen der Spielerfahrung verändern.

## 26.4 Player Experience Configuration System (PECS)

Als übergreifender Systembegriff wird **Player Experience Configuration System (PECS)** vorgeschlagen.

PECS verwaltet die individuelle Ausrichtung und Darstellung der Spielerfahrung. Es implementiert nicht selbst die fachlichen Spielmechaniken und besitzt keine parallele Weltwahrheit.

Vorgesehene Verantwortungsbereiche:
- Spielausrichtungen und kombinierbare Schwerpunkte;
- Simulationsprofile und individuelle Detailstufen pro System;
- Funktionsgruppen, Sichtbarkeit und progressive Erklärung;
- Automatisierungs- und Delegationspräferenzen;
- Gameplay-Konfigurationen und Presets;
- Freischalt- und Verfügbarkeitsinformationen aus den zuständigen Spielsystemen;
- Laufzeitänderungen und deren sichere Übernahme;
- Profilimport, -export und spätere Weitergabe;
- Validierung von Abhängigkeiten und Konflikten zwischen Konfigurationen.

PECS ist eine koordinierende Schicht. Die Fachsysteme bleiben Eigentümer ihrer Regeln, Zustände, Aktionen und Validierungen.

## 26.5 Funktionsgruppen und adaptive Darstellung

Die Bedienoberfläche soll die Funktionen des Spiels passend zur gewählten Spielausrichtung, dem Freischaltzustand und der gewählten Detailtiefe gruppieren und visualisieren.

Beispiele für Funktionsgruppen:
- Abenteuer, Erkundung und Kampf;
- Charakter, Fähigkeiten und Magie;
- Landwirtschaft, Tierhaltung und Versorgung;
- Handwerk, Produktion und Lager;
- Handel, Märkte und Wirtschaft;
- Transport, Routen und Logistik;
- NPCs, Beziehungen und Gesellschaft;
- Siedlungen, Bau und Verwaltung;
- Kreaturen, Zucht und Ausbildung;
- Quests, Wissen und Weltgeschehen.

Die Darstellung muss drei Fragen getrennt beantworten:
1. Ist eine Funktion grundsätzlich verfügbar?
2. Ist sie bereits entdeckt oder freigeschaltet?
3. Wie detailliert möchte der Spieler sie bedienen?

Die Spielausrichtung darf Funktionen hervorheben, aber nicht grundsätzlich verstecken, wenn der Spieler sie bewusst aufrufen möchte. Die Detailstufe darf nur die für sie vorgesehene Bedien- und Informationsform beeinflussen, nicht Questbedingungen, Weltfakten oder reguläre Freischaltungen.

Neue Funktionen sollen schrittweise verständlich werden. Die Oberfläche darf den Spieler nicht zu Beginn mit sämtlichen Systemen und Parametern überfordern. Progressive Offenlegung muss transparent bleiben; sie darf nicht den Eindruck erwecken, ein System existiere nicht oder sei dauerhaft ausgeschlossen.

## 26.6 Automatisierung und Delegation

Vereinfachte Stufen sollen geeignete Routinehandlungen zusammenfassen oder delegieren können.

Mögliche Beispiele:
- automatische Aussaat und Ernte durch zugewiesene Arbeitskräfte;
- automatische Lagerauffüllung anhand definierter Mindestbestände;
- selbstständige Ausführung freigegebener Handelsrouten;
- automatische Zuweisung von NPC-Arbeitsaufgaben;
- standardisierte Produktionsabläufe;
- zusammengefasste Verwaltung von Tierpflege oder Versorgung.

Automatisierung ist keine folgenlose Abkürzung. Sie verwendet dieselben Ressourcen, Zeitregeln, Fähigkeiten, Arbeitskräfte, Risiken und Weltzustände wie manuelle Abläufe. Kosten, Ergebnisse, Fehler und wichtige Entscheidungen müssen nachvollziehbar bleiben.

Der Spieler muss erkennen können, was automatisiert wird, nach welchen Regeln es geschieht, welche Ressourcen und Akteure beteiligt sind, welche Grenzen und Risiken gelten und wie er eingreifen, pausieren oder die Automatisierung beenden kann.

## 26.7 Unabhängigkeit von Quest, Story und zentralem Fortschritt

Quest- und Storyfortschritt bleiben fachlich unabhängig von Spielausrichtung und persönlicher Simulationstiefe.

Die Quest Runtime bleibt Eigentümerin von Questzustand, Bedingungen, Objectives, Entscheidungen, Wissen und narrativen Konsequenzen. PECS darf diese Zustände weder überspringen noch umdeuten.

Quests müssen unterschiedliche, fachlich gleichwertige Lösungswege berücksichtigen können, sofern das jeweilige Questdesign sie vorsieht.

Beispiel: Eine benötigte Lieferung kann – abhängig von den tatsächlichen Möglichkeiten und Weltzuständen – selbst produziert, gekauft, gehandelt, transportiert oder durch eine andere ausdrücklich vorgesehene Lösung beschafft werden.

Dabei gelten folgende Regeln:
- Questidentität und Questfortschritt hängen nicht von einer ausgewählten Spielausrichtung ab.
- Questbedingungen prüfen reale Welt- und Spielerzustände, nicht die bloße Profilbezeichnung.
- Zeitliche Abläufe und Ereignisse werden durch Quest Runtime beziehungsweise Weltzeit gesteuert, nicht durch UI- oder Simulationspräferenz.
- Alternative Lösungswege müssen explizit im Questdesign modelliert und getestet werden.
- Automatisierte Abläufe dürfen gültige Questereignisse erzeugen, sofern sie dieselben autorisierten Weltaktionen und Validierungen verwenden.
- Eine vereinfachte Bedienung darf erzählerisch oder spielmechanisch notwendige Konsequenzen nicht unsichtbar machen.
- Freischaltungen durch Story und Quests bleiben wirksam, unabhängig von der gewählten Spielausrichtung.

## 26.8 Wiederentdeckbarkeit und langfristige Motivation

Wiederholbarkeit soll nicht allein durch zufällige Gegner, höhere Zahlen oder künstlich verlängerte Spielzeit entstehen. Sie soll aus unterschiedlichen Möglichkeiten, Entscheidungen, Weltzuständen und selbst gewählten Schwerpunkten hervorgehen.

Vaelith soll mehrere Ebenen der Wiederentdeckung unterstützen:

### 26.8.1 Neue Spielausrichtungen

Ein neuer Durchlauf kann andere Tätigkeiten in den Mittelpunkt stellen: beispielsweise Abenteuer, Handel, Landwirtschaft, Logistik, Handwerk, soziale Beziehungen oder Verwaltung.

### 26.8.2 Andere Simulationsprofile

Dieselbe Tätigkeit kann unterschiedlich erlebt werden: automatisiert und entspannt, ausgewogen, detailliert oder als intensive Tiefensimulation.

### 26.8.3 Unterschiedliche Regel- und Gameplay-Profile

Spieler können freigegebene Regeln kombinieren, Mechaniken konfigurieren und eigene Profile erstellen. Solche Profile müssen Versionen, Voraussetzungen und eventuelle Einschränkungen dokumentieren.

### 26.8.4 Dynamische und prozedurale Weltvariationen

Weltgenerierung, Regionen, Siedlungen, Ressourcenverteilung, Fraktionen, Ereignisse und andere geeignete Systeme können unterschiedliche Ausgangslagen schaffen. Bereits erschlossene oder persistierte Weltinhalte dürfen dabei nicht unkontrolliert überschrieben werden.

### 26.8.5 Unterschiedliche Entscheidungen und Konsequenzen

Questentscheidungen, Beziehungen, Fraktionszustände, wirtschaftliche Entwicklungen und Weltgeschehnisse können zu unterschiedlichen Verläufen führen. Die konkrete Story bleibt kohärent und darf nicht zu beliebiger Zufallsvariation werden.

### 26.8.6 Spielererstellte Erweiterungen

Datenmods, Regelpakete, Gameplay-Erweiterungen und Code-Mods können zusätzliche Inhalte und Spielweisen ermöglichen. Die jeweilige Mod-Kategorie, Vertrauensstufe, Abhängigkeit und Kompatibilität müssen deutlich erkennbar sein.

### 26.8.7 Langfristige Entdeckungen

Auch in einer bekannten Welt sollen neue Ziele, Zusammenhänge, Orte, Tätigkeiten und Konsequenzen entstehen können. Neue Spielweisen sollen vorhandene Systeme anders miteinander verbinden, nicht nur eine andere Benutzeroberfläche zeigen.

## 26.9 Gameplay-Konfiguration und Modding: klare Abgrenzung

Nicht jede Anpassung ist eine Mod. Das Konzept unterscheidet:

1. **Native Spieleinstellungen:** Vom Grundspiel unterstützte Optionen wie Bedienung, Automatisierung und Detailtiefe.
2. **Gameplay-Profile:** Gespeicherte Kombinationen nativer Einstellungen und freigegebener Regeln.
3. **Regel-/Daten-Erweiterungen:** Zusätzliche oder veränderte Definitionen, Regeln und Inhalte über validierte Erweiterungspunkte.
4. **Code-Mods:** Erweiterungen mit ausführbarem Code über die offizielle Vaelith Mod API.

Die ersten beiden Kategorien müssen ohne externe Programme im Spiel zugänglich sein. Die Kategorien drei und vier nutzen die bestehenden Vorgaben aus `11-modding-api.md`.

Ein integrierter Mod-Browser beziehungsweise Mod-Manager kann später aus dem Spiel heraus Installation, Aktivierung, Reihenfolge, Abhängigkeiten, Vertrauenshinweise und Diagnose ermöglichen. Ob und wie Community-Verteilung, Hosting und Moderation umgesetzt werden, bleibt eine gesonderte Produkt- und Betriebsentscheidung.

Code-Mods sind privilegierter In-Process-Code und dürfen nicht als sicher sandboxed dargestellt werden. Daten- und Regelpakete benötigen dagegen ein enges, validiertes Schema und dürfen nicht durch beliebige ausführbare Ausdrücke zu Code-Mods werden.

## 26.10 Profile, Spielstände und Laufzeitwechsel

Spielausrichtung und Simulationspräferenzen sollen pro Spielstand beziehungsweise Kampagne speicherbar sein. Globale Komfortvorgaben können als Vorlage dienen, dürfen aber bestehende Spielstände nicht ungefragt verändern.

Ein Profil soll mindestens nachvollziehbar machen:
- ausgewählte Spielausrichtungen;
- Detailstufe pro Funktionsbereich;
- Automatisierungs- und Delegationsregeln;
- aktivierte Gameplay-Profile;
- verwendete Regel- und Mod-Pakete;
- Versionen, Abhängigkeiten und Prioritäten;
- notwendige Welt- oder Kampagnenrestriktionen.

Spieler sollen Simulationsstufen während einer laufenden Welt wechseln können. Änderungen müssen validiert und abhängig vom betroffenen System sofort oder zu einem definierten sicheren Übergangspunkt wirksam werden.

Ein Wechsel darf keine Ressourcen, NPCs, Quests, Weltzustände oder laufenden Transaktionen duplizieren, löschen oder rückwirkend verfälschen. Bereits erzeugte Konsequenzen bleiben bestehen. Eine Änderung der Bedien- oder Automatisierungspräferenz ist keine Rücknahme bereits ausgeführter Weltaktionen.

Bei Mod- oder Regeländerungen gelten zusätzlich die Kompatibilitäts-, Migrations- und Wiederherstellungsregeln aus `09-data-architecture.md` und `11-modding-api.md`.

## 26.11 Abhängigkeiten und Konflikte

Konfigurationen und Erweiterungen benötigen explizite Abhängigkeiten und Gültigkeitsregeln.

Zu prüfen sind insbesondere:
- erforderliche Gameplay-Systeme und Erweiterungspunkte;
- gegenseitig ausschließende oder widersprüchliche Regeln;
- Prioritäten bei überschneidenden Definitionen;
- Auswirkungen auf laufende Aktionen und Transaktionen;
- Auswirkungen auf bestehende Welt- und Questzustände;
- fehlende oder aktualisierte Erweiterungen;
- Unterschiede zwischen Profil-, Content-, API- und Spielversionen.

Ungültige Konfigurationen dürfen nicht stillschweigend teilweise angewendet werden. Der Spieler benötigt eine verständliche Diagnose und – soweit möglich – eine sichere Rückkehr zur letzten gültigen Konfiguration.

## 26.12 Multiplayer-Abgrenzung

Das bestehende Projekt ist Singleplayer-first; Multiplayer ist noch keine verbindliche Releaseanforderung.

Falls Multiplayer später umgesetzt wird, müssen gemeinsame Weltregeln, aktive Mods und relevante Simulationskonfigurationen zwischen Teilnehmern konsistent sein. Individuelle UI-Präferenzen dürfen lokal bleiben, während weltverändernde Regeln und Code-Erweiterungen einer verbindlichen Host-/Server- und Kompatibilitätsregel folgen müssen.

Diese Dokumentation legt keine Multiplayer-Architektur fest.

## 26.13 Vorgesehene Systemverantwortung

| Bereich | Fachliche Verantwortung |
|---|---|
| PECS | Spielausrichtung, Profile, Spieler-Simulationstiefe und Funktionsdarstellung |
| Gameplay-Systeme | Eigentliche Aktionen, Regeln und Spielzustände |
| Living World Simulation | Weltzeit, NPCs, Wirtschaft, Ökologie und technische Simulationsauflösung |
| Quest Runtime | Questbedingungen, Objectives, Entscheidungen und narrative Konsequenzen |
| Unlock-/Progression-Systeme | Tatsächliche Freischaltbedingungen und Fortschrittszustände |
| Datenarchitektur | IDs, Versionen, Persistenz, Migration und Provenienz |
| Vaelith Mod API | Validierte Erweiterungspunkte und Code-/Daten-Mod-Lebenszyklus |
| UI | Darstellung und Bedienung entsprechend der gültigen Konfiguration |

PECS darf keine zweite Quelle für Questfortschritt, Freischaltungen, NPC-Zustände, Wirtschaftsbestände oder andere fachliche Zustände schaffen.

## 26.14 Qualitäts- und Abnahmekriterien für spätere Umsetzung

Ein späteres PECS-Arbeitspaket ist nicht allein dadurch erfüllt, dass ein Einstellungsmenü existiert.

Zu validieren sind mindestens folgende Ende-zu-Ende-Szenarien:

1. Ein Spieler startet mit einer ausgewählten Spielausrichtung und erhält eine verständlich gruppierte, aber nicht künstlich beschränkte Oberfläche.
2. Ein Spieler wählt für Landwirtschaft eine vereinfachte und für Handel eine detaillierte Simulation.
3. Ein Spieler ändert die Detailstufe eines laufenden Systems, ohne Weltzustände oder laufende Transaktionen zu beschädigen.
4. Ein automatisierter Produktions- oder Transportablauf verwendet dieselben fachlichen Regeln, Ressourcen und Ereignisse wie ein manueller Ablauf.
5. Eine Quest kann unabhängig von der Spielausrichtung über mehrere vorgesehene Lösungswege erfüllt werden.
6. Ein Questereignis tritt korrekt ein, auch wenn der Spieler eine Tätigkeit automatisiert oder gerade nicht aktiv bedient.
7. Eine Funktion wird als verfügbar, entdeckt oder freigeschaltet korrekt dargestellt; die Profilwahl umgeht keine Freischaltbedingung.
8. Ein gespeichertes Profil wird mit korrekten Versionen und Abhängigkeiten wiederhergestellt.
9. Eine ungültige Regel- oder Mod-Konfiguration wird erkannt, verständlich erklärt und sicher abgelehnt.
10. Ein neuer Spieldurchlauf mit anderem Profil erzeugt eine spürbar andere Spielerfahrung, ohne die gemeinsame Weltlogik zu brechen.

Zusätzlich sind Usability, Accessibility, Performance, Savegame-Migration und langfristige Konsistenz zu prüfen.

## 26.15 Vorgeschlagene Konzeptbausteine und spätere Lieferobjekte

Die nachfolgende Gliederung ist eine mögliche spätere Spezifikation, keine bereits genehmigte Roadmap:

- PECS-Grundmodell und Begriffsvertrag;
- Katalog der Spielausrichtungen und Tätigkeitsgruppen;
- Taxonomie der Funktionsbereiche;
- Simulationsstufen je Funktionsbereich;
- Automatisierungs- und Delegationsmodell;
- Profil- und Presetformat;
- adaptive Funktionsnavigation und UI-Verhalten;
- Laufzeitwechsel und Transaktionsgrenzen;
- Quest-Kompatibilitäts- und Lösungswegregeln;
- Wiederentdeckbarkeits- und New-Run-Konzept;
- Schnittstellen zur Mod API;
- Savegame-, Versions- und Migrationsregeln;
- Testwelten, Diagnose und Performancebudgets.

## 26.16 Offene Entscheidungen

Die folgenden Punkte bleiben ausdrücklich offen und müssen vor ihrer Implementierung spezifiziert werden:

- endgültige Bezeichnung und Umfang von PECS;
- finale Liste und Benennung der Spielausrichtungen;
- ob Spielausrichtungen nur empfehlen/vorbelegen oder weitere UI-Priorisierung steuern;
- genaue Zahl und Semantik der Simulationsstufen;
- welche Funktionsbereiche eigene Simulationsstufen benötigen;
- welche Systeme sinnvoll automatisierbar oder delegierbar sind;
- Regeln für Sofortwechsel und sichere Übergangspunkte;
- Verhältnis zwischen globalen Einstellungen, Spielstandprofilen und Kampagnenprofilen;
- Profilformat, Import/Export und Teilen mit anderen Spielern;
- welche Regeländerungen nativ, welche als Datenmods und welche ausschließlich als Code-Mod zulässig sind;
- wie unterschiedliche New-Game-Profile Weltgenerierung und Startbedingungen beeinflussen dürfen;
- wie Wiederholungsanreize gestaltet werden, ohne künstliches Grinden oder unnötige Wiederholungspflichten zu erzeugen;
- ob eine Community-Mod-Plattform Teil des Spiels oder ein späterer separater Dienst wird;
- Auswirkungen auf künftige Multiplayer-Scope- und Synchronisationsentscheidungen.

## 26.17 Zusammenfassung

Vaelith bleibt eine gemeinsame, lebendige, vollständig dreidimensionale Welt mit einer zusammenhängenden Geschichte und miteinander verbundenen Gameplay-Systemen.

Die Erweiterung macht diese Welt zu einer flexibleren Grundlage für unterschiedliche vollständige Spielerfahrungen:

- Der Spieler entscheidet, welche Tätigkeiten und Spielweisen er priorisiert.
- Er legt für geeignete Systeme individuell fest, wie detailliert er sie erleben möchte.
- Er kann Automatisierung und Delegation nutzen, ohne die Weltlogik auszuschalten.
- Er kann die Konfiguration während einer laufenden Welt verändern.
- Quests, Story und echte Freischaltungen bleiben unabhängig davon.
- Er kann durch andere Profile, Entscheidungen, Weltzustände und Erweiterungen Vaelith immer wieder neu entdecken.
- Er kann die Spielerfahrung mit nativen Einstellungen, Profilen, Regelpaketen und Mods weiter verändern.

**Leitidee:** Vaelith schreibt nicht vor, wie die Welt gespielt werden muss. Vaelith schafft eine glaubwürdige Welt und vielseitige Systeme, aus denen der Spieler seine eigene Spielerfahrung formt.
