<p align="center">
  <img alt="Logo von Gesetze für KI" src=".github/readme/logo.svg#gh-light-mode-only" width="110">
  <img alt="Logo von Gesetze für KI" src=".github/readme/logo-dunkel.svg#gh-dark-mode-only" width="110">
</p>

<h1 align="center"><a href="https://gesetze-fuer-ki.de">Gesetze für KI</a></h1>

<p align="center"><b>Ihr KI-Assistent schlägt das aktuelle Bundesrecht nach. Kostenlos.</b></p>

<p align="center">
  Alles zum Einrichten und Benutzen steht auf <b><a href="https://gesetze-fuer-ki.de">gesetze-fuer-ki.de</a></b>:<br>
  <a href="https://gesetze-fuer-ki.de/verbinden/"><b>So verbinden Sie Ihren Assistenten</b></a>
</p>

<p align="center">
  <a href="https://github.com/Gesetze-fuer-KI/gesetze/actions/workflows/sync.yml"><img alt="Nächtlicher Abgleich" src="https://github.com/Gesetze-fuer-KI/gesetze/actions/workflows/sync.yml/badge.svg"></a>
  <a href="https://liberapay.com/GesetzeFuerKI"><img alt="Über Liberapay unterstützen" src="https://img.shields.io/badge/Liberapay-unterst%C3%BCtzen-F6C915?logo=liberapay&logoColor=black"></a>
</p>

---

<sub>Ab hier für Neugierige und alle, die mitmachen wollen.</sub>

## Was hier liegt

Alle rund 6.100 Gesetze und Verordnungen des Bundes in ihrer aktuellen Fassung, eine Textdatei (Markdown) je Gesetz. Jede Nacht kommt als Commit hinzu, was sich geändert hat, mit dem amtlichen Änderungsvermerk als Nachricht. Die Dateien sind auch für sich nutzbar: zum Lesen, Durchsuchen und Vergleichen von Fassungen.

## Wie der Abgleich läuft

<img alt="Ablauf: Die amtlichen Texte von gesetze-im-internet.de werden jede Nacht in das Repository gesetze übernommen, eine Markdown-Datei je Gesetz mit jeder Änderung als Commit. Der Server gesetze-fuer-ki holt sie stündlich, baut den Suchindex und stellt sie über MCP bereit. Ihr KI-Assistent schlägt darüber den Wortlaut nach." src=".github/readme/ablauf.svg#gh-light-mode-only" width="100%">
<img alt="Ablauf: Die amtlichen Texte von gesetze-im-internet.de werden jede Nacht in das Repository gesetze übernommen, eine Markdown-Datei je Gesetz mit jeder Änderung als Commit. Der Server gesetze-fuer-ki holt sie stündlich, baut den Suchindex und stellt sie über MCP bereit. Ihr KI-Assistent schlägt darüber den Wortlaut nach." src=".github/readme/ablauf-dunkel.svg#gh-dark-mode-only" width="100%">

Die [Action](.github/workflows/sync.yml) läuft jede Nacht um 03:17 UTC mit [`sync.py`](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki/blob/main/app/sync.py) aus [gesetze-fuer-ki](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki). Sie fragt jedes Gesetz mit der Version des letzten Abrufs an (`.sync/etags.json`) und lädt nur geänderte neu.

## Ein Gesetz finden

Die Dateien liegen nach den ersten zwei Buchstaben ihrer Kennung auf gesetze-im-internet.de: `es/estg.md` ist das Einkommensteuergesetz, `bg/bgb.md` das BGB, `ge/gewo.md` die Gewerbeordnung. Jede Datei beginnt mit Metadaten (Abkürzung, Titel, Stand, Ausfertigung, Quelle); danach folgen Gliederung und Vorschriften als Überschriften, jeweils mit einem unsichtbaren Kommentar, der die amtliche Kennung trägt.

## Änderungen ansehen

Auf GitHub: eine Datei öffnen und **History** klicken. Lokal:

```bash
git log -p -- us/ustg_1980.md
```

## Herkunft und Lizenz

Herausgeber der Texte ist das Bundesministerium der Justiz; amtliche Gesetzestexte sind nach § 5 UrhG gemeinfrei. Verbindlich ist die amtliche Fassung. Fehler der Umwandlung bitte als [Issue](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki/issues) melden. Mehr unter [Daten und Grenzen](https://gesetze-fuer-ki.de/daten/).

---

<sub>Keine Rechtsberatung: Der Dienst liefert Gesetzestexte; maßgeblich ist die amtliche Fassung. · [Unterstützen](https://gesetze-fuer-ki.de/unterstuetzen/) · [Impressum](https://gesetze-fuer-ki.de/impressum/) · [Datenschutz](https://gesetze-fuer-ki.de/datenschutz/)</sub>
