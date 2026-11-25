# Anforderungsprofil – Finanz-App Brink FokusMensch

Stand: Ende November 2026 · Phase 2 (zur Freigabe) · ohne personenbezogene Identifikationsdaten

## 1. Ausgangslage

Haushalt mit zwei Freiberuflern, zusammen veranlagt.

**Person A (Hauptnutzer)** – Trainer, Coach, Berater unter „Brink FokusMensch“. Zusätzlich angestellt (Lohnsteuerkarte, Reisekosten erstattet der Arbeitgeber).
- Umsätze 19 % USt, Ist-Versteuerung (§ 20 UStG), USt-Voranmeldung quartalsweise selbst über ELSTER.
- Größenordnung: 25.000–60.000 € Nettoumsatz pro Jahr, zuletzt rückläufig. Damit gilt für den Versand von E-Rechnungen die Übergangsfrist bis Ende 2027.
- Heute: Rechnungen in Lexware, Belege werden zum Jahresende gesammelt, der Steuerberater bucht (DATEV, SKR04) und erstellt EÜR, USt- und ESt-Erklärung.
- Pkw im Betriebsvermögen. Privatanteil wird mit 50 % der Kfz-Kosten angesetzt, aufgeteilt in einen Teil mit und einen Teil ohne USt. Kundenfahrten stellt er teils mit 0,50 €/km in Rechnung, teils sind sie im Angebotspreis enthalten.
- Telefon mit privatem Nutzungsanteil (unentgeltliche Wertabgabe 19 %).

**Person B** – Dozentin für drei öffentliche Bildungseinrichtungen. Umsätze steuerfrei nach § 4 Nr. 21 a bb UStG (jährliche USt-Erklärung mit 0). Häusliches Arbeitszimmer. Versichert über die KSK.

**Gemeinsam (nur Jahresmappe):** Kinder in Ausbildung, Kapitalerträge, Fondsbeteiligung, Vorsorge, Pflege-Pauschbetrag, Spenden, haushaltsnahe Dienstleistungen.

## 2. Rolle des Steuerberaters (Zielbild)

Hybridmodell: Die App erledigt die laufende Buchhaltung. Der Steuerberater bekommt zum Jahresende einen DATEV-Export samt Belegen und erstellt Abschluss und Erklärungen. Seine Buchführungsgebühr entfällt, die Abschlussgebühr sinkt im besten Fall. Die App wird so gebaut, dass später auch Selbsterstellung möglich ist (feldgenaue Werte für ELSTER).

## 3. Muss-Funktionen (Ausbaustufe 1: Person A)

**Rechnungen**
- Kunden, Leistungen und Nummernkreis (bestehende Lexware-Nummern fortführen).
- Positionen: Tagessatz, Pauschale, Stunden, Fahrtkosten (km × Satz, 19 % USt), Auslagen. Ein Hinweis bei Auslagen, die als durchlaufende Posten behandelt werden.
- Pflichtangaben nach § 14 UStG werden geprüft, Layout im Design von „Brink FokusMensch“.
- Ausgabe als PDF und als E-Rechnung (ZUGFeRD/XRechnung, Profil EN 16931), validiert. Leitweg-ID für öffentliche Auftraggeber.
- Versand per E-Mail. Status: Entwurf → festgeschrieben → bezahlt (Zahlungsdatum ist wichtig wegen der Ist-Versteuerung).
- Storno und Gutschrift statt Löschen. Festgeschriebene Rechnungen sind unveränderbar (GoBD).

**Belege und Ausgaben**
- Erfassung laufend: PDF-Upload, Foto, eingehende E-Rechnung (XRechnung/ZUGFeRD lesen).
- Kategorien auf Basis der SKR04-Konten, die der Steuerberater heute nutzt (Kfz, Reisekosten, Bewirtung 70/30, Geschenke, Telefon/Internet, Bürobedarf, Fachliteratur, Fortbildung, Wartung Hard- und Software, Beiträge, Abschluss- und Prüfungskosten, Geldverkehr).
- Vorsteuer wird automatisch ermittelt und dem Quartal der Zahlung zugeordnet.
- Revisionssichere Ablage (Hash, Änderungsprotokoll), Aufbewahrung 8 bzw. 10 Jahre.

**Kfz und Privatanteile**
- Kfz-Kosten getrennt nach Kosten mit Vorsteuer und ohne (Steuer, Versicherung).
- Privatanteil konfigurierbar (heute 50 %), wird automatisch gebucht und auf USt-pflichtige und USt-freie Teile verteilt.
- Einfaches Fahrtenlog für Kundenfahrten: dient als Nachweis für den betrieblichen Anteil und speist zugleich die km-Abrechnung auf Rechnungen.
- Telefon-Privatanteil als feste Monatsbuchung.

**Anlagevermögen**
- Anlageverzeichnis mit AfA, GWG (bis 800 € netto sofort), Computer und Software mit einem Jahr Nutzungsdauer, Abgänge.
- Entscheidungshilfe vor Anschaffungen („Was kostet mich der Laptop netto nach Vorsteuer und Steuerwirkung?“).

**Umsatzsteuer**
- Quartalsweise Voranmeldung nach Ist-Versteuerung, mit Kennziffern für die Eingabe in ELSTER (Umsätze 19 %, unentgeltliche Wertabgaben, Vorsteuer).
- Jahreswerte für die USt-Erklärung, Abgleich mit den geleisteten Vorauszahlungen.

**Überblick**
- Dashboard: Umsatz, Kosten und Gewinn laufend, offene Posten, USt-Zahllast des Quartals.
- Rücklage für die Einkommensteuer (Schätzung).
- Hinweis auf Grenzen: Kleinunternehmer, E-Rechnungspflicht, GWG-Grenze.

**Übergabe**
- DATEV-Export (Buchungsstapel SKR04, Belegbilder), EÜR-Vorschau in der Gliederung des Steuerberaters, Kontennachweis.

**Jahresmappe (gemeinsam)**
- Checkliste und Ablage für Lohnsteuerbescheinigung, Kapitalertrags- und Fondsbescheinigungen, Kinder, Vorsorge, Spenden, haushaltsnahe Dienstleistungen, Pflege.
- Werte werden erfasst und weitergegeben, aber nicht selbst berechnet.

## 4. Ausbaustufe 2: Person B

Einnahmen nach Auftraggeber, Ausgaben, Arbeitszimmer, EÜR mit steuerfreien Umsätzen, USt-Jahreserklärung (0), Einkommensschätzung für die KSK, DATEV-Export.

## 5. Kann-Funktionen (später)

Bankimport (CSV/CAMT) mit Abgleich gegen Rechnungen und Belege, Angebote, Mahnungen, wiederkehrende Rechnungen, Steuerprognose für den Haushalt, Anlage-EÜR-Werte feldgenau.

## 6. Bewusst ausgeklammert

Direkte ELSTER-Übermittlung (ERiC), vollständige Einkommensteuerberechnung, Bilanzierung, Lohnbuchhaltung.

## 7. Fragen an den Steuerberater

1. Honorar im Hybridmodell: Was kostet Abschluss plus Erklärungen, wenn die Buchhaltung fertig als DATEV-Export kommt?
2. Pkw: Worauf stützt sich der Privatanteil von 50 %, und welche Aufzeichnungen sollen künftig geführt werden?
3. Person B: Ist das Arbeitszimmer nach der Rechtslage seit 2023 weiter voll absetzbar (Mittelpunkt der Tätigkeit), oder gilt die Tagespauschale?
4. Vorsteuer künftig laufend in den Voranmeldungen? (Fachlich ja, kurz bestätigen lassen.)

## 8. Noch zu entscheiden (Phase 3)

Plattform (Mac lokal, Web oder beides; Belegfotos vom iPhone?), Datenhaltung und Backup, Migration aus Lexware (Kunden, Nummernkreis, offene Rechnungen).
