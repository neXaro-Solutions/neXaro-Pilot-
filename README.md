# neXaro Pilot

**Eigenständige KI-Plattform – vollständig getrennt vom CRM SumUp.**

Dieses Repository verwaltet ausschließlich die Pilot-Anwendung. Die bestehende Live-Version unter https://www.nexaro-solutions.de/pilot/ und ihre eigenständige Supabase-Datenbank bleiben zunächst unverändert.

## Struktur
- `pilot/`: Weboberfläche, Design, Flugzeug-/Avatar-Animation, Sprachsteuerung, Tests und Vorlagen
- `supabase/`: ausschließlich Pilot-spezifische Backend-Quellen und Migrationen
- `docs/`: Architektur, Migration, technische Grenzen, Abnahme
- `tests/`: Tests für Projektabgrenzung und Kernfunktionen

## Arbeitsprinzip
Aufgabe eingeben → Pilot plant und arbeitet → nur bei notwendigen Entscheidungen Nutzer einbeziehen → fertiges Ergebnis im Auftrag speichern.

## Wichtige Grenzen
**Keine CRM-Dateien, keine Website-Root-Dateien und keine Live-Datensätze in GitHub.** Die Pilot-Live-Daten verbleiben im separaten Supabase-Projekt `qfrylqxbqmuafyvnqkey`. GitHub speichert Quellcode und kontrollierte SQL-Migrationen, keine Nutzerinhalte, Datenbank-Backups oder Secrets.

**Achtung:** Das Ziel-Repository wurde als `public` erkannt. Bitte vor der Übernahme ausschließlich in Supabase liegender Backend-Quellen unter Settings → General → Change repository visibility auf **Private** setzen.

Der Migrationsbranch ist **nicht** automatisch deployt. Veröffentlichen erst nach Tests, Backup und Abnahme. Siehe `docs/MIGRATION_STATUS.md`.
