# neXaro Pilot – Architektur und Systemgrenzen

## Systemgrenze
- **Produkt:** KI-Plattform `neXaro Pilot`
- **Quellcode:** ausschließlich dieses Repository
- **Betriebsdaten:** eigenständiges Supabase-Projekt `qfrylqxbqmuafyvnqkey` (eu-central-1)
- **Live-Auftritt:** bis zum geprüften Umzug bestehender Pfad `/pilot/`; Website-Root bleibt unangetastet
- **CRM SumUp:** getrenntes Produkt. Keine gemeinsame Codebasis, kein fremder Datenbankzugriff, keine Migrationen in CRM.

## Verantwortlichkeiten
1. `pilot/`: Aufgaben-UI, Projektverlauf, Ergebnisdarstellung, Sprache und Design.
2. `supabase/functions/`: KI-Orchestrierung, Ausführung, Recherche, Artefakterstellung, Freigaben und Hintergrundjobs.
3. `supabase/migrations/`: versioniertes Datenmodell, Rollen, RLS und Integrität.
4. `tests/`: Sicherheits-, Vertrags-, Browser- und End-to-End-Tests.

## Fachliche Prinzipien
- Minimaler Nutzeraufwand, maximale zulässige Automatisierung.
- Projektname und Datum beim Anlegen, alle Ergebnisse im jeweiligen Auftrag.
- Keine doppelte Frage nach bereits bestätigten Entscheidungen.
- Nur echte notwendige Freigaben; risikoreiche externe Aktionen nicht ungefragt.
- Unklarheit und fehlende Belege transparent statt fingierter fertiger Ergebnisse.
- Responsive Darstellung auf Desktop, Android, iOS und macOS.

## Migrationsregeln
- Historische Quellstände nicht ungeprüft deployen.
- Die operative Supabase-Datenbank niemals aus einem alten Snapshot überschreiben.
- Versionierten Source-Stand mit produktiv deployten Edge-Functions und DB-Migrationen abgleichen.
- Datenbank + Storage verschlüsselt außerhalb GitHub sichern und Restore isoliert testen.
- Erst Staging, Tests, Freigabe und Rollback-Konzept, dann produktiver Cutover.
