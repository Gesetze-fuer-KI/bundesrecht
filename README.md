<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Gesetze-fuer-KI/.github/main/profile/logo-dunkel.svg">
    <img alt="Logo von Gesetze für KI: eine Waage, deren Säule das MCP-Zeichen bildet" src="https://raw.githubusercontent.com/Gesetze-fuer-KI/.github/main/profile/logo.svg" width="110">
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

Rund 6.100 Gesetze und Verordnungen in ihrer aktuellen Fassung, übernommen von [gesetze-im-internet.de](https://www.gesetze-im-internet.de). Jede Nacht kommt hinzu, was sich geändert hat, als Commit mit dem amtlichen Änderungsvermerk; die Historie reicht zurück bis zum ersten Abgleich im Oktober 2026.

Die Dateien sind die Datengrundlage von [Gesetze für KI](https://gesetze-fuer-ki.de), einem MCP-Server, mit dem KI-Assistenten die Gesetze selbst nachschlagen. Sie sind aber auch für sich nutzbar: zum Lesen, Durchsuchen und Vergleichen von Fassungen.

## Aufbau

Ein Gesetz ist eine Datei, abgelegt nach den ersten zwei Buchstaben seiner Kennung auf gesetze-im-internet.de: `es/estg.md` ist das Einkommensteuergesetz, `bg/bgb.md` das BGB, `ge/gewo.md` die Gewerbeordnung. GitHub zeigt höchstens 1.000 Einträge je Verzeichnis, daher die Unterordner.

Jede Datei beginnt mit den Metadaten:

```yaml
---
abkuerzung: EStG
titel: Einkommensteuergesetz
stand: zuletzt geändert durch Art. 7 G v. 29.6.2026 I Nr. 197
ausfertigung: '1934-10-16'
quelle: https://www.gesetze-im-internet.de/estg/
---
```

Danach folgen Gliederung und Vorschriften als Überschriften. Vor jeder steht ein unsichtbarer Kommentar mit der Kennung aus dem amtlichen XML (`<!-- norm id="BJNE003619116" -->`), damit Programme die Datei sicher zerlegen können.

## Änderungen nachlesen

Jeder nächtliche Commit nennt die geänderten Gesetze mit ihrem amtlichen Änderungsvermerk. Die Historie eines Gesetzes zeigt zum Beispiel

```bash
git log -p -- us/ustg_1980.md
```

## Wie der Abgleich läuft

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Gesetze-fuer-KI/.github/main/profile/ablauf-dunkel.svg">
  <img alt="Ablauf: Die amtlichen Texte von gesetze-im-internet.de werden jede Nacht in das Repository gesetze übernommen, eine Markdown-Datei je Gesetz mit jeder Änderung als Commit. Der Server gesetze-fuer-ki holt sie stündlich, baut den Suchindex und stellt sie über MCP bereit. Ihr KI-Assistent schlägt darüber den Wortlaut nach." src="https://raw.githubusercontent.com/Gesetze-fuer-KI/.github/main/profile/ablauf.svg" width="100%">
</picture>

Die [Action](.github/workflows/sync.yml) läuft jede Nacht um 03:17 UTC. Sie lädt [`sync.py`](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki/blob/main/app/sync.py) aus [gesetze-fuer-ki](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki), fragt jedes Gesetz mit der Version des letzten Abrufs an (`.sync/etags.json`) und lädt nur Geänderte neu.

## Herkunft und Lizenz

Die Texte stammen von gesetze-im-internet.de, herausgegeben vom Bundesministerium der Justiz. Amtliche Gesetzestexte sind nach § 5 UrhG gemeinfrei. Verbindlich ist die amtliche Fassung; für Fehler der Umwandlung wird keine Gewähr übernommen. Fehler bitte als [Issue](https://github.com/Gesetze-fuer-KI/gesetze-fuer-ki/issues) melden.

---

<sub>Keine Rechtsberatung: Der Dienst liefert Gesetzestexte; maßgeblich ist die amtliche Fassung. · [Impressum](https://gesetze-fuer-ki.de/impressum/) · [Datenschutz](https://gesetze-fuer-ki.de/datenschutz/)</sub>
