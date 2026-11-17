# 25 — Quest-System-Spezifikation für Vaelith

> Status: Ausgearbeitetes Vaelith-Arbeitskonzept auf Basis der Emberwild-Quelle questsystem/expansion_questsystem.md. Das ursprüngliche Quest-System war nicht fertig entwickelt. Dieses Dokument definiert die Zielarchitektur und kennzeichnet noch ausstehende Datenmigrationen.

## 25.1 Leitentscheidung

Vaelith erhält ein datengetriebenes, zentrales Quest- und Narrative-System. Questlogik wird nicht in Szenenskripten, NPC-Komponenten oder einzelnen Dialogen fest verdrahtet. Eine Quest Runtime verarbeitet typisierte Ereignisse aus Gameplay und Simulation und koordiniert Questfortschritt, Entscheidungen, Dialoge, Wissen, Belohnungen und Weltaktionen.

Die Runtime besitzt nicht selbst die Wahrheit über Inventar, NPCs, Fraktionen, Regionen, Wirtschaft, Gebäude oder Kreaturen. Diese Daten bleiben in den jeweiligen Fachsystemen. Die Quest Runtime fragt sie über definierte Schnittstellen ab und fordert Änderungen über autorisierte Services an.

Grundregeln:
- Stabile IDs für Quests, Questlinien, Objectives, Gruppen, Entscheidungen, Optionen, Dialoge, Wissenseinträge und Weltaktionen.
- Definitionen und individueller Spielfortschritt sind strikt getrennt.
- Questdaten sind deklarativ und enthalten keinen beliebigen ausführbaren Code.
- Alternative Lösungen müssen echte spielmechanische Alternativen sein.
- Ereignisse, Belohnungen und Weltaktionen müssen idempotent und savegame-sicher sein.
- Questfortschritt funktioniert unabhängig davon, ob ein NPC oder eine Region detailliert oder aggregiert simuliert wird.

## 25.2 Systemaufteilung

| System | Aufgabe |
|---|---|
| Quest Definition Registry | Laden, Versionieren und Validieren der Questdefinitionen |
| Quest Runtime | Lifecycle, Fortschritt, Abhängigkeiten und Ablaufsteuerung |
| Event Router | Zustellung typisierter Gameplay- und Simulationsereignisse |
| Condition Evaluator | Sichere Auswertung verschachtelter Bedingungen |
| Objective Engine | Objective-Fortschritt, Gruppen und alternative Pfade |
| Decision Ledger | Dauerhafte Spielerentscheidungen und deren Herkunft |
| World State Service | Kanonische Welt-, NPC-, Regions- und Fraktionszustände |
| World Action Service | Autorisierte und wiederholungssichere Weltänderungen |
| Knowledge Service | Hinweise, Erkenntnisse, Quellen und Widersprüche |
| Dialogue Runtime | Dialogknoten, Optionen, Bedingungen und Aktionen |
| Reward Service | Validierung, Vergabe und Protokollierung von Belohnungen |
| Player Quest State | Individueller Questfortschritt im Spielstand |
| Quest Editor | Authoring, Ablaufvorschau, Simulation und Diagnose |

## 25.3 Questdefinition

Die vorhandenen Emberwild-Felder id, kind, act, chapter, order, civilization, minLevel, recommendedLevel, giver, turnIn und area bleiben bei der Migration erhalten, sofern ihre Bedeutung in den Quelldaten bestätigt ist.

Die Questline erhält eine stabile ID; Anzeigenamen werden separat lokalisiert. Tags, Version, Author, Reviewed, LastModified, Priority, Visibility, Ending und BoardPos bleiben erhalten. BoardPos ist ausschließlich Editorlayout und darf keine Runtime-Auswirkung haben.

Zusätzliche Vaelith-Metadaten:
- Category: Hauptgeschichte, Nebenquest, Begleiter, Fraktion, Erkundung, Handwerk, Siedlung, Ereignis oder wiederholbare Aktivität.
- AvailabilityPolicy: Voraussetzungen und Angebotsregeln.
- FailurePolicy: explizite Scheiterbedingungen.
- RepeatPolicy: Wiederholung, Cooldown und Reset.
- ContentStatus: Draft, Review, Approved oder Deprecated.
- SourceRefs: Herkunft und Migrationsbezug.

Questnamen, Beschreibungen, Journaltexte und Dialoge liegen in lokalisierten Textressourcen, nicht als fest verdrahtete Runtime-Texte.

## 25.4 Lifecycle und Spielregeln

Statuswerte:
- locked: Voraussetzungen nicht erfüllt oder Quest verborgen.
- available: Quest kann angenommen bzw. gestartet werden.
- active: Quest läuft.
- completed: erfolgreich abgeschlossen.
- failed: durch explizite Bedingungen gescheitert.
- abandoned: vom Spieler bewusst aufgegeben, sofern erlaubt.

Pausiert, blockiert oder wartend sind Laufzeitmerkmale und keine zusätzlichen Hauptstatuswerte.

Vaelith-Entscheidungen:
- Hauptstory-Quests sind standardmäßig nicht aufgebbar.
- Nebenquests dürfen aufgegeben werden, sofern dadurch keine inkonsistenten Weltzustände entstehen.
- Zeitlimits werden nur verwendet, wenn Dringlichkeit und Konsequenz verständlich kommuniziert sind. Verdeckte, unfair verpasste Timer sind ausgeschlossen.
- Scheitern tritt nur bei ausdrücklich definierten Failure Conditions ein. Ein verpasstes optionales Ziel ist kein automatisches Questversagen.
- Wiederholbarkeit ist ausdrücklich zu konfigurieren. Hauptstory und einmalige Konsequenzquests werden nicht zurückgesetzt.
- Wiederholbare Aktivitäten erhalten pro Durchlauf eine eigene Run-ID; historische Abschlüsse bleiben erhalten.

## 25.5 Conditions und Trigger

Conditions werden als typisierte Ausdrucksbäume gespeichert. Unterstützt werden AND, OR und NOT sowie typisierte Operatoren für Gleichheit, Ungleichheit, Größenvergleiche, Existenz, Mengenmitgliedschaft und Enthaltensein.

Bedingungsdomänen:
- Queststatus und Questlinienfortschritt;
- Items, Mengen, Ausrüstung und Besitz;
- Charakterwerte, Fähigkeiten und Level;
- Magie-/Resonanzwerte, sofern das Vaelith-System sie bereitstellt;
- Wissen und bestätigte Erkenntnisse;
- NPC-Zustände, Beziehungen und Verfügbarkeit;
- Fraktionen und Reputation;
- Regionen, Orte, Zugänge und Weltzustände;
- Tagesphase, Saison und Ereignisse;
- Gebäude, Siedlungen, Produktion und Versorgung;
- Kreaturen, Zucht, Haltung und Ökologie.

Itembedingungen unterscheiden Besitzprüfung, Mindestmenge, Verbrauch bei erfolgreicher Aktion und bloße Verfügbarkeit. Eine Prüfung darf niemals versehentlich Items verbrauchen.

Trigger abonnieren typisierte Ereignisse oder reagieren auf definierte Interaktionspunkte. Sie führen keine beliebigen Scripts aus.

## 25.6 Objective-System

Die vorhandenen Typen bleiben erhalten: talk, kill, collect, interact, discover, investigate, deliver, craft, gather, escort, protect, survive, reach, activate, choose, reputation, knowledge und world_state.

Sinnvolle Vaelith-Erweiterungen können build, assign, defend, breed, produce, trade, explore_route und resolve_event sein. Neue Typen werden nur ergänzt, wenn sie einen eigenen Ereignisvertrag benötigen.

Jedes Objective besitzt stabile ID, Typ, Bedingungen, Referenzen, Fortschritt, Status und optionale Zielmenge. dependsOn definiert Abhängigkeiten als gerichteten azyklischen Graphen. objectiveGroups gruppieren Objectives über AND, OR oder SEQUENCE. Optionale Ziele und alternative Lösungen werden ausdrücklich modelliert.

Zyklen sind ungültig. Unerreichbare Objectives, nicht erfüllbare Bedingungen und fehlende Endzustände müssen im Editor angezeigt werden. Fortschritt wird persistent gespeichert und ein Event darf dasselbe Objective nicht mehrfach erfüllen.

## 25.7 Entscheidungen und Konsequenzen

Eine Quest kann mehrere Entscheidungen enthalten. Jede Entscheidung besitzt ID, Verfügbarkeit, Bedingungen, Optionen und Konsequenzen. Jede Option besitzt lokalisierte Texte, Voraussetzungen, Hinweise auf relevante Folgen und deklarative Aktionen.

Der Decision Ledger speichert Quest-/Run-ID, Decision-ID, ausgewählte Option, Zeit, Kontext, ausgeführte Konsequenzen und Definitionsversion.

Vaelith-Designregeln:
- Entscheidungen können sofortige oder verzögerte Folgen haben.
- Verzögerte Folgen müssen später nachvollziehbar auf die Entscheidung zurückführbar sein.
- Irreversible Entscheidungen benötigen eine verständliche Vorbereitung und Schutz vor versehentlicher Auslösung.
- Es gibt nicht grundsätzlich eine gute und eine böse Option. Vertrauen, Sicherheit, Beziehungen, Wissen und langfristige Weltfolgen können konkurrieren.
- Keine Scheinentscheidungen: Gleiche Folgen mehrerer Optionen müssen bewusst und erzählerisch begründet sein.
- NPC-AI, Vaelith oder Hintergrundsimulation dürfen Spielerentscheidungen nicht stillschweigend überschreiben.

## 25.8 World State und World Actions

World State ist ein zentraler Dienst für persistente Fakten und temporäre Zustände. Beispiele sind NPC-Status, Fraktionskontrolle, Regionsfreigabe, Routensicherheit, Gebäudezustand, Siedlungsversorgung und globale Ereignisse.

Jeder Zustand besitzt Scope, typisierten Wert, Persistenz-/Ablaufregel, Herkunft und Änderungszeit.

World Actions sind zentral definierte Aktionen, die von autorisierten Fachsystemen ausgeführt werden. Mehrere Teilaktionen müssen atomar oder kompensierbar sein. Wiederholungsschutz basiert auf stabiler Action-ID und Ausführungskontext. Quests verändern keine fremden Daten direkt, sondern stellen geprüfte Anforderungen an den zuständigen Service.

## 25.9 Knowledge System

Wissen ist mehr als ein boolesches Questflag. Ein Eintrag besitzt ID, Thema, lokalisierte Darstellung, Quellen, Erwerbsweg, Bestätigungsstatus und Beziehungen zu anderen Erkenntnissen.

Status:
- unbekannt;
- Hinweis/Indiz;
- unbestätigt;
- bestätigt;
- widerlegt;
- widersprüchlich/umstritten.

Widersprüchliche Überlieferungen dürfen nebeneinander bestehen. Das System erklärt nicht automatisch die zuerst gefundene Quelle zur Wahrheit. Quests, Dialoge und NPC-Reaktionen können prüfen, was der Spieler tatsächlich weiß und wie belastbar dieses Wissen ist.

## 25.10 Dialogsystem

Dialoge sind eigenständige lokalisierte Daten. Sie enthalten Einstiegspunkte, Knoten, Optionen, Bedingungen, Aktionen, Sprecherreferenzen und optionale Inszenierungsmarker.

Optionen können von Queststatus, Entscheidungen, Wissen, Beziehungen, Fraktionen, Spielerhandlungen und Weltzuständen abhängen. Dialogaktionen rufen deklarative World Actions oder definierte Gameplay-Aktionen auf.

Dialoge müssen unterbrechbar und sicher fortsetzbar sein. NPC-Tod, Abwesenheit, Bewegung, Kampf oder Zustandswechsel müssen kontrollierte Abbrüche erlauben. Mehrfachausführung von Konsequenzen ist ausgeschlossen. Dialoglogik und Kamera-/Animationsinszenierung bleiben getrennt.

NPC-Reaktionen ergeben sich nicht nur aus Quest-IDs, sondern aus Persönlichkeit, Kenntnis, Beziehung und Weltzustand.

## 25.11 Belohnungen

Das vorhandene Einzelitem-Feld wird in ein einheitliches Items-Array überführt. Bestehende Belohnungsarten bleiben erhalten: XP, Gold, Items, Materialien, Vaelith-Resonanz, Buffs, Lore, Baupläne und Gebietsfreischaltungen.

Zusätzlich möglich sind bedingte und wählbare Belohnungen, Reputation, Beziehungsänderungen, Wissen, Rezepte und Funktionsfreischaltungen.

Jede Vergabe besitzt eine eindeutige Grant-ID und wird protokolliert. Inventarkapazität, ungültige Referenzen oder Wiederholungsversuche dürfen keine Duplikate oder stillen Verluste verursachen. Falls direkte Zustellung nicht möglich ist, wird ein nachvollziehbarer Abholweg verwendet.

## 25.12 Player Quest State und Savegames

Questdefinition und individueller Fortschritt sind getrennt. Der Spielstand speichert:
- Status und Zeitpunkte;
- Quest-Run-ID und Wiederholungsstatus;
- Objective- und Gruppenfortschritt;
- Entscheidungen;
- Belohnungsnachweise;
- ausgeführte World Actions;
- Dialog-/Wissensfortschritt, soweit relevant;
- Zeitlimits und Cooldowns;
- verwendete Definitionsversion und Migrationshistorie.

Speichern ist jederzeit möglich. Nach Laden darf kein Objective doppelt zählen und keine Konsequenz erneut ausgeführt werden. Laufende Dialoge werden an einem sicheren Knoten fortgesetzt oder kontrolliert beendet. Definition-Updates dürfen aktive Spielstände nicht unbemerkt semantisch verändern.

## 25.13 Eventverarbeitung und Sicherheit

Events besitzen Event-ID, Typ, Quelle, Weltzeit, Spielzeit, Kontext und Schema-Version. Verarbeitung ist deterministisch und idempotent. Gleichzeitige Events erhalten eine stabile Sortierregel; fachlich abhängige Vorgänge werden explizit geordnet.

Die Runtime benötigt Deduplizierung, Retry-Regeln, Fehlerdiagnose, Transaktionsgrenzen, Schutz vor Event-Schleifen und Korrelation zwischen Event, Objective, Reward und World Action.

Questdefinitionen enthalten keinen beliebigen C#-Code, Datei- oder Netzwerkzugriff und keine Reflection-Aufrufe. Erweiterungen erfolgen über versionierte, freigegebene Condition-/Action-Provider.

## 25.14 Quest Editor

Der Quest Editor ist ein vollständiges Fachwerkzeug:
- Quest-/Questlinien-Browser;
- visuelle Quest- und Objective-Graphen;
- Condition Builder;
- Decision-/Consequence-Editor;
- Dialoggraph und Lokalisierung;
- Knowledge-Verwaltung;
- World-Action- und Reward-Referenzen;
- NPC-, Fraktions-, Orts-, Item- und Regionsbrowser;
- Ablaufvorschau und Pfadprüfung;
- Simulation mit kontrolliertem Spieler-/Weltzustand;
- Live-Debugger mit Eventverlauf und Condition-Ergebnissen;
- Schema-/Referenzvalidierung;
- Versionsvergleich, Änderungsprotokoll, Import/Export und Migration.

Der Editor meldet doppelte IDs, verwaiste Referenzen, Zyklen, unerreichbare Knoten, nicht erfüllbare Bedingungen, Softlocks und nicht abgedeckte Endzustände.

## 25.15 Journal und Spielerführung

Das Journal zeigt verständliche Ziele und Hinweise, nicht interne Datenstrukturen. Es unterscheidet Hauptziele, optionale Ziele, bekannte Hinweise und getroffene Entscheidungen. Es verrät keine Informationen, die der Spieler noch nicht kennt.

Kartenmarker sind kontextabhängig. Ermittlungs- und Wissensquests können Hinweise statt exakter Wegpunkte verwenden. Der Spieler muss erkennen können, was bekannt, vermutet oder noch ungeklärt ist.

## 25.16 Narrative Leitplanken

Quests erschließen die Welt und ihre Bewohner, statt nur Aufgabenlisten zu liefern. Hauptgeschichte, persönliche Geschichten, Fraktionen, Erkundung, Handwerk und Alltag greifen ineinander.

Vaelith ist Begleiter und eigenständige Figur, aber kein allwissender Questnavigator. Er darf irren, zögern, widersprechen und aus früheren Fehlern lernen. Hinweise geben Orientierung, lösen aber nicht jede Unsicherheit auf. Vaelith trifft keine Spielerentscheidungen und macht deren Folgen nicht automatisch rückgängig.

Alternative Wege über Diplomatie, Wissen, Erkundung, Handel, Handwerk, Kampf oder Unterstützung sind zu ermöglichen, wenn die Situation sie plausibel trägt.

## 25.17 Multiplayer-Abgrenzung

Die Datenverträge sollen später serverautoritativ betreibbar sein. Daraus folgt keine Multiplayer-Freigabe. Der aktuelle Produktumfang bleibt Singleplayer-first. Gruppenfortschritt, Questbesitz, Synchronisierung und Konfliktauflösung werden erst nach ausdrücklicher Produktentscheidung spezifiziert.

## 25.18 Abnahmekriterien

Mindestens zu testen sind:
- lineare und verzweigte Quests;
- AND/OR/SEQUENCE und verschachtelte NOT-Bedingungen;
- optionale Objectives und alternative Lösungen;
- Itemprüfung ohne Verbrauch und atomarer Verbrauch;
- Freischaltung über Queststatus, Wissen und World State;
- Entscheidungen mit sofortigen und verzögerten Folgen;
- Dialogoptionen mit Wissens-/Beziehungsbedingungen;
- NPC-Zustandswechsel während aktiver Quest;
- Fortschritt aus Kampf, Crafting, Handel, Bau, Zucht und Erkundung;
- Speichern/Laden in jedem Lifecycle-Status;
- doppelte Events und Reward-Anforderungen;
- Fehler in mehrteiligen World Actions;
- Wiederholung mit Cooldown und Run-Historie;
- Migration älterer Definitionen und Spielstände;
- fehlende Referenzen und ungültige Graphen;
- Fortschritt bei NPCs/Regionen in Fernsimulation.

## 25.19 Quellenstatus und verbleibende Arbeit

Die Quelle questsystem/expansion_questsystem.md fordert Questline-ID, verschachtelte Bedingungen, Objective-Gruppen, Entscheidungen, einheitliche Rewards, zentrale World Changes, World State, Knowledge, Dialogauslagerung, Quest Runtime, Lifecycle, Player Quest State und Schema-Validierung.

Dieses Dokument konkretisiert die Zielarchitektur für Vaelith. Es behauptet ausdrücklich nicht, dass das ursprüngliche Quest-System bereits fertig entwickelt war. Bestehende Quest-IDs, Objective-IDs, Übersetzungen, Belohnungsdaten und World-Change-Referenzen sind bei der Migration soweit möglich zu erhalten.

Noch zu erstellen sind konkrete Datenverträge, vollständige Beispielquests, Migrationsadapter und Editor-Workflows. Diese Aufgaben werden in der MDP geplant.


## 25.20 Abgleich mit dem vorhandenen Quest-Beispiel

Die Datei questsystem/questbeispiele/ew_act1_silent_bell.json ist ein konkretes Beispiel für den Entwicklungsstand des Quest Schema v2.2.0. Sie enthält bereits Questline, Lifecycle-Metadaten, verschachtelte Freischaltbedingungen, Objective-Gruppen mit ALL/ANY, Objective-Abhängigkeiten, Knowledge-Bedingungen, Entscheidungen, bedingte Belohnungen, World-Change-Referenzen, Failure Conditions, Visibility und Editor-Metadaten.

Das Beispiel bestätigt, dass diese Bereiche nicht nur abstrakte Ideen waren, sondern bereits in einem konkreten Datenentwurf zusammengeführt wurden. Es ist dennoch kein Beleg für ein vollständiges, validiertes oder implementiertes Quest-System. Die Beispielquest enthält Referenzen und Begriffe, deren Zielsysteme und Schemas separat zu prüfen sind.

Bei der Migration sind insbesondere folgende Beobachtungen zu berücksichtigen:
- Die Beispielquest verwendet Conditions als all-Listen. Vaelith soll diese Struktur in einen einheitlichen typisierten Ausdrucksbaum überführen, der ALL/ANY/NOT eindeutig ausdrücken kann.
- Objective-Gruppen und einzelne Objective-Abhängigkeiten existieren parallel. Der Validator muss sicherstellen, dass daraus keine widersprüchlichen oder zyklischen Abhängigkeiten entstehen.
- Entscheidungen schreiben World State, NPC-Beziehungen, Reputation, Knowledge und Questfreischaltungen. Diese Effekte müssen als zentrale, idempotente World Actions ausgeführt werden.
- Rewards enthalten Grundbelohnungen, bedingte Belohnungen und Objective-nahe Belohnungen. Vaelith muss genau definieren, wann diese vergeben werden und wie Mehrfachvergabe verhindert wird.
- Die Beispielquest führt eine Failure Condition über den Zustand eines Ortes. Die Vaelith-Designregel bleibt: Scheitern ist nur zulässig, wenn es ausdrücklich und für den Spieler nachvollziehbar vorgesehen ist.
- Das Feld abandonable ist in der Beispielquest true. Für Vaelith wird die Aufgebbarkeit nicht ungeprüft übernommen; Hauptstory-Quests sind standardmäßig nicht aufgebbar.
- Die Beispielquest nutzt mehrsprachige Felder direkt in der Definition. Vaelith darf diese Inhalte übernehmen, soll aber langfristig ein einheitliches Lokalisierungsmodell verwenden, statt pro Textfeld uneinheitliche Sprachvarianten zu pflegen.

Die Beispielquest dient als Migrations- und Testfall, nicht als endgültige Referenz für alle Vaelith-Regeln.
