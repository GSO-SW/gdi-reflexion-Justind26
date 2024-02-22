[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/OwH8KTXH)
# GDI+
Eine Sammlung von Tipps und Tricks zum Thema Grafikprogrammierung mit GDI+.

## Klassen / Ereignisse
### Timer
Ein Timer führt in regelmäßigen Abständen ein `Tick`-Event aus. Der [`System.Windows.Forms`.`Timer`](https://learn.microsoft.com/de-de/dotnet/api/system.windows.forms.timer?view=windowsdesktop-8.0&viewFallbackFrom=net-6.0) kann über die Toolbox auf die GUI gezogen werden. 

Anschließend können wir 
- die Zeit zwischen jedem `Tick`-Event einstellen (`+ Interval { get; set; }: int`) und
- den Timer starten (`+ Start():void`) oder
- stoppen (`+ Stop():void`) oder
- den Zustand abfragen. (`+ Enabled{ get; set; }: bool`) (Standard ist ausgeschaltet: `enabled = false`)



## Tipps und Tricks
Ergänzen Sie hier die notwendigen Code-Ausschnitte, um zu zeigen, wie man es macht. 
- Sie können [CodeBlöcke mit Syntax-Highlighting](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks#syntax-highlighting) einsetzen
- Wird es zu unübersichtlich? Sie können auch Unterordner mit Beispiel-Code anlegen und auf die entsprechenden Dateien verlinken. [Inspiration](https://github.com/gsoTH/flaskShowcase/tree/master/datenbanken).
- Die folgende Liste kann gerne ergänzt werden :)

### Bewegung animieren
Mit DoubleBuffered kann man die Bewegung etwas besser aussehen lassen, da man das ganze dann schon vor Rendern kann.
Ansonnsten kann man die Bewegung machen, indem man bei dem Objekt die X und Y Koordinate anpasst.

### Objekte mit Tasten steuern
Wenn man ein KeyDown Event hat dann kann man mit dem folgendem Code die Eingabe Taste prüfen:
~~~
if (e.KeyCode == Keys.D)
{
    spieler.X = spieler.X + breiteJeBereich;
    soundPlayer.Play();
}
~~~
In diesem Beispiel prüfe ich ob die Taste "d" gedrückt wird und dann wird der Spieler etwas nach Rechst bewegt.

### Verhindern, dass ein Spieler aus dem Bild läuft
~~~
if (spieler.X  <=0)
{

    spieler = new Rectangle(breite - this.ClientSize.Width, spieler.Y, 30, 30);


}
~~~
Hier wird geprüft ob der Spieler aus der Linken Bande versucht raus zu laufen und dann wird der Spieler wieder auf die Startposition gesetzt.

### Spiel pausieren
Man könnte um das Spiel zu pausieren Console.ReadLine an einer Stelle einbauen, wenn zum Beispiel Escape gedrückt, dann wartet er auf einen weiteren Input und dann läuft das Spiel weiter.

### Ihr schönstes Ergebnis
Mir fällt spontan ein, dass ich die Bewegung auf die WASD tasten erweitert habe.
~~~
 if (e.KeyCode == Keys.W)
 {
     spieler.Y = spieler.Y - hoeheJeBereich;
     soundPlayer.Play();
 }

 if (e.KeyCode == Keys.S)
 {
     spieler.Y = spieler.Y + hoeheJeBereich;
     soundPlayer.Play();
 }

 if (e.KeyCode == Keys.A)
 {
     spieler.X = spieler.X - breiteJeBereich;
     soundPlayer.Play();
 }

 if (e.KeyCode == Keys.D)
 {
     spieler.X = spieler.X + breiteJeBereich;
     soundPlayer.Play();
 }
 ~~~




