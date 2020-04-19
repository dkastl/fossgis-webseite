# FOSSGIS Webseite

Die FOSSGIS-Website wird aus den Inhalten, die in den untergeordneten Verzeichnissen existieren, erzeugt. Die Struktur der Website wird durch die Struktur in `content` definiert. So sind z.B. alle Nachrichtenartikel im Verzeichnis `content/news`.

Um einen neuen Newsartikel anzulegen, muss eine neue Datei in `content/news` mit der Endung `.md` (Markdown) angelegt werden. Ein Artikel beginnt mit den Metadaten ganz oben:

	---
	title: "Dies ist ein Titel"
	date: "2019-02-29T15:00:00+02:00"
	author: "Marta Musterfrau"
	---

Anschließend kann der Inhalt geschrieben werden, z.B.

```markdown
## Unterüberschrift

Hier ist etwas Text.

Und hier ist ein neuer Absatz.
```

Statische Inhalte wie Bilder und dergleichen, die nicht von Hugo interpretiert werden sollen, gehören unter `static`, nicht nach `content`.

Lokal kann die Webseite mithilfe von hugo generiert werden: [Hugo Installationsanweisungen](https://gohugo.io/getting-started/installing/). Anschließend kann im Verzeichnis `hugo serve` ausgeführt werden. Dies startet einen lokalen Webserver, der üblicherweise unter [http://localhost:1313](http://localhost:1313) zu erreichen ist.

Im Zweifelsfall Inhalte anlegen und Pull Request öffnen, wir finden eine Lösung :)

## Tipps für Inhalte

- Überschriften mit max. 80—100 Zeichen
- Die Dateinamen bestimmen die spätere URL, bitte kurz und prägnant, wie z.B. `fossgis-2019-cfp.md`

## News anlegen

*Früher wurden Artikel teilweise in anderen Formaten angelegt. Um die URLs
nicht zu ändern, lassen wir die alten Artikel so.*

Um einen News-Artikel anzulegen, legt man unter `content/news/` eine Datei an.
Sie sollte als erstes das Datum im Namen haben und eine Markdown-Datei sein.
Also etwa `2020-03-04-Great-News.md`.

Oben muss dann rein:

```
---
title: "Great News"
date: "2020-03-04T11:00:00+02:00"
author: "Oskar Seltenfröhlich"
---
```

Darunter dann der Text im Markdown-Format.

Verlinkte Bilder gehören nach `static/news/images`. Auch sie bekommen das Datum
vorne in den Dateinamen. Bilder sollten immer lokal verlinkt werden, damit die
News-Artikel nicht kaputt gehen, wenn sich externe Inhalte ändern.

## Kalender-Eintrag anlegen

Um hier einen Eintrag zu machen, kopiert man die Datei
[`TEMPLATE.yaml`](data/kalender/TEMPLATE.yaml) in eine neue Datei und passt es
dort an. Der Dateiname muss mit dem Datum des Eintrags anfangen und auf `.yaml`
enden.

### Felder in der Datei

* `title`: Titel (Kurz und bündig bitte)
* `from`: Anfangsdatum oder Timestamp im ISO-Format
* `to`: Enddatum oder Timestamp im ISO-Format (optional)
* `url`: Link zu weiteren Details über den Event (optional)

Ein `to`-Datum sollte nur eingetragen werden, wenn der Event mehrere Tage
geht.

