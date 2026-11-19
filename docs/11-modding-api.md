# 11 — Modding und Vaelith Mod API

## 11.1 Grundsatz

Modding wird von Projektbeginn an in Architektur und Datenmodell berücksichtigt. Das Grundspiel muss vollständig ohne Mods funktionieren. Es soll kein separates, konkurrierendes Mod-Loader-System gebaut werden, wenn BepInEx die jeweilige Verantwortung bereits abdeckt.

## 11.2 Grundlage

**Vorgesehene Basis:** BepInEx als etablierte Mod-Loader-Grundlage. Darauf wird eine offizielle **Vaelith Mod API in C#** entwickelt.

Die Kompatibilität mit Unity-Version, Scripting Backend, Mono-/IL2CPP-Umgebung und Zielplattform muss früh praktisch verifiziert werden. Es darf nicht ungeprüft angenommen werden, dass BepInEx auf allen Builds und Plattformen identisch funktioniert.

## 11.3 Mod-Kategorien

### Datenmods
Datenmods verändern oder ergänzen definierte Contentdaten, z. B. Items, Rezepte, Kreaturen, Quests, NPC-Profile oder andere freigegebene Inhalte. Sie sollen ohne frei ausführbaren C#-Code möglich sein und strenge Schema-/Referenzvalidierung durchlaufen.

### Plugin-/Code-Mods
Plugin-Mods verwenden C# und die offizielle API, um freigegebene Funktionen, UI, Anzeigen, Rendering-Erweiterungen, Spielmechaniken und Integrationen zu erweitern. Sie laufen im Prozess des Spiels und benötigen deshalb eine klare Vertrauens- und Sicherheitskennzeichnung.

## 11.4 Bidirektionale API

Die API muss in kontrollierter Form Informationen aus dem Spiel veröffentlichen und Mod-Erweiterungen entgegennehmen.

**Spiel → Mod:**
- definierte Daten zu Items, Quests, NPCs, Kreaturen und Weltzuständen;
- Ereignisse und freigegebene Zustandsänderungen;
- definierte Abfragen und Kontextinformationen;
- kontrollierte UI-/Interaktionshooks.

**Mod → Spiel:**
- Registrierung neuer Daten/Contenttypen, sofern unterstützt;
- Abfrage freigegebener Spielinformationen;
- Erweiterung definierter Funktionen und Ereignisse;
- Registrierung von UI-, Anzeige-, Rendering- oder Gameplay-Erweiterungen;
- Anforderung zulässiger Änderungen über geprüfte Schnittstellen.

Die API exponiert nicht pauschal interne Implementierungen. Verträge, Berechtigungen und stabile Erweiterungspunkte sind zu dokumentieren.

## 11.5 API-Verträge

Jede API-Funktion benötigt:
- eindeutige ID/Signatur und Dokumentation;
- Version und Kompatibilitätsregel;
- erforderliche Berechtigung;
- Eingabe-/Ausgabevalidierung;
- Fehler- und Timeoutverhalten;
- Event-/Lifecycle-Regeln;
- Auswirkungen auf Speicherstände;
- Performance- und Threadinghinweise;
- Testfälle und Beispielmod.

## 11.6 Sicherheit und Vertrauensmodell

Wichtig: Ein BepInEx-C#-Plugin läuft im Spielprozess und kann grundsätzlich weitreichende Rechte besitzen. Eine offizielle API macht beliebigen Plugin-Code nicht automatisch sandboxfähig.

Daher:
- Datenmods und Code-Mods klar unterscheiden;
- Code-Mods als ausführbaren, potenziell privilegierten Code behandeln;
- vertrauenswürdige Quellen, Signaturen/Hashes und Warnungen prüfen;
- sichere Datenvalidierung und Fehlerisolation auf API-Ebene;
- dokumentieren, dass ein Plugin außerhalb der API liegende Prozesszugriffe nicht zuverlässig durch die API allein verhindert bekommt;
- keine falschen Sicherheitsversprechen geben.

## 11.7 Kompatibilität und Konflikte

Mod-Metadaten sollen Mod-ID, Version, API-Minimum/-Maximum, Spielversion, Abhängigkeiten, optionale Abhängigkeiten, Konflikte, Ladepriorität und Herkunft enthalten. Konflikte müssen sichtbar sein; Ladefehler dürfen nicht unbemerkt den Spielstand beschädigen.

## 11.8 SDK und Entwicklererlebnis

Vorgesehen sind:
- API-Referenz;
- SDK-/Template-Projekte;
- Beispielmods;
- Datenmod-Schema und Validierung;
- Build-/Testanleitungen;
- Versions- und Deprecation-Politik;
- Diagnose-/Logmeldungen;
- Kompatibilitätsmatrix;
- Hinweise zu Savegame- und Performanceauswirkungen.

## 11.9 Testmatrix

Zu prüfen sind API-Verträge, Berechtigungen, Datenvalidierung, fehlerhafte Mods, Konflikte, Abhängigkeiten, Versionswechsel, Savegame-Verhalten, Lade-/Entladefehler, Laufzeitperformance und Spielbarkeit ohne Mods. Plattformen ohne verlässliche Code-Mod-Unterstützung müssen transparent ausgewiesen werden.

## 11.10 API-Schichten und Erweiterungspunkte

Die Vaelith Mod API soll fachlich stabile Verträge anbieten, statt interne Unity-Komponenten oder private Implementierungsdetails offenzulegen. Erweiterungspunkte sind nach Verantwortungsbereich zu gruppieren, beispielsweise Contentregistrierung, Datenabfragen, Gameplayereignisse, UI, Darstellung und definierte Gameplay-Erweiterungen.

Für jeden Erweiterungspunkt ist festzulegen:
- ob er lesend, registrierend oder zustandsverändernd ist;
- welche Daten und Aktionen zugänglich sind;
- welche Validierungen und Berechtigungen gelten;
- in welchem Lebenszykluszeitpunkt er verfügbar ist;
- welche Kompatibilitätsgarantien gelten;
- welche Auswirkungen auf Multiplayer-/Save-/Performancekonzepte entstehen, falls diese später relevant werden.

Mods dürfen keine stillschweigende Abhängigkeit von internen Klassen oder Szenenobjekten benötigen.

## 11.11 Contentregistrierung und Datenvalidierung

Datenmods benötigen ein dokumentiertes Paketformat und versionierte Schemas. Registrierungen müssen stabile Mod- und Content-IDs verwenden und Kollisionen mit Grundspiel- oder anderen Mod-IDs erkennen.

Der Ladevorgang umfasst:
- Metadaten- und Versionsprüfung;
- Abhängigkeitsauflösung;
- Schema- und Wertevalidierung;
- Referenzprüfung;
- Konflikterkennung und definierte Prioritätsregeln;
- verständlichen Fehlerbericht;
- kontrollierte Aktivierung oder Zurückweisung des Pakets.

Ungültiger Content darf nicht teilweise und unbemerkt in den aktiven Weltzustand gelangen. Datenmods müssen ohne ausführbaren Plugin-Code nutzbar bleiben.

## 11.12 Mod-Lebenszyklus und Fehlerisolation

Für Plugins sind Lade-, Initialisierungs-, Aktivierungs-, Deaktivierungs- und Shutdown-Phasen zu definieren. Die API soll Fehler pro Erweiterung erkennen und protokollieren. Wo sicher möglich, kann eine fehlerhafte Erweiterung deaktiviert werden; es darf jedoch keine vollständige Prozessisolation behauptet werden.

Ein Modfehler darf nicht unbemerkt Kernzustände beschädigen. Änderungen an persistenten Daten benötigen geprüfte Schnittstellen, Validierung und nachvollziehbare Ausführung. Die Grenzen der Fehlerisolation bei In-Process-Code sind ausdrücklich zu dokumentieren.

## 11.13 Savegames und Mod-Abhängigkeiten

Spielstände müssen erkennen können, welche Mods und Contentversionen für ihren Zustand relevant sind. Beim Laden sind fehlende, inkompatible oder geänderte Mods sichtbar zu machen.

Zu spezifizieren sind:
- Modliste und Versionen im Savegame;
- erforderliche und optionale Abhängigkeiten;
- Verhalten bei fehlendem Mod;
- Umgang mit entfernten oder umbenannten Content-IDs;
- Migrations- und Wiederherstellungsoptionen;
- Warnung vor potenziell verlustbehaftetem Laden.

Das Spiel darf fehlende Modinhalte nicht stillschweigend durch beliebige Ersatzdaten ersetzen. Sichere Lesbarkeit, Wiederherstellung und klare Nutzerentscheidung haben Vorrang.

## 11.14 Mod-Manager und Diagnose

Ein Mod-Manager soll installierte Pakete, Typ, Version, Herkunft, Abhängigkeiten, Konflikte und Vertrauenshinweise darstellen. Er muss Ladeprobleme verständlich erklären und Diagnoseinformationen exportierbar machen, ohne Geheimnisse oder unnötige persönliche Daten offenzulegen.

Ladeprioritäten dürfen nicht als Ersatz für eine echte Konfliktlösung dienen. Bei unauflösbaren Konflikten muss der Manager die betroffenen Mods und Ursache benennen.

## 11.15 SDK, Beispiele und API-Qualität

Das SDK muss mit der veröffentlichten API-Version übereinstimmen. Beispiele sind als ausführbare Referenzprojekte zu pflegen und bei API-Änderungen mitzutesten.

Vor einer API-Freigabe sind mindestens erforderlich:
- API-Referenz und Änderungsprotokoll;
- funktionierendes Minimalbeispiel;
- Beispiel für Contentregistrierung;
- Beispiel für Ereignisabonnement und -bereinigung;
- Beispiel für erlaubte Zustandsänderung;
- Fehler-/Konfliktdiagnose;
- Kompatibilitäts- und Migrationshinweise.

## 11.16 Versionierung und Deprecation

Die API benötigt eine nachvollziehbare Versionierungsstrategie. Breaking Changes müssen angekündigt, dokumentiert und – soweit realistisch – über eine Übergangsphase unterstützt werden.

Zu jeder Änderung gehören betroffene Verträge, Migrationshinweise, Kompatibilität mit Spiel- und SDK-Versionen sowie Tests. Interne Refactorings ohne Änderung des öffentlichen Vertrags sollen Mods möglichst nicht brechen.

## 11.17 Plattformkompatibilität und Releasefreigabe

Code-Mod-Unterstützung wird pro Plattform, Unity-Version und Scripting Backend explizit ausgewiesen. BepInEx-Kompatibilität ist praktisch zu testen und darf nicht aus einer anderen Plattform abgeleitet werden.

Wenn eine Plattform keine verlässliche Code-Mod-Unterstützung ermöglicht, müssen Datenmods und andere unterstützte Erweiterungswege klar davon abgegrenzt werden. Das Grundspiel muss unabhängig davon vollständig spielbar bleiben.

## 11.18 Offene Modding-Entscheidungen

| ID | Thema | Status |
|---|---|---|
| MOD-001 | BepInEx-Version, Fork-/Patchbedarf und unterstützte Plattformen | Kompatibilitätstest erforderlich |
| MOD-002 | Mono-/IL2CPP- und sonstige Backendstrategie | Technische Prüfung erforderlich |
| MOD-003 | Öffentliche API-Schichten und genaue Erweiterungspunkte | API-Design erforderlich |
| MOD-004 | Datenmod-Paketformat und Schema-Versionierung | Technische Spezifikation erforderlich |
| MOD-005 | Mod-ID-/Content-ID-Namensraum und Kollisionsregeln | Entscheidung erforderlich |
| MOD-006 | Mod-Ladepriorität und Konfliktauflösung | Design/Prototyp erforderlich |
| MOD-007 | Savegame-Verhalten bei fehlenden oder geänderten Mods | Technische Spezifikation erforderlich |
| MOD-008 | Vertrauenshinweise, Signaturen und Herkunftsprüfung | Sicherheitsprüfung erforderlich |
| MOD-009 | Mod-Manager-Umfang und Diagnoseexport | Produkt-/UX-Entscheidung erforderlich |
| MOD-010 | API-Versionierung, Supportfenster und Deprecation | Governance-Entscheidung erforderlich |


## Native Spieler-Konfiguration, Gameplay-Profile und Mods

Nicht jede Anpassung der Spielerfahrung ist eine Mod. Das PECS-Arbeitskonzept trennt native Spieleinstellungen, speicherbare Gameplay-Profile, validierte Regel-/Daten-Erweiterungen und ausführbare Code-Mods.

Native Spielausrichtungen und Simulationspräferenzen müssen ohne externe Werkzeuge im Spiel zugänglich sein. Gameplay-Profile speichern gültige Kombinationen solcher Einstellungen. Daten-/Regel-Erweiterungen und Code-Mods verwenden weiterhin die hier definierten Paket-, API-, Vertrauens-, Abhängigkeits-, Konflikt- und Savegame-Regeln.

Die PECS-Schicht darf keine eigene Mod-Laufzeit oder zweite Datenwahrheit erzeugen. Sie koordiniert Präferenzen und Darstellung; die Mod API bleibt Eigentümerin des Erweiterungslebenszyklus. Siehe `26-player-experience-and-replayability.md`.
