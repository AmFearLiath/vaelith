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
