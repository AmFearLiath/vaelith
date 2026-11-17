# 23 — Originalkonzept- und Quellenregister

> Quelleninventar der am 17. November 2026 bereitgestellten documents.zip. Das Register unterscheidet Originalquellen, Datenbestände, Vorschläge und ausgeschlossene Projektinhalte. Es ist kein pauschaler Übernahmebeschluss.

## 23.1 Archivumfang

Das Archiv enthält 361 ZIP-Einträge: 325 Dateien und 36 Verzeichniseinträge. Darunter sind 82 Markdown-Dateien, 240 JSON-Dateien, zwei Bilddateien und ein eingebettetes ZIP-Archiv. Alle 240 JSON-Dateien ließen sich syntaktisch parsen. Syntaktische Gültigkeit bedeutet nicht, dass Schema, Referenzen, Balancing oder Inhalte freigegeben sind.

283 Dateien/Einträge liegen unter Items/. Darin befinden sich Kataloge, Planungsunterlagen, Migration Notes, Werkzeuge, Ressourcen, verarbeitete Materialien, Verbrauchsgüter, Lebensmittel und Wearables. Mehrere Versionen und Migrationsstände sind vorhanden. Summen über Dateien oder Einträge sind daher nicht mit eindeutigen finalen Spielinhalten gleichzusetzen.

## 23.2 Quellenklassen

| Klasse | Bedeutung | Umgang |
|---|---|---|
| Emberwild-Fachkonzept | Ursprüngliche Spielidee oder fachliche Spezifikation | Prüfen und in Vaelith-Kontext übertragen |
| Emberwild-Datenbestand | JSON-Katalog, Rezept, Item oder Schema | IDs, Felder, Versionen und Referenzen inventarisieren und kontrolliert migrieren |
| Konzeptfusion | Zusammengeführtes oder weiterentwickeltes Systemkonzept | Bestandteile und Herkunft prüfen; nicht pauschal final behandeln |
| Architektur-/Roadmapvorschlag | Technischer oder organisatorischer Vorschlag | Für Unity neu bewerten |
| Multiplayer-Konzept | Online-/Gilden-/Territorien-Erweiterung | Optionale Produktentscheidung; kein automatischer Scope |
| ASHFALL-exklusiv | Projektbezogene ASHFALL-Inhalte oder Implementierung | Für Vaelith ausgeschlossen |
| Allgemeines Prinzip | Nicht projektspezifischer Grundsatz | Nur nach eigenständiger Eignungsprüfung übernehmen |

## 23.3 Quelleninventar

### 3D, Bausystem und Expansion
- 3D_PERSPEKTIVE_UND_VERTIKALITAET_KONZEPT.md
- bausystem_und_expansion/00_MASTERVISION_UND_ACTION_PARADIGMA.md
- bausystem_und_expansion/00_RICHTLINIEN_UND_PARTNERSCHAFT.md
- bausystem_und_expansion/01_BURG_VS_DORF_GEBAEUDEKATALOG.md
- bausystem_und_expansion/01_MASTER_ROADMAP_EMBERENGINE_REWRITE.md
- bausystem_und_expansion/02_3D_BAUSYSTEM_UND_INTERAKTION.md
- bausystem_und_expansion/03_MULTIPLAYER_GILDEN_UND_TERRITORIEN.md
- bausystem_und_expansion/04_WELTKARTE_EXPANSION_UND_RESSOURCENKREISLAUF.md
- bausystem_und_expansion/05_DEV_EDITOR_UND_TOOLING.md
- bausystem_und_expansion/Building Workshop & Community Building Library.md

### Konzeptfusion
- concept_fusion/00_GESAMTVIZION_UND_SYSTEMARCHITEKTUR.md
- concept_fusion/01_ASCHE_OEKOLOGIE_KREATUREN_UND_GENETIK.md
- concept_fusion/02_WIRTSCHAFT_PRODUKTIONSKETTEN_UND_KARAWANEN.md
- concept_fusion/03_NPC_SIMULATION_MEISTER_UND_DORFLEBEN.md
- concept_fusion/04_EMERGENTE_EREIGNISSE_UND_ASCHE_DIREKTOR.md
- concept_fusion/05_AETHELGARD_WELT_UND_PROVINZ_STRATEGIE.md
- concept_fusion/06_UI_UX_DESIGN_UND_IMMERSION.md
- concept_fusion/07_UMSETZUNGS_ROADMAP_UND_CODE_ARCHITEKTUR.md

### Quest und Geschichte
- questsystem/expansion_questsystem.md
- questsystem/questbeispiele/ew_act1_silent_bell.json
- story/emberwild-grundlagen.md

### Simulation und Verteidigung
- Siedlungsübersicht_Verteidigung.md
- README.md

### Multiplayer
- multiplayer/00_UEBERSICHT_UND_MASTERPLAN.md
- multiplayer/01_WELTKARTE_UND_ZONEN_ARCHITEKTUR.md
- multiplayer/02_GILDEN_CLANS_UND_TERRITORIEN.md
- multiplayer/03_DIPLOMATIE_HANDEL_UND_UNTERSTUETZUNG.md
- multiplayer/04_KAMPF_BELAGERUNGEN_UND_GVG.md
- multiplayer/05_SERVER_EVENTS_UND_WELTBOSSE.md
- multiplayer/06_PERFORMANZ_NETZWERK_UND_CODE_STRUKTUR.md
- multiplayer/07_LEVELDESIGN_GENERIERUNG_UND_DEV_EDITOR.md
- multiplayer/08_ENTSCHEIDUNGSFRAGEN_UND_WEICHENSTELLUNGEN.md

### Items und Wirtschaft
Items/ umfasst Consumables, Food, Processed, Resources, Tools, Wearables, Planning, Migration Notes sowie ein eingebettetes Items.zip. Die Einzeldateien bleiben als Originalbestand erhalten. Dieses Register ersetzt nicht die dateiweise Katalog- und Referenzprüfung.

## 23.4 ASHFALL-Ausschluss

Explizit ASHFALL-bezogene Quellen im Archiv sind unter anderem:
- bausystem_und_expansion/LEGACY_ASHFALL_AUDIT_UND_OBSOLETE_FILES.md
- singleplayer/01_ARCHITEKTUR_ANALYSE.md
- singleplayer/02_ERWEITERBARKEIT_KERNBEREICHE.md
- singleplayer/03_FEATURE_UND_MECHANIK_VORSCHLAEGE.md
- singleplayer/04_KONZEPT_FUSION_ASHFALL_UND_LIVING_KINGDOM.md
- singleplayer/05_ASSET_INTEGRATION_UND_PIPELINE.md

ASHFALL-spezifische Inhalte, Strukturen, Implementierungen, Assets, Daten, Szenen, Algorithmen und Projektentscheidungen werden nicht nach Vaelith übernommen. Allgemeine Prinzipien dürfen nur unabhängig neu bewertet werden, wenn sie ohne Übernahme projektspezifischer Inhalte sinnvoll und mit Vaelith vereinbar sind.

## 23.5 Übernahmeregeln

1. Originaldateien bleiben unverändert als Quellenbestand erhalten.
2. Jede übernommene Aussage erhält eine Quellenreferenz.
3. Widersprüche werden sichtbar dokumentiert; keine stille Zusammenführung.
4. Alte Engine- und Implementierungsvorgaben werden nicht automatisch auf Unity übertragen.
5. Drafts, Vorschläge und Beispiele bleiben als solche gekennzeichnet.
6. Multiplayer-Inhalte sind optionale Erweiterungen, bis der Produktumfang beschlossen ist.
7. ASHFALL-exklusive Inhalte sind ausgeschlossen.
8. Fehlende Inhalte werden als Ergänzungskandidaten erfasst, nicht erfunden.
9. Vor JSON-Migration werden Schema, IDs, Referenzen, Duplikate und Versionshistorie geprüft.
10. Ein Agent darf keine vollständige Migration behaupten, wenn nur ein Teilbestand ausgewertet wurde.

## 23.6 Bearbeitungsstatus

| Bereich | Zugriff/Sichtung | Konsolidierung |
|---|---|---|
| Quest-Erweiterung | Quelle gelesen | Zielarchitektur in Dokument 25 ausgearbeitet; Datenmigration offen |
| Emberwild-Story | Quelle gelesen | Dramaturgieabgleich offen |
| 3D-/Bausystem | Quellen gelesen | Kernthemen identifiziert; vollständige Regelmigration offen |
| Konzeptfusion | Quellen gelesen | Systemweise Konsolidierung offen |
| Multiplayer | Quellen gelesen | Optionale Erweiterung; Produktentscheidung offen |
| Item-/Materialdaten | JSON syntaktisch geprüft | Semantische ID-/Referenzmigration offen |
| ASHFALL | Quellen identifiziert | Ausschluss |

Jede spätere Übernahme wird mit Quelldatei, Abschnitt/Feld, Zielkapitel, Änderungstyp, Begründung und Status dokumentiert.
