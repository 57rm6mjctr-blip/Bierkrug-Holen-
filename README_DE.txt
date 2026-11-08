BIERKRUG HOLEN – UPDATE 2

Neu in dieser Version:
- Deutsch/Englisch über die Sprachauswahl
- einfache, leise Hintergrundmelodie mit Ein/Aus-Schalter
- überarbeitete Pixeloptik
- mehr Kühe und Traktoren, etwas höhere und mit dem Spielfortschritt steigende Geschwindigkeit
- Gruppenname und Einladungscode können angelegt werden, sobald Supabase eingerichtet ist
- weltweite und Gruppen-Bestenliste über Supabase vorbereitet

WICHTIG – Online-Funktionen einrichten:
1. Supabase-Projekt öffnen oder kostenlos erstellen.
2. Im SQL Editor den gesamten Inhalt von supabase.sql einfügen und ausführen.
3. In Project Settings > API die Project URL und den öffentlichen anon/publishable Key kopieren.
4. Diese beiden Werte in config.js eintragen (niemals den service_role-Key verwenden).
5. Alle Dateien erneut in GitHub hochladen/ersetzen und committen.
6. GitHub Pages aktualisiert die Website danach automatisch.

Dateien zusammen im selben Ordner belassen. index.html ist das Spiel. config.js und supabase.sql werden für die Online-Bestenlisten benötigt.

Sicherheitshinweis: Die Datenbankregeln sind für einen Familien-Prototyp offen und nicht manipulationssicher. Für einen öffentlichen Wettbewerb sollte später eine Anmeldung und serverseitige Punkteprüfung ergänzt werden.
