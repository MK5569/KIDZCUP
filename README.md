# KIDZCUP – Deployment-Anleitung

Dieses Paket ist ein vollständiges, eigenständiges Web-Projekt (Vite + React).
Es enthält genau eine wichtige Datei mit eurer App-Logik: `src/App.jsx`
(identisch mit der `kidzcup-app.jsx`, die wir bisher hin- und hergeschickt haben).

## Warum dieser Umweg nötig ist

Die Vorschau hier in Claude läuft in einer abgeschirmten Umgebung ohne Zugriff auf
externe Dienste wie Supabase (daher der "Load failed"-Fehler). Sobald die App auf
einer echten Website läuft, verschwindet diese Einschränkung – ein ganz normaler
Browser-Tab darf mit Supabase sprechen.

## Deployment auf Vercel (empfohlen, kostenlos)

1. Auf **vercel.com** mit GitHub, GitLab oder E-Mail registrieren
2. **Ohne GitHub geht's auch direkt per Upload:**
   - Diesen ganzen Ordner als ZIP herunterladen (liegt bei den Dateien bereit)
   - Bei Vercel: "Add New..." → "Project" → im Upload-Bereich den entpackten
     Ordner reinziehen
   - Vercel erkennt automatisch "Vite" als Framework, Standardeinstellungen
     übernehmen, auf "Deploy" klicken
3. Nach ca. 1 Minute bekommt ihr eine echte URL wie `kidzcup-app.vercel.app`

## Deployment auf Netlify (Alternative, ebenfalls kostenlos)

1. Auf **netlify.com** registrieren
2. "Add new site" → "Deploy manually"
3. Vorher einmal lokal (oder ich kann das für euch vorbereiten) `npm run build`
   ausführen lassen – das erzeugt einen `dist`-Ordner
4. Diesen `dist`-Ordner bei Netlify per Drag & Drop hochladen
5. Fertige URL wie `kidzcup-app.netlify.app` erscheint sofort

## Eigene Domain (optional)

Beide Anbieter erlauben es, später eine eigene Domain (z. B. `anmeldung.kidzcup.de`)
zu verbinden – das lässt sich jederzeit nachträglich einrichten, ohne dass ihr neu
deployen müsst.

## Nach dem Deployment: Testen

1. Die neue URL öffnen
2. Oben auf "Admin" wechseln
3. Mit der E-Mail/Passwort einloggen, die ihr in Supabase angelegt habt

Falls dort wieder ein Fehler auftaucht, ist es jetzt ein "echter" Fehler (z. B.
falsche Zugangsdaten, RLS-Problem) und kein Sandbox-Problem mehr – dann schicke mir
einfach die genaue Meldung.

## Lokal testen (falls gewünscht, für technisch Interessierte)

```bash
npm install
npm run dev
```
Öffnet die App unter `http://localhost:5173` – funktioniert genauso wie die
Vercel/Netlify-Version, weil es dann ebenfalls ein normaler Browser-Tab ist.
