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
