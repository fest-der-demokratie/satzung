# Satzung – Fest der Demokratie e.V.

Dieses Repository enthält die Vereinssatzung des **Fest der Demokratie e.V.** (Pfaffenhofen an der Ilm).

## Inhalt

- [`satzung.md`](satzung.md) – die Satzung als Markdown-Quelle (maßgebliche, versionierte Fassung)

## PDF

Die PDF-Fassung wird automatisch aus `satzung.md` gebaut und **nicht** im Repository abgelegt.

Der GitHub-Actions-Workflow [`.github/workflows/pdf.yml`](.github/workflows/pdf.yml) läuft bei **jedem Push** (sowie manuell über *Actions → Satzung PDF → Run workflow*) und erzeugt die PDF mit `pandoc` + `xelatex`.

- **Immer:** Die PDF wird als Artifact `satzung-pdf` hochgeladen und kann über die jeweilige Action-Zusammenfassung heruntergeladen werden.
- **Bei einem Git-Tag:** Zusätzlich wird die PDF an das GitHub-Release gehängt:

  ```sh
  git tag v1.0
  git push --tags
  ```

## Schrift

Die PDF wird in **IBM Plex Serif** gesetzt. Die Schriftdateien liegen im Ordner [`fonts/`](fonts/) und werden vom Build per Dateipfad in `xelatex` geladen – so ist der PDF-Build unabhängig von den im `pandoc/latex`-Image vorhandenen Schriften. IBM Plex Serif steht unter der [SIL Open Font License](fonts/OFL.txt).

## Bearbeiten

Änderungen erfolgen ausschließlich in `satzung.md`. Nach dem Push baut der Workflow automatisch eine neue PDF.

## Abhängigkeiten

Die verwendeten GitHub-Actions werden über [Dependabot](.github/dependabot.yml) wöchentlich auf Updates geprüft.
