# Bierkrug holen – erster spielbarer Prototyp

## Was ist schon drin?
- Pixelige 2D-Ansicht mit bayerischem Bauern, Bierkrug, Kühen und Traktoren
- Zwei große Touch-Knöpfe zum Hoch- und Runterlaufen
- Tastatursteuerung mit Pfeiltasten oder W/S
- Drei Leben, Kollisionen, Bier holen und zum Hof zurückbringen
- Punkte und lokale Bestenliste auf dem jeweiligen Gerät
- Optionale gemeinsame Online-Gesamt- und Gruppen-Bestenliste über Supabase
- Als Web-App installierbar (Home-Bildschirm), wenn über HTTPS gehostet

## 1. Auf Windows testen – ganz einfach
1. ZIP-Datei entpacken, z. B. nach `Dokumente\Bierkrug`.
2. Den Ordner öffnen.
3. `index.html` doppelt anklicken. Das Spiel sollte sich im Browser öffnen.
4. Auf „Los geht's“ klicken. Mit den Knöpfen oder Pfeiltasten spielen.

Die lokale Bestenliste funktioniert sofort und speichert Ergebnisse im Browser auf diesem Gerät.

## 2. Eine Online-Version veröffentlichen
Für eine iPhone-Web-App und die gemeinsame Bestenliste muss das Spiel unter einer HTTPS-Adresse erreichbar sein. Eine einfache Möglichkeit ist GitHub Pages oder Netlify. Lade alle Dateien aus diesem Ordner in ein neues Website-Projekt hoch. `index.html`, `config.js`, `manifest.webmanifest` und `sw.js` müssen im selben Verzeichnis liegen.

## 3. Gemeinsame Online-Bestenliste mit Supabase einrichten
1. Kostenloses Projekt auf https://supabase.com anlegen.
2. Im Supabase-Projekt links den SQL Editor öffnen.
3. Den Inhalt von `supabase.sql` hineinkopieren und auf Run klicken.
4. Unter Project Settings > API die Project URL und den `anon`/`publishable` Key kopieren.
5. `config.js` mit einem Texteditor öffnen und die beiden leeren Werte eintragen:

   `supabaseUrl: "DEINE_PROJECT_URL"`

   `supabaseAnonKey: "DEIN_ANON_ODER_PUBLISHABLE_KEY"`

6. Die geänderte `config.js` erneut zusammen mit den anderen Dateien veröffentlichen.
7. Auf jedem iPhone dieselbe Spieladresse öffnen. Jede Person trägt ihren Namen ein. Für eine Familiengruppe tragen alle denselben Gruppen-Code ein, z. B. `FAMILIE`.

Wichtig: Nur den öffentlichen anon/publishable Key verwenden, niemals den `service_role`-Key in die App schreiben. Die SQL-Regeln erlauben öffentliche Lese- und Einfügezugriffe. Das ist für einen privaten Prototyp praktisch, aber nicht manipulationssicher. Für einen größeren öffentlichen Start sollte die Punkteübermittlung serverseitig geprüft werden.

## 4. Auf dem iPhone zum Home-Bildschirm hinzufügen
1. Die veröffentlichte HTTPS-Adresse in Safari öffnen.
2. Teilen antippen.
3. „Zum Home-Bildschirm“ wählen.
4. Falls angeboten, „Als Web-App öffnen“ aktivieren.
5. „Hinzufügen“ antippen.

Danach kann das Spiel über das neue Symbol gestartet werden. Es ist eine Web-App und keine native App aus dem App Store.

## Bekannte Grenzen dieses ersten Prototyps
- Noch einfache gezeichnete Platzhalter-Grafik statt finaler Figurenanimationen.
- Das Spiel ist zunächst ein Einzelspieler-Spiel; die Bestenliste ist gemeinsam.
- Die Online-Bestenliste wird erst aktiv, wenn Supabase eingerichtet wurde.
- Die lokale Bestenliste ist nur auf dem Gerät sichtbar, auf dem gespielt wurde.
- Beim Treffer wird der Bierkrug fallengelassen und der Lauf beginnt erneut.

## Dateien
- `index.html`: komplettes Spiel und Oberfläche
- `config.js`: Einstellungen für die optionale Online-Bestenliste
- `supabase.sql`: Datenbanktabelle und Zugriffsregeln
- `manifest.webmanifest`: Angaben zur installierbaren Web-App
- `sw.js`: einfacher Offline-Cache
