# 12 — Assets, Animation und Audio

## 12.1 Assetstrategie

Vaelith benötigt Modelle, Icons, Materialien, Texturen, Umgebungen, Vegetation, Kreaturen, Gebäude, Animationen, VFX und Audio. Eine modulare Assetstrategie ist zu bevorzugen: Basismodelle, austauschbare Komponenten, Material-/Texturvarianten und unterschiedliche Darstellungsstufen sollen wiederverwendbar sein.

Die Verfügbarkeit geeigneter Assets darf die Weltästhetik informieren, aber nicht zufällig die gesamte Lore bestimmen.

## 12.2 Assetquellen und Lizenzen

Zu prüfende freie Quellen umfassen beispielsweise Poly Haven, ambientCG und Kenney sowie Quaternius. Sketchfab und andere Marktplätze sind pro Asset hinsichtlich Lizenz und Nutzungsrechten zu prüfen. Diese Aufzählung ist kein pauschaler Freibrief.

Für jedes integrierte Asset muss die Assetmatrix festhalten:
- Name, Typ, Autor und ursprüngliche Quelle;
- direkte Fundstelle und Abrufdatum;
- Lizenz und kommerzielle Nutzbarkeit;
- Namensnennungs-/Weitergabebedingungen;
- Originaldatei und vorgenommene Änderungen;
- Unity-/Pipeline-Kompatibilität;
- Qualitäts-/Performancebewertung;
- zugeordnete Spielinhalte;
- Integrations- und Teststatus.

Unklare oder nicht passende Lizenzen führen nicht zur Integration. Kostenpflichtige Assets benötigen ausdrückliche Freigabe.

## 12.3 Assetabdeckung

Die Abdeckung ist mindestens für folgende Kategorien zu erfassen:
- Waffen, Rüstungen, Schilde, Schmuck und Werkzeuge;
- Charaktere, Körper-/Rüstungskomponenten und Icons;
- Tiere, Begleiter und Kreaturen;
- Gebäude, Innenräume, modulare Bauteile und Dekorationen;
- Terrain, Felsen, Vegetation und Umgebungsobjekte;
- Materialien und Texturen;
- Animationen, Rigging und VFX;
- UI-Elemente, Audio und Musik.

Bestehende Itemlisten sind mit konkreten Assets, Varianten und offenen Lücken abzugleichen. Keine Itemkategorie darf allein deshalb entfallen, weil noch kein passendes Modell gefunden wurde.

## 12.4 Modell- und Materialprüfung

Prüfpunkte:
- Topologie, Polygonbudget und LOD;
- UV-Layouts und Texeldichte;
- Materialien, Texturformate und Shaderkompatibilität;
- Normalen/Tangenten;
- Rig/Skinned Mesh und Bone-Namen;
- Maßstab, Pivot und Orientierung;
- Collider und Interaktionspunkte;
- Lizenz/Quelle;
- Performance in repräsentativer Szene.

## 12.5 Animationen

Spieler, NPCs und Kreaturen benötigen glaubwürdige Bewegungen. Abdeckung muss je nach Charaktertyp mindestens relevante Zustände umfassen: Idle, Fortbewegung, Richtungswechsel, Übergänge, Interaktion, Kampf, Treffer, Ausweichen, Tod, soziale Handlungen, Arbeit, Schlaf/Ruhe, Fressen, Pflege und artspezifisches Verhalten.

Mögliche technische Mittel:
- gemeinsame oder retargetbare Rigs, wo geeignet;
- Animator State Machines und Blend Trees;
- IK für Füße, Hände und Interaktionen;
- Root Motion oder In-place nach Bewegungsanforderung;
- Motion Matching, wenn Umfang und Nutzen dies rechtfertigen;
- Animationsereignisse für Gameplay-Synchronisierung.

Bewegung, Kollisionskörper, Trefferzonen und Animation müssen zusammenpassen. Clipping, Fußgleiten, falsche Ausrichtung und nicht synchronisierte Gameplay-Events sind zu testen.

## 12.6 Kreaturen- und Artenspezifik

Nicht alle Kreaturen dürfen über dieselbe generische Animationssammlung dargestellt werden. Körperbau, Gangart, Größe, Fortbewegungsart und Sozialverhalten müssen passende Rigs und Bewegungsmuster erhalten. Wiederverwendung ist sinnvoll, wenn sie die Qualität nicht sichtbar reduziert.

## 12.7 UI- und Inventardarstellung

Items können eine eigene Inventar-/Icondarstellung und ein abweichendes 3D-Weltmodell besitzen. Seltene oder hochwertige Varianten können Material- oder Komponentenvarianten erhalten. Darstellung und Gameplaywerte bleiben getrennt.

## 12.8 Audio

Audio soll Welt, Kreaturen, Interaktion, Umgebung, Kampf und Atmosphäre unterstützen. Zu planen sind räumliche Audioquellen, Innen-/Außenwirkung, Distanzeffekte, Umgebungszonen, Zustandswechsel, Dialog, UI und VFX-Synchronisierung. Konkrete Musik-/Soundkonzepte und Lizenzinventar sind noch zu ergänzen.

## 12.9 Asset-Änderungen und Nachvollziehbarkeit

Originaldateien, Lizenznachweise und Bearbeitungsstände sind nachvollziehbar aufzubewahren. Assetupdates dürfen Referenzen oder Materialzuordnungen nicht stillschweigend brechen.

## 12.10 Assetpipeline und Importprofile

Für jede relevante Assetkategorie sind nachvollziehbare Importprofile zu definieren. Einheitliche Grundregeln sollen Maßstab, Achsen, Einheiten, Texturkompression, Materialkonventionen, Namensgebung und Metadaten festlegen. Kategorieabhängige Abweichungen bleiben möglich und müssen dokumentiert sein.

Die Pipeline soll Originaldatei, importierte Fassung und optimierte Laufzeitvariante unterscheidbar halten. Reimport darf manuelle Anpassungen oder Referenzen nicht unbeabsichtigt überschreiben.

## 12.11 Assetkatalog und Zuordnung zu Spielinhalten

Ein zentraler Assetkatalog verknüpft Assets mit fachlichen Datensätzen und Einsatzorten. Ein Item kann beispielsweise Inventaricon, Weltmodell, Ausrüstungsvariante, Materialvariante und Animation-/Effektreferenzen besitzen.

Zu verwalten sind:
- stabile Asset-ID und Dateireferenz;
- Assettyp und Kategorien/Tags;
- Quelle, Lizenz und Änderungsverlauf;
- technische Import-/Qualitätsdaten;
- zugeordnete Items, Kreaturen, Gebäude oder UI-Inhalte;
- Varianten, Abhängigkeiten und LODs;
- Integrations-, Validierungs- und Teststatus.

Fachliche Gameplaydaten bleiben von der visuellen Assetzuordnung getrennt. Fehlende Assets müssen auffindbar sein und dürfen nicht zum Verlust des zugrunde liegenden Items oder Inhalts führen.

## 12.12 Modularität und Variantenverwaltung

Modulare Modelle und Varianten benötigen klare Kompatibilitätsregeln. Komponenten dürfen nur kombiniert werden, wenn Maßstab, Anschlüsse, Rig, Materialslots und fachliche Zuordnung passen.

Varianten können Geometrie, Material, Textur, Farbe, Seltenheitsdarstellung oder funktionale Komponenten betreffen. Visuelle Varianten dürfen keine Gameplaywerte verändern, sofern eine explizite fachliche Datenreferenz dies nicht vorsieht.

## 12.13 LOD, Streaming und Speicherbudgets

Assets benötigen je nach Größe, Sichtweite und Nutzung geeignete Detailstufen und Streamingregeln. Zu prüfen sind Mesh-LOD, Texturauflösung, Mipmaps, Instancing, Occlusion und asynchrones Laden. Die Auswahl erfolgt anhand repräsentativer Szenen und Profiling.

Speicherbudgets müssen pro Assetgruppe und Szene/Region messbar sein. Übermäßige Materialvarianten, unnötige Duplikate und dauerhaft geladene nicht benötigte Assets sind zu vermeiden.

## 12.14 Animation-Runtime und Zustandsverträge

Animationen müssen mit Bewegungs-, Kampf-, Interaktions- und Kreaturenzuständen abgestimmt sein. Animation ist Darstellung und darf nicht alleinige Wahrheitsquelle für Gameplayzustände werden.

Zu definieren sind:
- Zustands- und Übergangsverträge;
- Synchronisierung von Treffer-, Interaktions- und Audioereignissen;
- Abbruch und Unterbrechung;
- Root-Motion-/In-Place-Verantwortung;
- Retargeting-Grenzen und Rig-Kompatibilität;
- Netzwerk-/Replay-Anforderungen nur, falls später beschlossen;
- Fallbacks bei fehlender oder fehlerhafter Animation.

## 12.15 Animation-QA und visuelle Abnahme

Jeder relevante Charakter- und Kreaturentyp benötigt repräsentative Prüfszenen. Zu prüfen sind Übergänge, Richtungswechsel, Geländeanpassung, Fußkontakt, Interaktionspunkte, Ausrüstung, Trefferzonen und Clipping.

Die Abnahme erfolgt in Bewegung und im tatsächlichen Gameplaykontext, nicht nur durch isolierte Vorschau einzelner Clips. Platzhalteranimationen sind sichtbar zu kennzeichnen.

## 12.16 Audioverwaltung und Laufzeitregeln

Audioinhalte benötigen Metadaten zu Typ, Quelle, Lizenz, Lautheits-/Formatvorgaben, räumlichem Verhalten und Einsatzkontext. Laufzeitregeln müssen Priorisierung, gleichzeitige Stimmen, Distanz, Innen-/Außenräume, Umgebungszonen und Übergänge berücksichtigen.

Audio darf bei häufigen Ereignissen nicht unkontrolliert vervielfacht werden. Kritische Gameplayhinweise benötigen klare Priorität und dürfen nicht ausschließlich akustisch vermittelt werden.

## 12.17 Asset- und Audio-Rechteprüfung

Lizenzinformationen müssen bis zur ausgelieferten Nutzung nachvollziehbar bleiben. Bei abgeleiteten oder bearbeiteten Assets sind die ursprünglichen Bedingungen weiter zu berücksichtigen. Nicht eindeutig geklärte Nutzungsrechte blockieren die Integration in Releasebuilds.

Für Musik, Sprachaufnahmen, Soundeffekte, Fonts und sonstige Drittinhalte gelten dieselben Nachweis- und Freigabeanforderungen wie für 3D-Assets.

## 12.18 Offene Asset-/Animations-/Audioentscheidungen

| ID | Thema | Status |
|---|---|---|
| ASSET-001 | Finale visuelle Stilrichtlinien und technische Qualitätsprofile | Art Direction erforderlich |
| ASSET-002 | Assetkatalog und stabile Asset-ID-Konvention | Daten-/Toolentscheidung erforderlich |
| ASSET-003 | Importprofile und unterstützte Austauschformate | Pipeline-Prototyp erforderlich |
| ASSET-004 | LOD- und Speicherbudgets je Assetkategorie | Profiling erforderlich |
| ASSET-005 | Modulare Charakter-/Ausrüstungs- und Kreaturenpipeline | Prototyp erforderlich |
| ASSET-006 | Rig-/Retargeting-Standards und Ausnahmen je Artengruppe | Animationstest erforderlich |
| ASSET-007 | Umfang und Lizenzierung von Musik, Sprache und Soundeffekten | Content-/Lizenzplanung erforderlich |
| ASSET-008 | Audio-Middleware oder Unity-Bordmittel | Prototyp/Anforderungsprüfung erforderlich |
| ASSET-009 | Asset-Streaming- und Addressables-Strategie | Technische Evaluierung erforderlich |
| ASSET-010 | Assetfreigabe und visuelle Qualitätsabnahme | Prozessentscheidung erforderlich |


## 12.19 Verbindliches Asset-Credit- und Attribution-Register

Vaelith führt ein zentrales, dauerhaft gepflegtes **Asset-Credit-Register** für alle externen Assets und sonstigen Drittinhalte. Das Register erfasst insbesondere alle Autoren und Urheber, deren Lizenz eine Namensnennung verlangt. Es erfasst darüber hinaus auch Assets ohne Namensnennungspflicht, damit Herkunft und Lizenzstatus vollständig nachvollziehbar bleiben.

Ein Datensatz verbindet mindestens:
- eindeutige Asset-ID;
- Assetname und konkrete Beschreibung;
- Autor/Urheber bzw. Rechteinhaber, exakt nach Quellenangabe;
- ursprüngliche Fundstelle und direkte Assetseite;
- verwendete Datei(en) und Projektpfad(e);
- Lizenzname und Lizenzversion bzw. Lizenzlink;
- erforderliche Namensnennung im vorgeschriebenen Wortlaut;
- vorgeschriebene Form und Platzierung der Nennung;
- Hinweise zu Änderungen, Bearbeitungen oder abgeleiteten Werken;
- Abrufdatum und verwendete Versions-/Downloadangabe;
- Status der Rechteprüfung und verantwortliche Prüfung;
- betroffene Builds, Pakete oder Veröffentlichungen.

Wenn mehrere Assets von demselben Autor stammen, bleibt jedes Asset einzeln zugeordnet. Der Autor kann zusätzlich als gruppierter Eintrag angezeigt werden; die Einzelzuordnung darf dadurch nicht verloren gehen. Mehrere Autoren oder Rechteinhaber eines Assets müssen vollständig abgebildet werden.

## 12.20 Wortlaut und Erfüllung der Namensnennung

Die erforderliche Attribution wird nicht frei umformuliert. Der vom Autor oder Lizenzgeber geforderte Wortlaut wird möglichst originalgetreu gespeichert. Zusätzlich werden Quelle, Lizenzhinweis und gegebenenfalls Änderungsvermerk erfasst, soweit die Lizenz dies verlangt.

Das Register unterscheidet:
- Namensnennung erforderlich;
- Namensnennung nicht erforderlich, Herkunftsnachweis dennoch geführt;
- keine Weitergabe-/Attributionspflicht, aber sonstige Lizenzbedingungen;
- Lizenz unklar oder noch nicht geprüft;
- Asset nicht für die vorgesehene Nutzung freigegeben.

Die konkrete Platzierung der Credits wird je Lizenz und Auslieferungskontext dokumentiert, beispielsweise Ingame-Credits, Credits-Menü, Dokumentation, Website oder mitgelieferte Lizenzdatei. Eine Nennung an nur einer Stelle gilt nicht automatisch als ausreichend, wenn die Lizenz weitere Anforderungen stellt.

## 12.21 Asset-Credit-Übersicht und Veröffentlichung

Aus dem Register muss eine lesbare Credit-Liste erzeugt werden können. Sie gruppiert Einträge sinnvoll nach Autor, Asset oder Lizenz, bewahrt aber die Zuordnung zwischen Autor, konkretem Asset und erforderlichem Nennungstext.

Vor jeder Veröffentlichung wird geprüft:
1. Alle tatsächlich ausgelieferten Drittassets sind im Register enthalten.
2. Autor, Asset, Quelle und Lizenz sind nachvollziehbar verknüpft.
3. Der vorgeschriebene Attributionstext ist vollständig vorhanden.
4. Änderungen und Bearbeitungen sind korrekt gekennzeichnet.
5. Die erforderliche Credit-Platzierung ist im Build bzw. in den mitgelieferten Unterlagen vorhanden.
6. Ungeklärte oder unzulässige Assets sind aus dem Releaseumfang ausgeschlossen.

Entfernte Assets werden nicht aus der Historie gelöscht. Ihr Status wird auf nicht mehr verwendet gesetzt; frühere Releases und deren Creditpflichten bleiben nachvollziehbar.

## 12.22 Rechteprüfung als Teil der Assetpipeline

Ein Asset darf erst in einen Releasekandidaten gelangen, wenn seine Lizenzbedingungen geprüft und dokumentiert sind. Der technische Importstatus ersetzt keine Rechtefreigabe. Automatisierte Prüfungen sollen fehlende Autorennamen, Lizenzlinks, Attributionstexte und ungeklärte Statuswerte erkennen.

Das Register ist die zentrale Quelle für die Erstellung der Credits. Kopierte Listen in einzelnen Szenen, Prefabs oder Entwicklernotizen gelten nicht als eigenständige maßgebliche Nachweise. Der tatsächliche Speicherort und das Dateiformat des Registers werden als Teil der Assetpipeline festgelegt.

## 12.23 Neue offene Assetentscheidung

| ID | Thema | Status |
|---|---|---|
| ASSET-011 | Technische Form, Ablage, Pflege und Buildintegration des zentralen Asset-Credit- und Attribution-Registers | Tool-/Prozessentscheidung erforderlich |
