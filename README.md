# Word Document Guide

Ein interaktiver, deutschsprachiger Leitfaden für die Formatierung längerer Word-Dokumente. Die Anwendung verbindet eine Word-inspirierte Oberfläche mit geführten Lernschritten und Checklisten.

## Aktueller Stand

**Version 0.1 – erster funktionsfähiger Prototyp**

- Word-inspirierte Menüleiste und simulierte Dokumentvorschau
- Drei Lernmodule: Dokument einrichten, Formatvorlagen verwenden, Inhaltsverzeichnis erstellen
- Geführte Schritte mit Hinweisen und interaktiven Checklisten
- Fortschrittsanzeige pro Modul und insgesamt
- Automatische Speicherung des Lernfortschritts im lokalen Browser
- Responsive Layout für Desktop, Tablet und Smartphone
- GitHub-Actions-Workflows für Build-Prüfung und vorbereitete GitHub-Pages-Veröffentlichung

Die Vorschau bearbeitet oder importiert noch keine echten Word-Dateien (.docx). Der Lernfortschritt wird mit localStorage auf demselben Browser und Gerät gespeichert; es gibt noch keine Anmeldung oder Synchronisierung zwischen Geräten.

## Voraussetzungen

- Node.js 20 oder neuer (empfohlen)
- npm
- Git, wenn du das Projekt lokal klonen möchtest

## Lokal starten

1. Repository klonen:

   ```bash
   git clone https://github.com/Vinzenz-hub/word-document-guide.git
   cd word-document-guide
   ```

2. Abhängigkeiten installieren:

   ```bash
   npm install
   ```

3. Entwicklungsserver starten:

   ```bash
   npm run dev
   ```

4. Öffne die im Terminal angezeigte Adresse (standardmäßig http://localhost:5173).

## Produktions-Build prüfen

```bash
npm run build
npm run preview
```

Die fertigen Dateien werden in `dist/` erzeugt. Bei jedem Push auf `main` prüft GitHub Actions automatisch, ob der Build erfolgreich ist.

## Veröffentlichung mit GitHub Pages

Der Workflow `.github/workflows/deploy.yml` baut die Anwendung und veröffentlicht den Build über GitHub Pages.

Einmalige Einrichtung im Repository:

1. Öffne **Settings → Pages**.
2. Wähle bei **Build and deployment** als **Source** die Option **GitHub Actions**.
3. Nach dem nächsten Push auf `main` sollte der Workflow **Deploy to GitHub Pages** die Website veröffentlichen.
4. Die veröffentlichte Adresse findest du anschließend unter **Settings → Pages** oder im erfolgreichen Deployment-Lauf.

Die Veröffentlichung ist erst bestätigt, wenn der Deployment-Workflow erfolgreich abgeschlossen wurde.

## Projektstruktur

```text
word-document-guide/
├── .github/
│   └── workflows/
│       ├── ci.yml       # Automatische Build-Prüfung
│       └── deploy.yml   # Build und Veröffentlichung über GitHub Pages
├── src/
│   ├── App.tsx          # Oberfläche, Lernmodule und Fortschrittslogik
│   ├── index.css        # Layout und responsive Gestaltung
│   └── main.tsx         # React-Einstiegspunkt
├── index.html
├── package.json
├── tsconfig.json
├── vite.config.ts
└── README.md
```

## Nächste Entwicklungsschritte

1. Inhalte fachlich prüfen und redaktionell ausbauen.
2. Bedienbarkeit, Tastaturzugänglichkeit und responsive Ansichten testen.
3. Komponenten und Lerninhalte bei wachsendem Umfang trennen.
4. Automatische Tests ergänzen.
5. DOCX-Import und -Analyse als mögliches späteres Feature evaluieren.

## Inhaltliche Leitlinie

Menünamen können je nach Word-Version leicht variieren. Schriftgrößen, Seitenränder und andere Formatierungsvorgaben sind nicht universell gültig: Verbindliche Anforderungen der jeweiligen Hochschule, Schule oder Organisation haben Vorrang.

## Lizenz

Noch nicht festgelegt.
