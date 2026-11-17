# 22 — Asset-Credit- und Attribution-Register

## 22.1 Zweck und Geltungsbereich

Dieses Register dokumentiert externe Assets und sonstige Drittinhalte, die in Vaelith verwendet werden. Sein besonderer Zweck ist, alle Autoren und Rechteinhaber zu erfassen, deren Lizenz eine Namensnennung verlangt, und jeden Autor eindeutig mit dem konkreten Asset sowie dem vorgeschriebenen Nennungstext zu verbinden.

Das Register umfasst auch Drittinhalte ohne Namensnennungspflicht. Damit bleiben Herkunft, Lizenz, Änderungen und Freigabestatus vollständig nachvollziehbar. Es gilt für Modelle, Texturen, Materialien, Sounds, Musik, Sprachaufnahmen, Fonts, Icons, Animationen, VFX, Bibliotheken und sonstige externe Inhalte.

## 22.2 Verbindliche Grundregeln

- Jedes verwendete Drittasset erhält eine stabile Asset-ID und einen eigenen Datensatz.
- Autor/Urheber und konkretes Asset werden eindeutig miteinander verknüpft.
- Der erforderliche Attributionstext wird exakt nach Lizenz-/Quellenanforderung gespeichert.
- Lizenzname, Lizenzversion und Fundstelle werden dokumentiert.
- Die Namensnennungspflicht wird nicht aus dem Preis oder der kostenlosen Verfügbarkeit abgeleitet.
- Änderungen und abgeleitete Werke werden dokumentiert.
- Unklare Rechte blockieren die Releasefreigabe.
- Entfernte Assets bleiben als historische Datensätze erhalten und werden als nicht mehr verwendet markiert.
- Das Register wird vor jedem Release gegen die tatsächlich ausgelieferten Inhalte geprüft.

## 22.3 Datensatzstruktur

Jeder Assetdatensatz enthält mindestens folgende Felder:

| Feld | Bedeutung |
|---|---|
| asset_id | Eindeutige, stabile interne ID |
| asset_name | Originalname bzw. eindeutiger Name des Assets |
| asset_description | Kurze Beschreibung und konkrete Verwendung |
| asset_type | Kategorie, z. B. Modell, Textur, Audio, Font oder Animation |
| author_name | Name des Autors/Urhebers exakt nach Quelle |
| rights_holder | Rechteinhaber, sofern abweichend oder zusätzlich |
| source_name | Plattform, Anbieter oder ursprüngliche Quelle |
| source_url | Direkte Fundstelle des Assets |
| license_name | Lizenzbezeichnung |
| license_version | Lizenzversion oder Veröffentlichungsstand |
| license_url | Link zum vollständigen Lizenztext |
| attribution_required | Ja / Nein / Unklar |
| attribution_text | Vorgeschriebener Nennungstext im erforderlichen Wortlaut |
| attribution_placement | Lizenzkonforme Platzierung der Nennung |
| modification_notice | Erforderlicher Hinweis auf Änderungen/Bearbeitungen |
| original_filename | Ursprünglicher Dateiname |
| project_paths | Verwendete Projektpfade |
| asset_version | Version/Downloadstand |
| acquired_at | Abrufdatum |
| modified | Ob und wie das Asset verändert wurde |
| commercial_use | Erlaubt / Verboten / Bedingt / Unklar |
| redistribution | Bedingungen für Weitergabe/Auslieferung |
| review_status | Ungeprüft / In Prüfung / Freigegeben / Gesperrt |
| reviewed_by | Verantwortliche prüfende Person |
| reviewed_at | Datum der Rechteprüfung |
| release_usage | Builds, Pakete oder Veröffentlichungen, in denen es enthalten ist |
| notes | Zusätzliche Lizenzbedingungen und Hinweise |

Wenn ein Asset mehrere Autoren oder Rechteinhaber besitzt, wird jeder einzeln erfasst und mit dem Asset verknüpft. Wenn ein Autor mehrere Assets bereitstellt, bleibt jedes Asset als separater Datensatz bestehen.

## 22.4 Autorenzuordnung und Credit-Ausgabe

Das Register muss zwei Ansichten unterstützen:

1. **Assetansicht:** Ein Asset zeigt alle zugehörigen Autoren, Rechteinhaber, Lizenzen und erforderlichen Nennungstexte.
2. **Autoransicht:** Ein Autor zeigt alle verwendeten Assets und die dazugehörigen Nennungspflichten.

Die veröffentlichte Credit-Liste wird aus den geprüften Datensätzen erzeugt. Gruppierung oder Sortierung darf die erforderliche Einzelzuordnung nicht verschleiern. Lizenzspezifische Formulierungen werden nicht vereinheitlicht, wenn dadurch Pflichtangaben verloren gehen.

## 22.5 Rechte- und Freigabestatus

| Status | Bedeutung |
|---|---|
| Ungeprüft | Quelle/Lizenz noch nicht ausreichend untersucht |
| In Prüfung | Informationen werden gesammelt oder rechtlich bewertet |
| Freigegeben | Vorgesehene Nutzung und Bedingungen sind dokumentiert und geprüft |
| Bedingt freigegeben | Nutzung nur unter konkret dokumentierten Bedingungen zulässig |
| Gesperrt | Nutzung für den vorgesehenen Zweck nicht zulässig oder ungeklärt |

Nur freigegebene oder vollständig erfüllte bedingt freigegebene Datensätze dürfen in Releaseinhalte gelangen. Ein Import in Unity ist keine Rechtefreigabe.

## 22.6 Releaseprüfung

Vor jeder Veröffentlichung wird der tatsächliche Build-/Contentbestand mit dem Register abgeglichen. Die Prüfung stellt sicher, dass keine verwendeten Drittinhalte fehlen, alle erforderlichen Autoren genannt werden, der Wortlaut korrekt ist und die vorgeschriebene Platzierung vorhanden ist.

Zusätzlich werden Lizenzdateien, Notices und sonstige erforderliche Begleitunterlagen erzeugt bzw. beigelegt. Die konkrete Ausgabeform richtet sich nach den jeweiligen Lizenzbedingungen und dem Veröffentlichungskanal.

## 22.7 Pflege und Historie

Bei Assetupdates, Versionswechseln, Änderungen der Lizenzbedingungen oder Wechsel der Verwendung wird der Datensatz aktualisiert und die Änderung nachvollziehbar protokolliert. Frühere Angaben werden nicht spurlos überschrieben, wenn sie für bereits veröffentlichte Versionen relevant sind.

Wenn ein Asset entfernt wird, wird sein Status auf nicht mehr verwendet gesetzt. Bereits veröffentlichte Builds behalten ihre historische Credit- und Lizenzdokumentation.

## 22.8 Offene technische Entscheidungen

Die technische Ablage (z. B. strukturierte Quelldatei, Datenbank oder Assetkatalogintegration), das konkrete Austauschformat und die automatische Buildvalidierung werden im Rahmen der Assetpipeline entschieden. Bis dahin gilt dieses Dokument als fachliche Mindestanforderung an die Datensammlung und Prüfung.

