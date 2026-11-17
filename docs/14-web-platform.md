# 14 — Webplattform und Administration

## 14.1 Produktziel

Vaelith erhält eine professionelle Webpräsenz und einen Administrations-/Kontrollbereich. Die Website soll das Spiel angemessen präsentieren und nicht wie ein generisches, unverändertes Template wirken. Der visuelle Anspruch muss eigenständig, konsistent und hochwertig sein.

## 14.2 Spielstart und Hauptmenü

**Festgehaltene Vorgabe:** Das Spiel startet nicht automatisch beim Öffnen der Website oder eines Launchers. Der Spieler entscheidet bewusst, wann er das Spiel startet. Nach dieser Entscheidung landet er direkt im Hauptmenü des Spiels.

Webpräsenz und Spielstart sind deshalb klar zu trennen. Eine Website darf informieren, verwalten oder einen Startvorgang anbieten, aber nicht ungefragt in das Spiel bzw. eine laufende Spielsitzung springen.

## 14.3 Gemeinsames Designsystem

Website und Admin-/Kontrollbereich verwenden abgestimmte Stylesheets, Design-Tokens, Komponenten und genehmigte Assets. Der Adminbereich besitzt eine eigene Informationsarchitektur und aufgabenorientierte Navigation, nutzt aber dieselbe visuelle Grundlage.

Gemeinsam zu pflegen sind:
- Farben, Typografie, Abstände und Raster;
- Komponenten und Interaktionszustände;
- Formulare, Tabellen, Meldungen und Navigation;
- responsive Layoutregeln;
- Icon- und Bildsprache;
- Accessibility-Standards.

## 14.4 Website

Die Website soll klare Informationsbereiche, Neuigkeiten, Spielinformationen, Medien, ggf. Community-/Supportzugänge und einen nachvollziehbaren Einstieg bieten. Konkrete Seitenstruktur und Texte werden in einem gesonderten Web-Work-Package definiert.

## 14.5 Admin-/Kontrollbereich

Der Adminbereich muss sich an realen administrativen Aufgaben orientieren. Berechtigungen, Auditierbarkeit, Datenvalidierung, Schutz vor unbefugten Änderungen und klare Trennung von öffentlicher Website und internen Funktionen sind zwingend.

Mögliche Funktionsbereiche sind Content-/Assetverwaltung, News, Accounts/Rollen, Konfiguration, Support/Moderation oder Projektverwaltung, sofern diese tatsächlich Teil des Produktumfangs werden. Diese Liste ist keine automatische Freigabe aller Funktionen.

## 14.6 Integration und Sicherheit

Weboberfläche, Backend und Spielkommunikation benötigen definierte APIs, Authentifizierung, Autorisierung, Rate Limits, Validierung, Auditlogs und sichere Geheimnisverwaltung. Das Spiel darf keine privilegierten Backend-Geheimnisse enthalten. Interne Adminfunktionen dürfen nicht nur durch versteckte URLs geschützt sein.

## 14.7 Trennung von Spiel und Web

Kritische Gameplayzustände dürfen nicht allein von der Verfügbarkeit der Website abhängen, sofern dies nicht ausdrücklich Teil eines später beschlossenen Onlinekonzepts wird. Das Offline-/Onlineverhalten und die Frage einer zwingenden Serververbindung sind offen.

## 14.8 Bestehende Webdesign-Absprachen

Die frühere Unterhaltung „Webdesign für Vaelith“ ist eine relevante Originalquelle und muss bei der konkreten Umsetzung erneut vollständig berücksichtigt werden. Diese Zusammenfassung hält die ausdrücklich bekannten Kernvorgaben fest, ersetzt aber nicht die vollständige Seiten-/Funktionsplanung aus dem Originalchat.


## 14.9 Informationsarchitektur und Nutzerwege

Website, Administrationsbereich und Spielclient sind getrennte Nutzungskontexte. Die Website richtet sich an Besucher und Spieler; der Adminbereich an berechtigte Betreiber und Redakteure; der Spielclient an Personen, die tatsächlich spielen möchten. Gemeinsame Komponenten dürfen diese unterschiedlichen Aufgaben nicht in eine einheitliche, unübersichtliche Navigation zwingen.

Jeder Bereich benötigt klar definierte Einstiegsseiten, Hauptaufgaben, Navigationshierarchie, Fehlerzustände und Rückwege. Die konkrete Seitenliste wird in einem eigenen freigegebenen Web-Arbeitspaket erstellt und anhand der vorhandenen Webdesign-Absprachen abgeglichen.

## 14.10 Expliziter Startvorgang

Der Start des Spiels ist eine bewusste Aktion des Spielers. Ein möglicher Launcher oder eine Website darf den Start anbieten und den notwendigen technischen Startvorgang auslösen, aber nicht ungefragt starten. Nach erfolgreichem Start wird das Spiel-Hauptmenü angezeigt; ein automatischer Sprung in eine laufende Spielwelt ist nicht Teil dieser Vorgabe.

Startfehler, fehlende Updates, beschädigte Dateien oder nicht erfüllte Systemvoraussetzungen benötigen verständliche Rückmeldungen und einen sicheren Abbruch- bzw. Wiederholungsweg. Die konkrete Launcher-Architektur ist noch nicht festgelegt.

## 14.11 Gemeinsame Designressourcen und getrennte Zuständigkeit

Design-Tokens, freigegebene Bild-/Iconressourcen, Typografie, Komponentenregeln und Accessibility-Vorgaben werden zentral versioniert. Website und Adminbereich dürfen daraus eigene Layouts und Navigationsmuster ableiten. Gemeinsame Stylesheets dürfen nicht dazu führen, dass administrative Tabellen, Formulare oder komplexe Arbeitsabläufe lediglich wie öffentliche Marketingseiten gestaltet werden.

Änderungen an zentralen Tokens oder Komponenten müssen auf beiden Oberflächen geprüft werden. Komponenten benötigen dokumentierte Zustände für Laden, Erfolg, Fehler, leere Ergebnisse, deaktivierte Aktionen und Berechtigungsverweigerung.

## 14.12 Konten, Rollen und administrative Aktionen

Falls Konten und Onlinefunktionen Teil des freigegebenen Produktumfangs sind, müssen Identität, Anmeldung, Sitzungsverwaltung, Rollen und Berechtigungen serverseitig abgesichert werden. Rollen werden nach konkreten Aufgaben und minimal erforderlichen Rechten definiert. Kritische Aktionen benötigen nachvollziehbare Audit-Einträge mit handelnder Identität, Zeitpunkt, Zielobjekt und Ergebnis.

Administratoren dürfen Sicherheitsgrenzen nicht durch reine UI-Ausblendung umgehen können. Jede privilegierte Aktion wird serverseitig autorisiert und validiert. Konten- und Backendumfang bleiben von der noch offenen Online-/Offline-Produktentscheidung abhängig.

## 14.13 Content-Veröffentlichung und Datenpflege

Redaktionelle Inhalte benötigen einen nachvollziehbaren Lebenszyklus aus Entwurf, Prüfung, Freigabe, Veröffentlichung und gegebenenfalls Rücknahme. Veröffentlichte Inhalte sollen versioniert und bei Bedarf auf einen vorherigen freigegebenen Stand zurücksetzbar sein.

Spielrelevante Daten dürfen nicht durch unkontrollierte Website- oder Adminänderungen an Validierung, Mod-Kompatibilität oder Spielstandintegrität vorbeigeschleust werden. Content-Publishing muss Schema-, Referenz- und Berechtigungsprüfungen verwenden und Änderungen protokollieren.

## 14.14 Schnittstellen und Betriebsfähigkeit

APIs benötigen dokumentierte Verträge, Versionsregeln, Eingabevalidierung, Fehlerformate, Rate Limits und Überwachung. Geheimnisse gehören in sichere serverseitige Konfiguration und niemals in öffentliche Webdateien oder den Spielclient. Entwicklungs-, Test- und Produktionsumgebungen müssen getrennt sein.

Backups, Wiederherstellung, Protokollierung, Ausfallverhalten und Datenschutz werden für jeden tatsächlich beschlossenen Backenddienst festgelegt. Nicht benötigte Dienste sollen nicht allein aus technischer Möglichkeit heraus eingeführt werden.

## 14.15 Barrierefreiheit, Responsive Design und Qualität

Die Oberflächen sind auf unterschiedlichen Bildschirmgrößen und Eingabemethoden zu prüfen. Tastaturbedienbarkeit, sichtbarer Fokus, ausreichende Kontraste, verständliche Fehlermeldungen, semantische Struktur und sinnvolle Zoom-/Skalierungsverhalten gehören zur Qualitätsprüfung.

Visuelle Abnahme umfasst reale Browserdarstellung und relevante responsive Zustände, nicht nur statische Mockups. Funktionale Abnahme umfasst Navigation, Formulare, Berechtigungen, Fehlerfälle und sichere Veröffentlichung.

## 14.16 Offene Entscheidungen

Die offenen Webentscheidungen WEB-001 bis WEB-010 sind in Dokument 20 registriert. Insbesondere werden Hosting, Authentifizierung, Konten, Launcher, Onlinepflicht und konkrete Adminmodule nicht vorweggenommen.
