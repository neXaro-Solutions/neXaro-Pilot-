# Stand der Trennung und Migration – 09.10.2026

## Gesichert identifiziert
- Quellstand Pilot-Frontend: `neXaro-Solutions/nexaro-solutions-website` @ `fa848fe8becd78da7347b9085e19f496ce33f36b`, ausschließlich Verzeichnis `pilot/`.
- Bisher versionierte Pilot-Backends: ausschließlich Pilot-relevante Dateien unter `supabase/` desselben Quellstands.
- Eigenes Supabase-Projekt Pilot: `qfrylqxbqmuafyvnqkey` (Frankfurt), produktive Daten verbleiben dort.
- Neues Ziel-Repository: `neXaro-Solutions/neXaro-Pilot-`. Sichtbarkeit bei Prüfung **PUBLIC**.
- CRM SumUp und Website-Root: **nicht zur Migration vorgesehen**.

## Übernahme- und Freigabestufen
1. **Quellcode-Baseline:** den vorhandenen Pilot-Code bytegleich ins neue Repo übernehmen; README/Architektur ergänzen. Offen, bis alle Quellobjekte verifiziert sind.
2. **Backend-Inventar:** Alle in Supabase laufenden Funktionen abgleichen; nur öffentlich vorhandene Pilot-Quellen werden übernommen, solange Ziel nicht Private ist.
3. **Datenstand:** Bestehende Tabellen und Inhalte bleiben in der eigenständigen Pilot-Datenbank. Keine nutzerbezogenen Daten in GitHub.
4. **Wiederherstellung:** Separat verschlüsseltes Datenbank- und Storage-Backup sowie dokumentierter Test-Restore.
5. **Refactoring:** monolithische Pilot-Oberfläche modularisieren, ohne ursprüngliche Funktionslogik oder Design zu verlieren.
6. **Abnahme:** Desktop/Mobil, Sprachauswahl, Avatar/Flugzeug, komplette Auftragskette, Berechtigungen, E2E, Rollback und Deployment.

## Offene Risiken
- Das GitHub-Repository muss **Private** werden, bevor intern/deployed-only Quellcode archiviert wird.
- Der Git-Stand der Website enthält nicht alle aktuell in Supabase deployten Funktionen bzw. Datenbankmigrationen.
- Einige bestehende Tests hängen noch von der bisherigen Website-Verzeichnisstruktur ab.
- Der Git-Import ist **kein** Backup von Live-Nutzerdaten und keine Live-Bereitstellung.

## Schutzregel
Keine Änderungen an `nexaro-solutions-website/main`, CRM-Repositories oder CRM-Datenbank. Keine Produktionseingriffe während des Imports.
