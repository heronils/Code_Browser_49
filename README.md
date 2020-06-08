# Code Browser 4.9

*[Read in english](README_EN.md)*

[Einführung](#einführung) • [Warum dieses Repo](#warum-dieses-repo) • [Installation](#installation) • [Tastenkürzel](#tastenkürzel) • [Direktiven](#direktiven) • [Tips und Tricks](#tips-und-tricks) • [Versionshistorie](#versionshistorie) • [Credits](#credits)

![Bildschirmfoto von Code Browser](screenshots/de/hallowelt.png)

*Bildschirmfoto von Code Browser.*

## Einführung

[Code Browser](http://tibleiz.net/code-browser/) ist ein Zen-artiger Text-Editor, geschrieben von [Marc Kerbiquet](http://tibleiz.net/). Er lädt in Sekundenbruchteilen und zeigt auch riesige Dateien ohne große Verzögerungen an. Er verfügt über eine eigene Skriptsprache, mit Hilfe derer man die Funktionalität des Editors erweitern kann.

Seine revolutionäre Eigenschaft aber besteht darin, wie er spezielle formatierte [Direktiven](#direktiven) im Quellcode interpretiert und anzeigt:

* *Sektionen* (englisch: *Sections*). Dunkelblau im Bildschirmfoto. Sie falten frei zu wählende Teile des Codes weg. Man kann in solche Sektionen mittels `Alt` + (`→` oder `←`) hinein und hinaus navigieren, so wie man in Datei-Browsern in Ordner hinein und hinaus navigieren kann. Weshalb Sektionen ursprünglich von Marc Kerbiquet auch *Folder* (deutsch: *Ordner*) genannt wurden.

  Sektionen können beliebig tief verschachtelt werden. Somit kann man eine lineare Code-Datei in einen Baum aus 'Mini-Dateien' umwandeln, was der Code-Strukturierung sehr förderlich ist. Es bleibt allerdings tatsächlich eine einzelne Datei.
* *Links*. Hellgrün im Bildschirmfoto. Sie erweitern das Konzept, und ermöglichen es, Verweise zu anderen Sektionen oder auch zu anderen Dateien einzufügen, vergleichbar zu [Hyperlinks](https://de.wikipedia.org/wiki/Hyperlink) in HTML-Dokumenten. In der Praxis werden Links gerne in indexierenden Dateien oder Doku´s eingesetzt, seltener im Code selbst. Sie bieten weitere interessante Möglichkeiten wegen ihrer Fähigkeit, auf Zeilennummern oder sogar auf Suchresultate regulärer Ausdrücke zu verlinken.
* *Beschreibungen* (englisch: *Descriptions*). Der waldgrüne Text im Bildschirmfoto. Sie sind 'visueller Zucker'. Es handelt sich um hübsch anzusehende, wahlweise farbig hervorgehobene Kommentare. Die Kommentarzeichen werden ausgeblendet. Meine Nutzerskripte verwenden Beschreibungen für spezielle Direktiven.

Mehr Informationen dazu gibt´s in der Hilfedatei oder [auf der Projektseite](http://www.tibleiz.net/code-browser/code-folding.html).

## Warum dieses Repo?

Nach Version 4.9 hat der Autor leider ein wichtiges Feature entfernt – relative Einrückung (siehe *Folding* → *Relative Indentation* in der Hilfedatei) – was den Editor für einrückungsbasierte Sprachen wie [Python](https://www.python.org/) eher unbrauchbar gemacht hat. Ferner wurde die Geschwister-Navigation verändert – `Strg` + `Umschalttaste` + (`↑` oder `↓`) – welche nun die Ebene wechselt wenn man über Sektionsgrenzen hinweg navigiert.

Da ich diese Features in [Treesearcher](https://github.com/nilslindemann/Treesearcher) benötige, hier ein Backup von Version 4.9, dazu ferner meine globalen Einstellungen und meine Benutzerskripte.

## Installation

1. Lade die zu deinem Betriebssystem passende Portable aus dem hier befindlichen Ordner `setup` herunter und [entpacke](https://www.7-zip.de/) Sie. Der Editor ist die `cb.exe` unter Windows und die `code-browser` im Ordner `usr/local/bin` unter Linux.

Die nachfolgenden Schritte sind optional aber ich empfehle sie.

2. Lies den Abschnitt *Customizing* → *Files* in der beigefügten Hilfedatei.

3. Starte den Editor einmal. Das erstellt die unter 2. beschriebenen Nutzerverzeichnisse. [Suche gegebenfalls systemweit](https://www.voidtools.com/) nach `code-browser-4` unter Windows oder `.code-browser-4` unter Linux. Diese Ordner sind die Nutzerverzeichnisse.

4. *Globale Einstellungen ändern*: Ersetze die globale `preferences.cbc` mit der in diesem Verzeichnis.

   Die Hauptunterschiede sind: Relative Einrückung wird als Standard gesetzt, ein (meiner Meinung nach) hübscher anzusehendes Theme wird verwendet (Siehe *Themes* → *Purple-Blue* in der `preferences.cbc`), einige Tastenkürzel werden umdefiniert (siehe *Key Mappings* → *Nils*), und einige Sprachen werden geändert (siehe *Languages*). Auch wird unter Anderem Python (`Alt` + `p`) und Node.js (`Alt` + `n`) als Tool definiert (siehe *Tools*).

   Die `preferences.cbc` kann nach Belieben verändert werden, **wird aber bei einer Neuinstallation – [falls Du den Installer verwendet hast](https://web.archive.org/web/20160912162221/http://tibleiz.net:80/code-browser/download.html) – überschrieben**.

5. *Benutzerskripte aktivieren*: Verschiebe die `user.cbs` und die `user.cbc` hier im Verzeichnis in das in Schritt 3 erstellte Nutzerverzeichnis. Die `user.cbs` sind die Skripte, und die `user.cbc` verbindet die Skripte mit dem Editor.

   *Beachte, daß das Layout der `user.cbc` zerstört wird, wenn Du Änderungen innerhalb von Code Browser via 'Tools' → 'Options...' vornimmst. Mach Dir zur Not ein Backup dieser Datei.*

   Die Benutzerskripte bieten weitere Funktionen, wie das Falten und Entfalten von Sektionen und das Auskommentieren von Code-Abschnitten.

## Tastenkürzel

[Wenn meine Benutzerskripte und meine Nutzereinstellungen installiert sind](#installation), verwendet der Code Browser die folgenden Tastenkürzel. Die Kürzel können unter `preferences.cbc` → *Key Mappings* → *(aktiviertes Key Mapping)* geändert werden. Die mit dem Text *(Benutzerskript)* davor werden von meinen Benutzerskripten definiert und können in der `user.cbc` geändert werden.

### Zu lang, hab's nicht gelesen

[Hier ein Youtube Video](https://youtu.be/sU4ThIJ6eKc) (englisch), das erklärt, wie man einige der unten aufgelisteten Tastenkürzel verwendet.

### Grundlegendes

* `Strg` + `z` und `Strg` + `y` – Undo und Redo
* `Strg` + `Umschalttaste` + `s` – Speichere alle Dateien, auch die nicht sichtbaren (Zum Beispiel solche, die man verändert hat und aus denen man dann via Link hinaus navigiert ist).
* `Esc` – Schließe jeglichen Dialog unterhalb des Editors oder, wenn kein Dialog offen ist, schließe den aktuellen Tab.
* `Alt` + `f4` – Beende Code Browser. Wenn Dateien ungespeichert sind, wird Code Browser nachfragen was getan werden soll.
* ... und noch weitere, die man im Hauptmenü einsehen kann.

### Ansichtsmodi

* `F4` bis `F7` – Zwischen den vier verschiedenen Ansichtsmodi von Code Browser wechseln.

  *Wegen eines Bugs in Code Browser kann man nicht mehr zu einem vorherigen Dokument via Link zurücknavigieren, wenn man zwischendrin den Ansichtsmodus wechselt. In dem Fall muss man das vorherige Dokument von Hand wieder öffnen.*

### Navigation

* `Alt` + (`↑` oder `↓`) – Zur vorherigen oder zur nächsten Sektion/Link springen.
* `Alt` + (`→` oder `←`) – In eine Sektion/einen Link hinein- oder aus ihr wieder hinaus navigieren.
* `Strg` + `Umschalttaste` + (`↑` oder `↓`) – Zur vorherigen oder nächsten Geschwister-Sektion/Link in der Eltern-Ebene springen – Abkürzung für `Alt` + `←`, `Alt` + (`↑` oder `↓`), `Alt` + `→`.
* *(Benutzerskript)* `Strg` + `Alt` + (`↑` oder `↓`) – Zum vorherigen oder zum nächsten Absatz springen (Absatz = Durch Leerzeilen getrennte Codezeilen).
* `Alt` + `g` – Springe zur einzugebenden Zeilennummer.
* `Strg` + `b` – Springe zur entsprechenden Klammer. Zusätzlich `Umschalttaste` wählt den Text dazwischen aus.

### Sektionen

* `F12` – Eine neue Sektion erstellen. Wenn Text selektiert ist, wird dieser der Inhalt der Sektion werden.
* `Umschalttaste` + `F12` – Die Sektion unter dem Cursor löschen. Ihr Inhalt wird nicht gelöscht, sondern auf die Eltern-Ebene verschoben.
* `Alt` + `Enter` – Eigenschaften der Sektion oder des Links unter dem Cursor bearbeiten.
* *(Benutzerskript)* `Strg` + `Alt` + (`←` oder `→`) – Absatz unter dem Cursor falten oder die Sektion unter dem Cursor entfalten.

  *Ohne den schließenden Marker einer entfalteten Sektion – `)` – kannst du die Sektion nicht wieder zusammenfalten.*

### Links

* `Strg` + `Alt` + `c` – Kopiere einen Link zur aktuellen Sektion in die Zwischenablage. Kann dann mit `Strg` + `v` woanders – auch in andere Dateien – eingefügt werden. Damit das funktioniert, muss die Sektion und alle Eltern-Sektionen über eine ID verfügen (ID = Ein frei zu wählender Text). Diese kann für eine Sektion (oder einen Link) entweder von Hand hinzugefügt werden, mittels `Alt` + `Enter` wenn der Cursor sich auf der Sektions- oder Linkzeile befindet, oder einfach die Sektion einmal mit `Strg` + `Alt` + `→` entfalten und dann mit `Strg` + `Alt` + `←` wieder falten. Das setzt die ID mit dem Titel der Sektion gleich.

Es ist kein Tastenkürzel definiert, um einen Link von Hand zu erstellen, da das sowieso ein umständlicher Prozess ist.

### Beschreibungen

* `F11` oder `F10` – Den selektierten Text zu einer Beschreibung oder zurück zu normalem Text konvertieren.

### Text verschieben

* *(Benutzerskript)* `Strg` + (`↑` oder `↓`) – Die aktuelle Zeile oder Selektion eine Zeile nach oben oder nach unten verschieben. Die Selektion muss kein sauberer selektierter Block sein, es werden einfach alle Zeilen verschoben, in denen etwas selektiert ist.

### Code auskommentieren und entkommentieren

* *(Benutzerskript)* (`Umschalttaste` +) `Alt` + `x` – Die aktuelle Zeile oder die Selektion auskommentieren oder wieder entkommentieren. Verwendet `~<Leerzeichen>` als Direktive. Funktioniert rekursiv bei Sektionen.

### Lesezeichen

* `Strg` + `F2` – Ein Lesezeichen setzen.
* (`Umschalttaste` +) `F2` – Zum nächsten oder vorherigen Lesezeichen springen. Lesezeichen-Navigation funktioniert nur innerhalb einer einzelnen Datei und Lesezeichen sind nicht dauerhaft zwischen Sitzungen.
* (`Umschalttaste` +)`Strg` + `m` – Hebe alle Vorkommen des aktuell selektierten Textes im aktuellen Dokument hervor oder entferne alle Hervorhebungen.

### Suchen und ersetzen

* `Strg` + `r` – Öffne den *Suchen und ersetzen*-Dialog.
* `Alt` + `r` – Wenn der *Suchen und ersetzen*-Dialog den Fokus hat, wähle das erste Suchresultat aus, oder ersetze es und wähle das nächste Suchresultat aus. Leider kann dieses Tastenkürzel nicht geändert werden.
* (`Umschalttaste` +) `F3` – Finde das nächste oder das vorherige Suchresultat, ersetze das aktuelle nicht.

## Direktiven

Hier eine Referenz der für Code Browser und meine Benutzerskripte bedeutsamen Metazeichen und -zeichengruppen. So würden sie in einem anderen Editor aussehen. Diejenigen, welche für Code Browser relevant sind, sind gelb hinterlegt. Solche, die für meine Benutzerskripte relevant sind, sind orange hinterlegt (Letztere haben nur eine Bedeutung, wenn Sie am Anfang eines beschreibenden Kommentars stehen).

*Edit: Zumindest sollten sie farbig hinterlegt sein, aber Github´s Markdown Parser unterstützt keine farbige Hervorhebungen. Browser-Erweiterungen wie [diese für Firefox](https://addons.mozilla.org/de/firefox/addon/markdown-viewer-webext/) oder [diese für Chrome](https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk) werden [die Hervorhebungen anzeigen](https://raw.githubusercontent.com/nilslindemann/Code_Browser_49/master/README.md#direktiven).*

<pre>
<span style='background:yellow'>#[of]</span>ID der Sektion<span style='background:yellow'>:</span>Titel der Sektion
Inhalt der Sektion
<span style='background:yellow'>#[cf]</span>

<span style='background:yellow'>#[l]:</span>Titel des Links<span style='background:yellow'>:#</span>ID der Sektion

<span style='background:yellow'>#[c]</span>Beschreibender Kommentar

<span style='background:yellow'>#[c]</span><span style='background:orange'>( </span>Titel der entfalteten Sektion
Inhalt der Sektion
<span style='background:yellow'>#[c]</span><span style='background:orange'>)</span>

<span style='background:yellow'>#[c]</span><span style='background:orange'>~ </span>Auskommentierter Text
<span style='background:yellow'>#[c]</span><span style='background:orange'>~ ~ </span>Doppelt auskommentiert

# Normaler Kommentar

Normaler Text
</pre>

Diese Datei würde, in Code Browser geöffnet, so aussehen:

![Verschiedene Kommentartypen und wie sie in Code Bowser aussehen](screenshots/de/kommentartypen.png)

*Verschiedene Kommentartypen und wie sie in Code Bowser aussehen*

Die Direktiven starten jeweils mit dem sprachspezifische Metazeichen für [Kommentare](https://de.wikipedia.org/wiki/Kommentar_(Programmierung)). In diesem Beispiel ist es das Hash-Zeichen – `#` – von Code Browser standardmäßig verwendet für unbekannte Dateitypen, Text und [Python](https://www.python.org/). Bei Javascript ist es `//`, bei CSS, welches keine einzeiligen Kommentare hat, `/*` am Start der Zeile und `*/` am Ende.

Kommentarzeichen können in der `preferences.cbc` unter *Languages* → *(Sprache)* mit der Variable `line-comment` definiert werden. Oder mit `open-comment` und `close-comment`, wenn die Sprache keine einzeiligen Kommentare besitzt. Wenn alle drei definiert sind, wird `line-comment` bevorzugt.

Direktiven stehen jeweils in einer eigenen Zeile.

Bedeutung der einzelnen Direktiven:

* `#[of]` und `#[cf]` öffnet und schließt eine Sektion (ursprünglich *Folder* genannt). Der Doppelpunkt – `:` – trennt die ID der Sektion (das, worauf Links verlinken) vom Titel der Sektion.
* `#[l]:` kennzeichnet einen Link. Der zweite Doppelpunkt trennt den Titel des Links vom Ziel des Links.

  Die Syntax für Link-Ziele entspricht etwa der von [URLs](https://de.wikipedia.org/wiki/Uniform_Resource_Locator). Wenn das Ziel ein absoluter Dateipfad ist, muss es mit `file:///` starten. Relative Link-Ziele sind auch möglich. Wenn das Ziel eine Sektion ist, hängt man den Pfad zur Sektion mittels Hash-Zeichen – `#` – an den Dateipfad an. Also etwa `file:///<Dateipfad>#<Pfad zur Sektion innerhalb der Datei>`. Wenn sich die Sektion in der selben Datei befindet, kann man den Dateipfad weglassen, so wie in obigem Beispiel.

  Man kann auch auf Zeilennummern verlinken, indem man zusätzlich `?aln=<nummer>` (*absolute line number*) anhängt. Und mehr, siehe Abschnitt *Links* in der Hilfedatei.

  Links erzeugt man am einfachsten mittels `Strg` + `Alt` + `c` – [Siehe Tastenkürzel → Links](#links).
* `#[c]` kennzeichnet eine Beschreibungszeile.
* `#[c](<Leerzeichen>` und `#[c])` öffnet und schließt eine entfaltete Sektion.
* `#[c]~<Leerzeichen>` kennzeichnet eine auskommentierte Zeile.
* `#` kennzeichnet einen normalen Kommentar, der keine besondere Bedeutung für Code Browser oder für meine Benutzerskripte hat.

## Tips und Tricks

* Das von meiner `preferences.cbc` verwendete Farbschema versucht, die folgenden Schriften in dieser Reihenfolge zu verwenden: *[Consolas](https://www.google.com/search?q=Download+Consolas+font)*, *[Lucida Sans Typewriter](https://www.google.com/search?q=Download+Lucida+Sans+Typewriter+font)*, *[Courier New](https://www.google.com/search?q=Download+Courier+New+font)*, *Monospace*. Du kannst diese Schriftarten unter *Themes* → *Basic* ändern (suche nach `font-family`).
* Alle definierten Sprachen – bis auf die Wurzelsprache `Default` – erben Variablen von einer Elternsprache via `prototype = languages.<Elternsprache>`. Man kann diese Variablen in der jeweiligen Sprache ändern, indem man sie einfach dorthin kopiert. `<Name der Variablen> =` setzt die Variable auf Null, sie erbt dann auch nicht von der Elternvariable.
* Wegen eines Bugs in Code Browser kann der Typ der Einrückung nicht dynamisch erkannt werden. Per default **werden Tabs zur Einrückung verwendet**, außer in der Sprache [Elm](https://elm-lang.org/), welche zwei Leerzeichen vorschreibt. Wenn Du stattdessen Leerzeichen für die Einrückung verwenden willst, befolge bitte die Instruktionen unter *Languages* → *Defaults* → *Default* → *Tabs* in der `preferences.cbc`.
* Man kann innerhalb von `*.cbc` Dateien in Namen keine Unterstriche – `_` – verwenden, wohl aber das Trennzeichen – `-`.
* Code Browser beherrscht keine Codevervollständigung. Abhilfe kann das Autohotkey-basierte [Typing Aid](https://github.com/ManiacDC/TypingAid) schaffen.
* Verwende die Paragraphen-Navigation – `Strg` + `Alt` + (`↑` oder `↓`) – um schneller in Code-Dateien zu navigieren.
* Der einfachste Weg einer Sektion eine ID zu verpassen ist sie einmal zu entfalten und dann wieder zusammenzufalten. Das setzt die ID der Sektion mit ihrem Titel gleich.
* Strukturiere Code semantisch nach dem was er tut, nicht was er ist.
* Strukturiere Code wie ein Fraktal. Wenn eine Funktion *B* nur von einer Funktion *A* genutzt wird, füge *B* als Sub-Sektion am Anfang innerhalb der Sektion ein, in der *A* definiert ist. Eine Funktion *C*, die nur von *B* genutzt wird packe dann wiederum in die Sektion von *B*, und so weiter. Verfahre auch mit Klassen und Variablen so.
* Wenn längere Code-Bereiche von einem Kommentar betroffen sind, verwende entfaltete Sektionen.
* Falte längere Code-Abschnitte, die dazu dienen, eine Variable zu füllen, zu einer Sektion und gib dieser Sektion den Namen der Variablen.
* Während des Schreibens von Code falte fertiggestellte Bereiche temporär weg.
* Um auseinanderliegende Code-Bereiche zu vergleichen, füge einen temporären Link zum anderen Code-Bereich ein, so daß Du schnell hin und her wechseln kannst.
* Füge Links zu Kommentaren hinzu, die über woanders liegende Code-Bereiche reden.
* Erstelle Dir eine globale Index-Datei, die Links zu allen Code-Dateien enthält, an denen Du regelmäßig arbeitest. Pinne diese Index-Datei an der Liste an, die aufpoppt, wenn man das Symbol von Code Browser in der Taskleiste rechtsklickt (Um in dieser Liste zu erscheinen muss die Datei in Code Browser mittels *File* -> *Open ...* geöffnet worden sein).
* Falte nicht zu viel. Wenn es auf eine Bildschirmseite passt, reicht es in der Regel.

## Versionshistorie

### Version 1

Erster Commit.

### Version 2

* Habe das Benutzerscript vollständig überarbeitet und einige Bugs gefixt. Die Skripte zum Auskommentieren von Quellcode und Entfalten von Sektionen verwenden jetzt Beschreibungskommentare statt wie bisher normale Kommentare.
* Habe das Farbschema gepimpt. Die Grundidee ist, lokale Variablen blau und predefinierte Variablen/Funktionen Lila anzuzeigen. So kann ein versehentliches shadowing unterbunden werden. Leider ist die Funktionalität etwas beschränkt. Daher wird der Text in normalen Textdateien blau dargestellt.
* Viele Sprachen entsprechend optimiert.
* Viele andere kleine Korrekturen

## Credits

Ein herzlicher Dank an Marc Kerbiquet für [Code Browser](http://tibleiz.net/code-browser/) und [für andere Sprachen, Werkzeuge und Spiele, die er geschrieben hat](http://tibleiz.net/).

Wenn Du hier Fehler findest, bitte eröffne ein [„Issue“](https://github.com/nilslindemann/Code_Browser_49/issues) oder schick´ mir ein [„pull request“](https://help.github.com/en/articles/creating-a-pull-request).

Geschrieben 2019-09-26 von [Nils Lindemann](https://github.com/nilslindemann?tab=repositories). Letzte Aktualisierung: 2020-05-08.
