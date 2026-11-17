# 01 — Projektüberblick

## 1.1 Produktvision

**Vaelith** ist ein umfangreiches, vollständig dreidimensionales Abenteuer-Rollenspiel mit Action-RPG-Elementen und einer persistenten, dynamischen Welt. Es verbindet Erkundung, Kampf, Charakterentwicklung, Magie, Quests, Beziehungen, Wirtschaft, Herstellung, Kreaturenhaltung und -zucht, Siedlungs- und Schlossbau sowie den Ausbau und Betrieb von Dungeons.

Der Spieler soll die Welt nicht nur als Kulisse erleben. Sie besitzt eigene Regionen, Ökosysteme, Bewohner, Produktionsketten, Interessen und Ereignisse. Systeme wirken auch dann weiter, wenn der Spieler sie gerade nicht beobachtet; die Simulationstiefe wird jedoch nach Relevanz und Entfernung gestaffelt, damit die Weltgröße technisch beherrschbar bleibt.

Die Spielerrolle entwickelt sich erzählerisch und mechanisch: vom Menschen bzw. Wesen, das seine Herkunft entdeckt, über einen Bewohner und Gestalter der Welt bis hin zu einer Person, die Verantwortung für die Folgen ihrer Macht übernehmen muss.

## 1.2 Genre und Spielerlebnis

- Primär: 3D-Abenteuer-RPG.
- Kampf und Charakterentwicklung: Action-RPG.
- Ergänzend: Weltgestaltung, Siedlungs-/Schlossbau, Dungeon-Management, Kreaturen- und Tierhaltung, Wirtschaft und Simulation.
- Erzählton: geheimnisvoll, atmosphärisch, mit langfristigen Enthüllungen und nachvollziehbaren Konsequenzen.
- Setting: Science-Fantasy bzw. futuristisch geprägte Welt mit magischen und mystischen Elementen ist die derzeitige Arbeitsrichtung. Sie ist noch nicht als unveränderliche Endentscheidung zu behandeln.

Diese zusätzlichen Spielsysteme dürfen nicht wie voneinander getrennte Minispiele wirken. Sie müssen über gemeinsame Weltzustände, Bewohner, Kreaturen, Ressourcen, Quests und Produktionsketten miteinander verbunden sein.

## 1.3 Kernpfeiler

1. **Erkundung:** Eine große Welt mit unterschiedlichen Landschaften, Biomen, Orten, Ruinen, Höhlen, Dungeons, Geheimnissen und Gefahren.
2. **Lebendige Welt:** NPCs, Fraktionen, Siedlungen, Tiere, Kreaturen, Wirtschaft und Ereignisse besitzen nachvollziehbare Zustände und Bedürfnisse.
3. **RPG-Fortschritt:** Fähigkeiten, Ausrüstung, Beziehungen, Entscheidungen und erzählerische Entwicklung.
4. **Magie und Verantwortung:** Macht eröffnet Möglichkeiten, aber jede relevante Handlung kann Konsequenzen haben.
5. **Weltgestaltung:** Schloss- und Dorf-/Siedlungsbau werden schrittweise durch die Geschichte erschlossen.
6. **Dungeon-Betrieb:** Befreite Dungeons können zu ausgebauten, produktiven und verteidigbaren Einrichtungen werden.
7. **Lebewesen als Systeme:** Tiere und Kreaturen besitzen individuelle Attribute, Bedürfnisse, Verhalten, Beziehungen und vererbbare Merkmale.
8. **Werkzeugqualität:** Die interne Editor-Suite muss die tatsächlichen Produktionsabläufe vollständig unterstützen und darf nicht aus bloßen UI-Platzhaltern bestehen.
9. **Erweiterbarkeit:** Modding wird von Beginn an architektonisch berücksichtigt, ohne dass das Grundspiel Mods benötigt.

## 1.4 Spielerlebnis in Phasen

Die folgende Gliederung ist eine dramaturgische Leitlinie, keine endgültige Kapitel- oder Questliste:

- **Entdecken:** Der Spieler erfährt etwas über seine Herkunft, die Welt und die Kräfte, die sein Leben beeinflussen.
- **Lernen und bestehen:** Er erkundet, kämpft, baut Beziehungen auf, erlernt Systeme und übernimmt Verantwortung für sein unmittelbares Umfeld.
- **Gestalten:** Neue Möglichkeiten zur Nutzung von Magie, zum Ausbau von Dungeons und zur Gestaltung von Siedlung und Schloss werden erschlossen.
- **Verantwortung übernehmen:** Entscheidungen wirken zunehmend über den persönlichen Bereich hinaus und beeinflussen Bewohner, Regionen und Weltzustände.

## 1.5 Qualitätsziel

Vaelith soll als hochwertiges 3D-Spiel erscheinen. Die technische Umsetzung muss visuelle Qualität, Spielgefühl, Zuverlässigkeit, Performance und spätere Erweiterbarkeit gemeinsam betrachten. Ein beeindruckender Einzelbereich ist kein Erfolg, wenn Streaming, Simulation, Speichern oder Datenpflege nicht zuverlässig funktionieren.

## 1.6 Plattformen und technische Zielplattform

**Offen:** Zielplattformen, Mindesthardware, Controller-/Eingabematrix, Store-Ziele und konkrete Release-Pläne sind noch festzulegen. Diese Entscheidung ist früh genug zu treffen, damit Renderpipeline, Scripting Backend, Modding und Assetbudgets nicht auf inkompatiblen Annahmen basieren.

## 1.7 Umfang und Nicht-Ziele

- Die Welt ist in ihrer geografischen Gesamtstruktur von Anfang an geplant; nicht alle Regionen werden von Anfang an vollständig generiert oder spielbar ausgeliefert.
- Die Entwicklung ist modular und inkrementell; große Systeme werden in integrierbaren Arbeitspaketen aufgebaut.
- Es wird kein zweites, unabhängiges Mod-Loader-System parallel zu BepInEx entwickelt, sofern die Plattformprüfung dessen Einsatz bestätigt.
- Es wird keine technische oder inhaltliche Abhängigkeit von ASHFALL übernommen.
- Die Dokumentation soll keine ungeprüften Zahlen zu Weltgröße, Chunkgröße, Spielerzahl, Downloadgröße oder Mindestanforderungen als feste Spezifikation ausgeben.
