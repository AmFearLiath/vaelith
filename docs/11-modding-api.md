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
