# Vaelith — Projekt- und Entwicklungsdokumentation

> **Stand:** 17. November 2026  
> **Status:** Konsolidierter Projektentwurf aus den verfügbaren gemeinsamen Projektgesprächen.  
> **Zielgruppe:** Projektleitung, Game Design, Unity-Entwicklung, Tools-/Content-Entwicklung, QA und Entwicklungsagenten.

Diese Dokumentation beschreibt Zielbild, Leitplanken, Spielsysteme, Weltgenerierung, Tooling, technische Architektur sowie den Entwicklungsprozess von **Vaelith**. Sie ist eine lebende Spezifikation. Als offen, vorgeschlagen oder illustrativ markierte Inhalte sind keine endgültig beschlossenen Entscheidungen.

## Inhaltsverzeichnis

1. [Projektüberblick](01-project-overview.md)
2. [Designprinzipien und Leitplanken](02-design-principles.md)
3. [Welt, Setting und Lore](03-world-and-lore.md)
4. [Spieler, Progression und Magie](04-player-progression-and-magic.md)
5. [Gameplay-Systeme](05-gameplay-systems.md)
6. [Lebendige Welt und Simulation](06-living-world-simulation.md)
7. [Prozedurale Weltgenerierung](07-world-generation.md)
8. [Editor- und Tool-Suite](08-editor-suite.md)
9. [Datenarchitektur und Persistenz](09-data-architecture.md)
10. [Unity-Architektur](10-unity-architecture.md)
11. [Modding und Vaelith Mod API](11-modding-api.md)
12. [Assets, Animation und Audio](12-assets-animation-audio.md)
13. [Wirtschaft, Items und Crafting](13-economy-items-crafting.md)
14. [Webplattform und Administration](14-web-platform.md)
15. [Monetarisierung](15-monetization.md)
16. [VAELITH Modular Development Pipeline](16-mdp-development-process.md)
17. [Roadmap und Arbeitspakete](17-roadmap.md)
18. [QA, Sicherheit und Performance](18-qa-security-performance.md)
19. [Agentenregeln](19-agent-operating-rules.md)
20. [Entscheidungsregister und offene Punkte](20-decisions-and-open-questions.md)
21. [Glossar](21-glossary.md)
22. [Asset-Credit- und Attribution-Register](22-asset-attribution-register.md)
23. [Originalkonzept- und Quellenregister](23-original-concept-source-register.md)
24. [Item-, Material- und Produktionsmigration](24-item-material-production-migration.md)
25. [Quest-System-Spezifikation und Migration](25-quest-system-specification.md)
26. [Player Experience, Simulation Profiles und Wiederentdeckbarkeit](26-player-experience-and-replayability.md)


## Statuskennzeichnung

- **Leitplanke:** Im Gespräch klar festgelegte Vorgabe.
- **Arbeitskonzept:** Ausgearbeitet, aber nicht ausdrücklich final bestätigt.
- **Vorschlag/Beispiel:** Veranschaulichung, keine verbindliche Entscheidung.
- **Offen:** Benötigt Entscheidung oder technische Prüfung.
- **Quellenlücke:** Originalunterlagen lagen bei der Erstellung nicht vor; Inhalte werden nicht als inventarisiert ausgegeben.

## Zentrale Projektthese

Der Spieler entdeckt eine lebendige Welt, entwickelt darin seine eigene Rolle, erlebt und gestaltet sie auf seine bevorzugte Weise und kann sie immer wieder neu entdecken. Die Welt und ihre Systeme bleiben zusammenhängend; die individuelle Spielerfahrung ist anpassbar.

## Konzept-Erweiterung

Dokument 26 beschreibt das neue Arbeitskonzept für individuelle Spielausrichtungen, spielersteuerbare Simulationstiefe, adaptive Funktionsdarstellung, Automatisierung, unabhängigen Questfortschritt und langfristige Wiederentdeckbarkeit. Es erweitert die bestehende Vision; es ersetzt sie nicht und ist noch keine pauschale Implementierungsfreigabe.

## Wichtige Quellenbegrenzung

Die am 17. November 2026 bereitgestellte documents.zip wurde eingelesen. Das Archiv enthält 325 Dateien, darunter 82 Markdown- und 240 JSON-Dateien sowie ein eingebettetes Items.zip. Alle 240 JSON-Dateien ließen sich syntaktisch parsen. Die fachliche Sichtung und Konsolidierung erfolgt systemweise und ist noch nicht abgeschlossen. Insbesondere sind Item-/Materialversionen und Referenzen noch nicht vollständig semantisch migriert; ursprüngliche Monetarisierungsdetails und frühere Einzelchats bleiben separate Quellenlücken. Dokument 23–25 führen Quellenstatus und Migrationsarbeit nach.

## Wichtige Arbeitsregel für Entwicklungsagenten

**Vaelith wird als eigenständiges, vollständig 3D-Spiel in Unity neu entwickelt.** Die Dokumentation beschreibt die Zielvision und die fachlichen Ausgangskonzepte. Sie ist keine pauschal verbindliche Liste sämtlicher zu implementierender Features.

Vor der Umsetzung ist zwischen verbindlichen Projektleitplanken, zu prüfenden Bestandskonzepten, Arbeitskonzepten, Funktionserweiterungen, unverbindlichen Vorschlägen/Beispielen und offenen Entscheidungen zu unterscheiden. Bestehende Emberwild-/Vaelith-Inhalte sind fachliche Quellen und mögliche Migrationsbestände; die alte technische Implementierung wird nicht automatisch fortgeführt. Maßgebliche Details stehen in `01-project-overview.md`, `02-design-principles.md`, `16-mdp-development-process.md` und `19-agent-operating-rules.md`.
