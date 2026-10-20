<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/readme/logo-dunkel.svg">
    <img alt="Logo von Gesetze für KI: eine Waage, deren Säule das MCP-Zeichen bildet" src=".github/readme/logo.svg" width="110">
  </picture>
</p>

<h1 align="center"><a href="https://github.com/Gesetze-fuer-KI/gesetze">gesetze</a></h1>

<p align="center">
  <a href="https://github.com/Gesetze-fuer-KI/gesetze/actions/workflows/sync.yml"><img alt="Nächtlicher Abgleich" src="https://github.com/Gesetze-fuer-KI/gesetze/actions/workflows/sync.yml/badge.svg"></a>
  <a href="https://www.gesetze-im-internet.de"><img alt="Quelle: gesetze-im-internet.de" src="https://img.shields.io/badge/Quelle-gesetze--im--internet.de-1f4e79"></a>
  <a href="https://dejure.org/gesetze/UrhG/5.html"><img alt="Gemeinfrei nach § 5 UrhG" src="https://img.shields.io/badge/gemeinfrei-%C2%A7_5_UrhG-lightgrey"></a>
  <a href="https://liberapay.com/GesetzeFuerKI"><img alt="Über Liberapay unterstützen" src="https://img.shields.io/badge/Liberapay-unterst%C3%BCtzen-F6C915?logo=liberapay&logoColor=black"></a>
</p>

<p align="center"><b>Das gesamte Bundesrecht als Markdown, jede Nacht abgeglichen, mit jeder Änderung in der Git-Historie.</b></p>

Rund 6.100 Gesetze und Verordnungen in ihrer aktuellen Fassung, übernommen von [gesetze-im-internet.de](https://www.gesetze-im-internet.de). Jede Nacht kommt als Commit hinzu, was sich geändert hat, mit dem amtlichen Änderungsvermerk als Nachricht.

Das ist die Datengrundlage von **[Gesetze für KI](https://gesetze-fuer-ki.de)**: Darüber schlagen Claude, ChatGPT und andere Assistenten die Gesetze selbst nach. **[So verbinden Sie Ihren Assistenten](https://gesetze-fuer-ki.de/verbinden/)**. Die Dateien sind aber auch für sich nutzbar, zum Lesen, Durchsuchen und Vergleichen von Fassungen.

| | |
|---|---|
| **[Daten und Grenzen](https://gesetze-fuer-ki.de/daten/)** | [Woher die Texte kommen](https://gesetze-fuer-ki.de/daten/#woher-die-texte-kommen), [was nicht enthalten ist](https://gesetze-fuer-ki.de/daten/#was-nicht-enthalten-ist) und [wie genau sie sind](https://gesetze-fuer-ki.de/daten/#wie-genau-die-texte-sind) |
| **[Frühere Fassungen](https://gesetze-fuer-ki.de/werkzeuge/#fruhere-fassungen)** | Wie ein Assistent den Wortlaut von einem früheren Tag abruft |
| **[Unterstützen](https://gesetze-fuer-ki.de/unterstuetzen/)** | Der Dienst ist kostenlos und wird privat betrieben |

## Aufbau

Eine Datei je Gesetz, abgelegt nach den ersten zwei Buchstaben seiner Kennung: `es/estg.md` ist das Einkommensteuergesetz, `bg/bgb.md` das BGB, `ge/gewo.md` die Gewerbeordnung. Jede Datei beginnt mit Metadaten (Abkürzung, Titel, Stand, Ausfertigung, Quelle); danach folgen Gliederung und Vorschriften als Überschriften. Die Historie eines Gesetzes zeigt zum Beispiel

```bash
git log -p -- us/ustg_1980.md
```

## Wie der Abgleich läuft

<picture>
  <source media="(prefers-color-scheme: dark)" srcset=".github/readme/ablauf-dunkel.svg">
  <img alt="Ablauf: Die amtlichen Texte von gesetze-im-internet.de werden jede Nacht in das Repository gesetze übernommen, eine Markdown-Datei je Gesetz mit jeder Änderung als Commit. Der Server gesetze-fuer-ki holt sie stündlich, baut den Suchindex und stellt sie über MCP bereit. Ihr KI-Assistent schlägt darüber den Wortlaut nach." src=".github/readme/ablauf.svg" width="100%">
</picture>

Die [Action](.github/workflows/sync.yml) läuft jede Nacht um 03:17 UTC mit [`sync.py`](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki/blob/main/app/sync.py) aus [gesetze-fuer-ki](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki) und lädt nur Gesetze neu, die sich seit dem letzten Abruf geändert haben.

## Herkunft und Lizenz

Herausgeber der Texte ist das Bundesministerium der Justiz; amtliche Gesetzestexte sind nach § 5 UrhG gemeinfrei. Verbindlich ist die amtliche Fassung. Fehler der Umwandlung bitte als [Issue](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki/issues) melden.

---

<sub>Keine Rechtsberatung: Der Dienst liefert Gesetzestexte; maßgeblich ist die amtliche Fassung. · [Impressum](https://gesetze-fuer-ki.de/impressum/) · [Datenschutz](https://gesetze-fuer-ki.de/datenschutz/)</sub>
