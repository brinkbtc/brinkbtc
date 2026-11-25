# Architektur – Finanz-App Brink FokusMensch

Stand: Ende November 2026 · Phase 3 (Vorschlag zur Freigabe)

## Grundentscheidung: eine Web-App für Mac und iPhone

Die App läuft im Browser und lässt sich auf dem iPhone wie eine App auf den Homescreen legen (PWA). Eine Codebasis, ein Datenbestand.

- **Mac:** Rechnungen schreiben, Belege prüfen, Quartal abschließen, Export.
- **iPhone:** Belege fotografieren, einzeln direkt oder gesammelt einmal pro Woche als Stapel. Beides ist technisch derselbe Upload und kostet keinen Mehraufwand.
- **Später möglich:** Belege per E-Mail an eine eigene Adresse weiterleiten (z. B. für PDF-Rechnungen von Online-Shops).

Verworfene Alternative: native Mac- und iPhone-App mit iCloud-Sync. Bringt mehr Datenhoheit, braucht aber zwei Codebasen, schwierigere Synchronisation und deutlich mehr Pflegeaufwand.

## Bausteine

- **Frontend und Backend:** TypeScript, ein Framework (SvelteKit oder Next.js), serverseitig gerendert, mobil optimiert.
- **Datenbank:** PostgreSQL. Geldbeträge in Cent als Ganzzahlen, nie als Fließkommazahlen.
- **Beleg-Archiv:** Dateien unveränderbar abgelegt, mit SHA-256-Hash und Zeitstempel. Änderungen an Buchungen nur per Gegenbuchung und Protokoll (GoBD).
- **E-Rechnung:** XRechnung und ZUGFeRD (EN 16931) mit einer etablierten Open-Source-Bibliothek erzeugen, PDF als PDF/A-3 mit eingebettetem XML. Prüfung gegen den offiziellen KoSIT-Validator vor dem Festschreiben.
- **Belegerkennung (optional):** Ein Foto wird ausgelesen (Händler, Datum, Brutto, USt-Satz, Vorschlag fürs Konto). Bestätigt wird immer durch dich. Vorschlag: Claude API, nur mit deiner Zustimmung. Alternative: manuelle Eingabe.
- **E-Mail-Versand:** über das Postfach deiner Domain (SMTP), Rechnung als Anhang, Kopie im Archiv.
- **Exporte:** DATEV-Buchungsstapel (SKR04) plus Belege, Kennziffern-Übersicht für die USt-Voranmeldung, EÜR-Vorschau.

## Betrieb und Sicherheit

- **Hosting:** kleiner Server bei einem deutschen Anbieter (Rechenzentrum in Deutschland, Vertrag zur Auftragsverarbeitung), ca. 5–10 € pro Monat.
- **Zugang:** nur du (später zweiter Zugang für Person B), Login mit Passkey bzw. Zwei-Faktor, ausschließlich HTTPS.
- **Backup:** täglich verschlüsselt an einen zweiten Ort, monatlicher Wiederherstellungstest. Jederzeit ein Komplettexport (Daten und Belege), damit du nie eingesperrt bist.
- **Pflege:** Steuersätze, Kennziffern, Formate und Fristen zentral in einer Konfiguration. Einmal pro Jahr Durchsicht: Rechtsänderungen und Kontrolle der Formate.

## Umsetzungsreihenfolge

1. Gerüst: Login, Datenmodell (Haushalt → Personen → Tätigkeiten), Stammdaten, Backup.
2. Rechnungen: PDF und E-Rechnung, Versand, Festschreiben, Zahlungseingang. Ziel: Lexware für Rechnungen ab 2027 ablösen.
3. Belege: Upload vom iPhone, Erkennung, Kategorien, Vorsteuer.
4. Kfz, Privatanteile, Fahrtenlog, Anlageverzeichnis.
5. USt-Voranmeldung, Dashboard, Steuerrücklage.
6. DATEV-Export, EÜR-Vorschau, Jahresmappe.
7. Ausbaustufe Person B.

Migration aus Lexware: Kunden, Leistungen und Nummernkreis übernehmen. Offene Rechnungen 2026 werden dort zu Ende geführt. Für die Aufbewahrung bleiben die Lexware-Daten als Export erhalten.
