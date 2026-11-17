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
