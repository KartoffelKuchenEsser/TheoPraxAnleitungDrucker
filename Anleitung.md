# Anleitung zum Drucker der Begabten-AG | Chemie des Melanchthon-Gymnsaiums Bretten

## Gliederung

* Vorwort
* Druckerdaten
* Wort Definitionen / Drucklexikon
   * Extruder
   * Filament
   * Gcode
   * Induktiver Druck-Sensor/Sensor
   * Infill
   * Layer
   * Nozzle
   * Skirt
   * Slicer
* Software und ihre Einstellung
   * Software
   * Einrichtung
* Druckeinstellungen
   * Hardware Einstellungen
   * Achsenvorbereitung
   * Leveling
* Drucken
   * Richtige Reihenfolge
   * Qualitätssicherung
* Pflege
   * Aufhängung
   * Achsen
   * Extruderschrauben
   * Ausrichtung
   * Heatbed
   * Höhe
   * Leveling
   * Nachspannen
   * Nozzle
* Druckprobleme und ihre Behebung
   * Filament
      * Filament wechseln
      * Beschädigung des Filaments \(Plastikflocken/Splitter sind zu sehen\)
   * Lücken
      * Lücken und Löcher in den Top Layern
      * Lücken und Löcher in den Ecken am Boden
      * Lücken in den Bottom Layer
      * Lücken zwischen dem Infill und den Outlines
      * Lücken bei Dünnen Wänden \(z.B. Bei Schriftzügen\)
   * Keine / zu geringe Extrusion
      * Keine Ausgabe des Filaments am Anfang des Druckens
      * Beendigung des Extrudens während des Druckens
      * Under Extrusion
      * Over Extrusion
   * Ästhetik
      * Stringing
      * "Blobs und Zits"
      * Rillen in den Top Layern
      * Unterer Teil des Objekts ist eingedrückt
      * Unschöne Überhänge
      * Schlechtes Bridging
      * Elephantenfuß
      * Pillowing
      * Vibration and Ringing
      * Warping
      * Z Wobbles
      * Schlechte Oberflächenqualität bei Supportflächen
   * Layer
      * Verschiebung von Layern in eine Achsenrichtung
      * Trennung von verschiedenen Layern
   * Infill
      * Schwaches / Fehlerhaftes Infill
      * Infill ist von außen zu sehen
* Diverses
   * Thermal Runaway
   * Heating Failed
   * Overheating
   * Verstopfte Düse
   * Sehr kleine Designelemente werden nicht Gedruckt
   * Designelemente werden nicht gedruckt
   * Drucktoleranzen
   * Der Extruder hört nicht auf nach unten zu fahren
* Mögliche Verbesserungen
   * Hardware
      * Software Anpassungen
	 * Verbesserung von Druckobjekten
* Software
   * Skynet
* Materialien

---

## Vorwort

Dieser Text beinhaltet die Betriebsanleitung für den 3D-Drucker "Anet A8"
der Begabten-AG \| Chemie. Der Text behandelt besonders die verschiedenen Probleme,
deren Grund und wie man dies Beheben kann.
Es werden verschiedene englische "Fachbegriffe" verwendet, diese sollten sie
aber recht schnell verinnerlicht haben.

_Kursiv_ geschriebene Absätze sind Kommentare und Erklärungen sie sind **nicht**
essentiell wichtig zu lesen.

_Sie enthalten jedoch hilfreiche Informationen,
die zum besseren Verständnis beitragen_

Und sind immer vom Text abgesetzt.

**Fett** geschrieben Wörter sind extrem wichtig, bei ihnen sollte man **immer**
darauf achten, dass sie korrekt eingehalten sind.

---

### Druckerdaten

Der Drucker ist wiegesagt der Anet A8-Drucker mit verschiedenen
Modifikationen.

* Rollenhalter
* X-Achsen Spanner
* Y-Achsen Spanner
* Filamentführung
* Bed Leveling Sensor \(Induktiv\)

Das Druckvolumen beträgt 220mm\*220mm\*240mm.
Gedruckt wird mit PLA. PLA ist ein Bio-Polymer mit verschiedenen Eigenschaften:

* Biologischabbaubar
  1. Stark korodiert \(nach 50 Jahren bei hoher Sonneneinstrahlung\)
* Poly-Lactid
  1. Herstellung aus Maisstärke
  2. Kein Verbrauch von Erdöl
  3. Lebensmittelecht
* Drucktemperatur von 200 °C
  1. Energiesparender als andere Filamente
* Kein Warping \(Verziehen\)
  1. Anfängerfreundlich
  2. Weniger Fehldrucke
* Günstig
  1. 20€ pro Spule
  2. 2000m bei ca. 1kg

### Wort Definitionen / Drucklexikon

**Extruder:** Er beinhaltet die Nozzle \(siehe Nozzle\) den Sensor \(siehe Sensor\),
und den Schrittmotor \(auch Extrudermotor genannt\).

**Filament:** Das Material mit dem gedruckt wird.
Wird auf einer Spule aufgerollt.

**Gcode:** Die Sprache die jeder Drucker, auf jeden Fall die Open Source,
verwendet kann.

**Induktiver Druck-Sensor/Sensor:** Ein Sensor, der auf metallische
Gegenstände reagiert. Damit kann die erste Layer einfach eingestellt werden,
da der Drucker die 0,1mm Differenz selbs einstellt.

**Infill:** Das Infill ist das Material im Objekt um so geringer die Infill-Zahl
umso geringer ist die Dichte des Objekts.

**Layer:** Englisches Wort für Schicht.

**Nozzle:** Nozzle ist der englische Begriff für Düse.
Sie gibt das geschmolzene Filament aus. Die Nozzle ist während des Drucks extrem
heiß, es ist also Vorsicht geboten.

**Skirt:** Eine Umrandung um alle Druckobjekte, um die Bett-Enfernung
schon frühzeitig zu erkennen und reagieren zu können.

**Slicer:** Ein Slicer ist ein Programm zum Umwandeln einer .STL-Datei,
welche aus vielen Rechtwinkligen Dreiecken besteht,
in eine Gcode-Datei welche von jedem Drucker verwendet werden kann.
Bevor die .STL-Dateien geladen werden können muss man im Slicer
die richtigen Einstellungen eintragen.

## Software und ihre Einstellung

### Software

Um 3D-Dateien drucken zu können, sollte man sich einen geeigneten Slicer zulegen.
Die folgende Anleitung geht vom kostenlosen Open Source Slicer "Cura" aus.
Diesen Slicer würde ich persönlich absolut jedem ans Herz legen,
der nicht hauptberuflich 3D-Druck betreibt.
In diesem Fall wäre Meshmixer die viel bessere Wahl,
dieser ist jedoch kostenpflichtig.

### Einrichtung

Nachdem sie Cura gestartet haben, öffnen sie die "Printer Settings" mit

> Settings&gt;&gt;Printer&gt;&gt;Add Printer

Wählen sie dann "Custom" und drücken sie den Button rechts unten im Fenster
mit der Aufschrift "Add Printer". Vorher sollten sie eventuell links unten
den gewünschten Namen eingeben. Danach öffnet sich das Fenster mit dem Namen
"Machine Settings" hier müssen sie einige Daten eingeben.
Die Korrektheit an diesem Punkt ist sehr wichtig.
Geben sie zunächst das Druckvolumen in mm an.

> X=220mm Y=220mm Z=240mm

Daraufhin geben sie die folgenden Punkte ein:

* Bei "Build Plate Shape" muss "Rectangular" ausgewählt sein.
* Bei "Origin at center" darf **kein** Kreuz sein.
* Bei "Heated Bed" muss wieder ein Kreuz gesetzt werden.

Bei "Gcode Flavour" sollten sie "Marlin" auswählen.
Dies ist das aktuelle Betriebsystem.

Der "Start Gcode" kann aus dem Internet heruntegeladen werden,
oder aber sie fügen diese Zeilen ein:

> G21
> G90
> M82
> M107
> G28 X0 Y0
> G28
> G1 Z15.0 F6000
> G0 X2 Y2 Z2
> G92 E0
> G1 F200 E3
> G92 E0
> G1 F840

Bei den "Printhead Settings" wird überall **0** eingefügt,
bis man zum Punkt "Number of extruders" kommt, dort wird eine **1** eingefügt.
Bei "Material Diameter" : 1,75mm
Nozzle Size : 0,4mm

Bei "End Gcode" wird folgendes eingefügt.

> M104 S0
> M140 S0
> G91
> G1 E-1 F300
> G1 Z+0,5 E-5 X-20 F9000
> G28 X0 Y0
> M84
> G90

Daraufhin können sie, nach abermaliger Kontrolle, auf "Finish" drücken.

### Druckeinstellungen

Auf der rechten Seite wählen sie ganz oben den richtigen Drucker aus.
Darunter bei Material "PLA"
Wählen sie dann "Custom"

Die Folgenden Werte sind einzutragen.

> Layer Height : 0,2mm
> Wall Thickness : 0,8mm
> Top/Bottom Thickness : 0,8mm
> Infill Density : Wird je nach Aufgabengebiet festgelegt.
> Gradual Infill Steps : Wie oben
> Printing Zemperature : 200 °C
> Build Plate Temperature : 60 °C
> Diameter : 1,75mm
> Flow : 100%
> Enable Retraction : "Kreuzchen"
> Print Speed : 50mm/s
> Travel Speed : 120mm/s
> Enable Print Cooling : "Kreuzchen"
> Generate Support : "Wenn erwünscht"
> Build Plate Adhesion Type : "Skirt"
> Print Sequence : "All at Once"

## Hardware-Einstellungen

### Achsenvorbereitung

**Feste Aufhängung**
Nach umstellen des Druckers, oder nach vielen Druckstunden,
sollten sie alle Führungsstangen \(Y-Achse und X-Achse\), das sind die glatten
Stangen, auf wackelfreien Sitz überprüfen.

Wenn eine Stange der X-Achse wackelt,
sollte sie die Feststell-Schrauben \(kleiner Imbus\) auf der Rückseite der rechten
Aufhängung nachziehen, nachdem sie beide Stangen bis zum Anschlag nach links
geschoben haben.

Wenn eine der Y-Achsenstangen wackelt,
sollten sie die Muttern der Gewindestangen \(Am Frontpanel\) lösen und das
Frontpanel bis zum Anschlag nach hinten schieben. Danach drehen sie die
vordersten Muttern solange nach hinten bis alles fest sitzt
und auch absolut nicht wackelt.

**Ausrichtung**
Nun müssen sie die waagerechte Ausrichtung der X-Achse kontrollieren
und eventuell anpassen. Drehen sie von Hand an beiden Achsen-Kupplungen
der Z-Achse so, dass der Extruder vom Heatbed wegbewegt wird. Nehmen sie dann
einen Messschieber zur Hand und messen sie den Abstand zwischen der unteren
Kante der X-Achsen Führungsstange und der oberen Kante der Z-Achsen Motoren.
Messen sie auf beiden Seiten, sodass die X-Achse gerade ausgerichtet ist.

### Leveling

Um einen schönen Druck gewähleisten zu können, muss das Heatbed gelevelt,
also gerade, sein.

**Manuell**
Nehmen sie wieder einen Messschieber zur Hand und messen sie den Abstand,
nahe der Schraube, zwischen Heatbed und Heatbed-Aufhängung.
Schrauben sie dazu die Kontermuttern ab.

_Der Wert ist an sich egal, nur sollten die Schrauben weit genug nach unten
gedreht werden, sodass die Kontermuttern aufgeschraubt werden können,
zu niedrig eingestellt kann es zu Beschädigungen der Platte kommen,
falls der Sensor nicht funktionsfähig ist._

Wiederholen sie diesen Vorgang in diagonaler Reihenfolge,
so lange bis die Werte möglichst nahe beieinander liegen.
Drehen sie nun die Kontermuttern wieder drauf und drehen sie sie fest.

**Automatisches Ausgleichen**
Drücken sie auf "Auto Home"

> Prepare&gt;&gt;Auto Home

Danach drücken sie auf "Level Bed"

> Prepare&gt;&gt;Level Bed

_Damit misst der Druck-Sensor die Entfernung von Sensor und
Heatbed an verschiedenen Punkten. Und gleicht eventuelle Ungenauigkeiten
während des Druckes aus_

## Drucken

### Richtige Reihenfolge

Die 3D-Dateien im .STL Format werden in Cura geladen.

_Es sollten alle Dateien zu Hause erstellt und bearbeitet
werden,
da die Schulrechner eine zu geringe Rechenleistung
aufbringen._

Je nach Druckobjekt kann/sollte "Support" eingeschaltet werden.
Die "Infill" Zahl hängt vom Einsatzgebiet ab. So braucht zum Beispiel
ein Flaschenöffner 25% Infill, mit 25% ist die Stabilität schon extrem stark.
Ein 20mm\*20mm\*20mm Würfel von 25% hält auf jeden Fall 100kg aus.

_Man sieht also, die Stabilität eines Druckobjekts ist auch bei geringem Infill
extrem hoch._

Die restlichen Einstellungen kann man so lassen, besonders die Geschwindigkeiten
sollten so belassen werden, da die Druckqualität darunter leidet.
Sie können aber ansonsten gerne mit den Einstellungen experimentieren.
Legen sie eine Micro SD-Karte ein.
Dann drücken sie auf "Save to removable Drive".

_Wenn dies nicht möglich ist, ändern sie die Infill Zahl \(oder eine andere Zahl\),
dann sliced das Programm die Datei. Ändern sie die Zahl dann wieder zurück.
Das kann manchmal vorkommen, jedoch wird Cura laufend verbessert,
deswegen sollten sie ihre Cura-Version immer aktuell halten_

Danach wefen sie die Micro SD-Karten aus.
Ziehen sie sie heraus und legen sie dann die Speicherkarte
in den Slot des Druckers.

_Wenn sie das Filament wechseln, müssen sie ein paar Dinge beachten.
Genaueres finden sie unter Probleme&gt;&gt;Filament&gt;&gt;Filament wechseln_

Drücken sie auf "Preheat PLA"

> Prepare&gt;&gt;Preheat&gt;&gt;Preheat PLA&gt;&gt;Preheat PlA

Damit heizen sie Bed und Extruder gleichzeitig hoch, wenn sie nur drucken würden
ohne zu Preheaten, dauert es länger, da der Drucker erst Bed
und dann Extruder hochheizt.

Drücken sie jetzt den linken Knopf so oft, bis sie wieder im Statusmenü sind.
Drücken sie dann auf den Namen ihrer Druckdatei.

> Print from SD-Card&gt;&gt;Refresh&gt;&gt;"Datei-Name"

Schauen sie sich den ersten Layer bzw. den Skirt an und beurteilen
sie das Ergebnis. Die nächsten Schritte, die sie eventuell tun sollten,
sind unter "Qualitätssicherung" beschrieben.

Nachdem sie die eventuellen Änderungen vorgenommen haben,
starten sie den Druck nochmal. Ansonsten lassen sie den Druck durchlaufen.

---

Während des Druckvorgangs, besonders bei langzeit Projekten, sollten sie schauen,
ob sich Probleme zeigen oder die Spule fehlerhaft aufgerollt ist, dann sollten
sie möglichst schnell den Roll-Fehler beheben, sonst kann es sein, dass der
Drucker ohne Filament druckt.

---

Danach müssen sie das Objekt vom Heatbed lösen.
Warten sie bis die Heatbed Temperatur unter 40°C gefallen ist.
Ansonsten kann es sein, dass sie das noch plastische Mateial verformt.
Nehmen sie den Rasierklingenhalter oder eine Spachtel zur Hand.
**Drücken sie immer von sich weg, und seien sie vorsichtig.**
Gehen sie mit der Klinge unter eine Ecke des Objekts und fahren sie um das
Objekt herum, sodass es am Rand überall gleich gelöst ist. Entweder es löst sich
davon schon, oder sie gehen mit der Spachtel darunter und gehen gleichmäßig und
ohne Druck unter dem Objekt herum und lösen es dadurch vorsichtig.
Beim ganzen Vorgang halten sie das Werkzeug immer im flachen Winkel, sonst
kann es sein, dass das Objekt dabei kaputt geht.

### Qualitätssicherung

Schauen sie sich den Skirt an und beurteilen sie, ob die erste Schicht
zu hoch oder zu niedrig gedruckt wird.

**Zu hoch**

Die Schicht hält kaum oder gar nicht an der Oberfläche und sieht alles in allem
nicht gut aus.

Gehen sie zur Korrektur auf "Z-Axis offset"

> Settings&gt;&gt;Z-Axis offset&gt;&gt;

Gehen sie nach Gefühl mit dem Wert so weit runter, wie sie denken,
gehen sie nicht zu weit runter.

_Dabei können sie das Heatbed verbiegen_

Wiederholen sie diese Prozedur solange, bis sie auf der richtigen Höhe sind.

**Zu niedrig**

Die Schicht wird überhaupt nicht gedruckt \(könnte auch ein anderes Problem sein:
siehe "Probleme"\) oder ist flach und breit gedrückt. Im Extrtemfall drückt der
Extruder auf das Heatbed, in diesem Fall sollten sie schnellstmöglichst
den Drucker ausschalten und den Extruder von Hand hochfahren.
Danach stellen sie den "offset" höher \(oben bereits beschrieben\).

_Bei einer Layerheight von 0,1mm sollten sie die Höhe \(Offset\) auf 0,75microm
stellen. Da aber der Sensor nicht auf der gleichen Höhe ist wie die Nozzle.
Nehmen sie einen Kassenzettel zur Hand und legen sie ihn \(bei kalter Nozzle\)
unter den Extruder, solange bis man ihn mit etwas Kraftaufwand verschieben kann.
Das ist deshalb möglich, da Kassenzettel eine durchschnittliche Dicke
von 0,1mm hat._

### Pflege

**Aufhängung**: Die Aufhängung sollte regelmäßig nachgezogen werden,
um das optimale Druckergebnis erzielen zu können. Im Extremfall sollte man
die X-Achsen Aufhängungen nachdrucken und austauschen.
Das Nachziehen wird unter:
&gt;&gt;Hardware-Einstellungen&gt;&gt;Achsenvorbereitungen&gt;&gt;Feste Aufhängung.

_Man sollte sie vor einer eventuellen Beschädigung auf Vorrat drucken_

**Achsen**: Die Spindelstangen der Z-Achse und die Führungsstangen der Y-Achse
können mitunter recht laut sein. Deswegen sollte man sie regelmäßig einfetten
und eventuell, vor dem erneuten Einfetten, reinigen. Zum Einfetten tragen sie
geringe Mengen auf beiden Seiten auf, nahe der Kontaktflächen, und nehmen sie den
Drucker wieder in Betrieb.

_Zum Einfetten gibt es sehr gutes Modellbaufett. Es werden nur
sehr geringe Mengen benötigt und es verteilt sich selbst beim Betrieb. Dies ist aber
sehr teuer._

**Extruderschrauben**: Der Extruder ist mit recht vielen Schrauben an seinen
Kugellagern befestigt. Diese sollte man circa alle 500 Druckstunden nachziehen,
da sie sich durch Vibrationen lockern können.

_Zum Nachziehen müssen sie den Schrittmotor abmontieren. Lösen sie die Schraube
auf der Unterseite der L-Platte, und ziehen sie den Schrittmotor, samt Nozzle,
zur Seite heraus_

**Ausrichtung**: Die Ausrichtung sollte regelmäßig kontrolliert und
ggf. korrigiert werden. Der Prozess ist erklärt unter:
&gt;&gt;Hardware-Einstellungen&gt;&gt;Achsenvorbereitung&gt;&gt;Ausrichtung.

**Heatbed**: Das Heatbed ist eine Aluminium-Platte mit Heizstreifen
auf der Unterseite. Dort befindet sich auch eine LED, die den Status
des Heatbeds anzeigt. Auf dem Heatbed ist ein Adhäsions-Pad aufgeklebt,
welches die Haftung des Druckobjekts während des Drucks verbessert und
das Ablösen nach dem Druck unterstützt.
Wenn sich PLA Reste auf dem Pad befinden,
schaben sie diese mit einer Spachtel ab.
Falls das Pad zu stark, durch die Nozzle,
beschädigt wurde, sollten sie es austauschen.
Dazu ziehen sie das Pad ab und reinigen die darunteliegende Fläche
mit Scheibenreiniger. Danach kleben sie ein neues Pad auf.

**Höhe**: Die Höhe sollte bei jedem Druck neu kontrolliert und korrigiert werden,
um einen guten Druck und erste Layer zu erreichen.
Die Höhenkalibrierung wurde schon erklärt.
Unter: &gt;&gt;Drucken&gt;&gt;Qualitätssicherung

**Leveling**: Das Leveling wurde in einem vorherigen Abschnitt erklärt.
Sie sollten es, auf jeden Fall das automatische, regelmäßig wiederholen.
Den Artikel finden sie unter.
&gt;&gt;Hardware-Einstellungen&gt;&gt;Leveling

**Nachspannen**: Das Nachspannen der Riemen ist essentiel wichtig,
um ein gleichmäßiges Druckergebnis zu gewährleisten.
Dazu wird am eingebauten Y-Achsen Spanner leicht gedreht,
bis sie es als gespannt erachten.
_Drehen sie nicht zu stark_

Um die X-Achse zu spannen, drehen sie mit einem Schraubendreher
die Spannschraube, am weißen Riemenspanner, weiter nach unten.
Wenn der Riemenspanner an seine Grenzen kommt, sollten sie den gesamten
Riemen nochmal neu spannen.

Dazu entfernen sie die Kabelbinder am Riemen und spannen den Riemen nach.
Danach befestigen sie den Riemen mit zwei neuen Kabelbindern
_Achten sie dabei darauf, dass die Kabelbinder nahe am Ankerpunkt liegen_
Im Extrtemfall sollten sie sich einen neuen Riemen zulegen, da der Jetztige zu
ausgeleiert sein kann.

Kontrollieren sie die Spannung alle 200 Druckstunden.

**Nozzle**: Bei langen Idle-Zeiten mit aufgeheiztem Extruder kann es dazu kommen,
dass sich das Filament chemisch zersetzt und verbrennt und damit die Nozzleöffnung
zusetzt.

Zum Reinigen der Nozzle holen sie sich ein kleines Behältnis mit
einer kleinen Menge Tetrahydfrofuran _Vorsicht: Brennbar_.
Einen Bunsenbrenner und einen dünnen Metaldraht.
Legen sie die abmontierte Nozzle in das Gefäß und lassen sie es einwirken.
Nehmen sie dann die Nozzle heraus und legen sie sie zum trocknen auf ein Tuch.
Zünden sie nun den Bunsenbrenner an und erheizen sie die Nozzle bis zur Rotglut.
Nehmen sie dann den Draht und stecken sie ihn in die Nozzleöffnung von beiden
Seiten, bis sie sicher sind, dass die Nozzle komplett frei ist.
Legen sie die Nozzle dann zum Abkühlen auf eine feuerfeste Unterlage und
montieren sie die Nozzle wieder am Extruder.

## Druckprobleme und ihre Behebung

### Filament

**Filament wechseln**:

Die Nozzle kann gerne mal beim wechseln des Filaments das Filament abreißen und
die Nozzle verstopfen.

Zum reinigen bauen sie den Extrudermotor aus und legen sie ihn samt
Extruder-Lüfter zur Seite.
Heizen sie die Nozzle auf 240 °C hoch.

> Prepare&gt;&gt;Preheat ABS

Nehmen sie einen dünnen, spitzen Gegenstand zur Hilfe und drücken sie das
Filament durch die Nozzle, sodass es am anderen Ende herauskommt.
Nehmen sie dann ein Stück Filament und schieben es hinterher.
Ziehen sie dann das Filament in einer flüssigen Bewegung wieder heraus,
und setzen den Extruder wieder zusammen.

Wenn dies noch nichts genützt hat, 
nehmen sie eine Kanüle, Kanülen eignen sich besonders gut, da sie sehr dünn sind bei gleichzeitiger relativ hoher Stabilität,
sie sollte ungefähr so lang oder länger sein wie der Heizblock.
Fühern sie die Nadel von unten ein und prüfen sie ob sich dort eine Verstopfung befindet.
Wenn der untere Teil frei zu sein scheint. Nehmen sie eine Dickere, und vorallem stabile Nadel, 
und fühern sie von oben in das Hotend ein.
Wenn sich die Verstopfung nicht gelöst zu haben scheint, und das erhitzen auf 240°C, positionsbedingt, nichts bringt. 
Dann nehmen sie eine Zange und halten das ausmontierte Hotend fest, erhitzen sie nun den Gewindeteil in dem sie die Verstopfung vermuten
mit einem Feuerzeug für ungefähr 15s und schieben sie dann die Nadel hinein. Dabei sollte sich die Verstopfung lösen und in einer stark
flüssigen Konsistenz aus der Düse ergießen.

<b>Achtung, Warnhinweis! folgender Textabschnitt dient nur zu Informationszwecken. 
Wir übernehmen keine Haftung für Sach- oder Personenschäden!</b>

Wenns sich diese Versopfung weiterhin nicht gelöst hat, oder die Düsen-Innenwände eine 
Ablagerung aus Filament sich zu Eigen gemacht haben. Haben sie entweder Glück, wenn sie ABS benutzt haben, dann können sie die Düse vom
Heizblock und dem Hotend lösen und das Hotend, einzeln (ohne Heizblock), in Aceton einlegen. 
Danach sollten sie die Teile schnell ausspülen. 
Aceton ist zwar giftig und leicht entzündlich, aber vergleichsweise ungefählich wenn wir uns die gleiche Lösung für PLA anschauen.
Die PLA-Lösungsmittel, wie Aceton auch, nur unter Aufsicht einer Lehrkraft verwenden.
Beim PLA-Lösungsmittel, Methylenchlorid, handelt sich um einen vermutlich Krebs erregenden Stoff.
Er reizt Augen,Haut und Atemwege. Die Prozedur sollte unbedingt in einem funktionstüchtigen Abzug erfolgen.
Führen sie die gleiche Prozedur wie mit Aceton durch.

**Beschädigung des Filaments \(Plastikflocken/Splitter sind zu sehen\)**:
Wenn dies geschieht kann man einige charakteristische Dinge sehen:
Es haben sich Flocken gebildet, die entweder auf dem Extruder  
oder darunter liegen und aus dem Extruder-Bereich zu fallen scheinen.

Dabei ist das Problem, dass die Extruder-Düse verstopft ist und der Extruder mit seienem
Zahnrad die Splitter vom Filament abschabt und dabei dieses durchaus durchtrennen kann. 
Die Folgen davon können sein, dass das Filament unterbrochen ist und es zu ghosting kommt.

Wenn dies geschehen ist, durchtrennen sie das Filament, oder kürzen sie es auf die Düsenhöhe,  
folgen sie danach den Instruktionen bei "Filament wechseln".


### Lücken

**Lücken und Löcher in den Top Layern**
Wenn die oberste Schicht des Druck-Objekts Lücken aufweist, kann dies verschiedene Folgen haben:

1. Es kann daran Liegen, dass die Top-Schicht in Cura zu gering eingestellt wurde. 
Als Lösung kannst du die "Top Layer" Einstellung höher stellen.

2. Es kann daran liegen, dass die Infill Zahl zu gering ist. 
Als Lösung kannst du die "Infill" Zahl höher stellen.

3. Es kann daran liegen, das die Nozzle zu wenig Plastik ausscheidet.
Schaue für eine Lösung unter "Under Extrusion".

**Lücken und Löcher in den Ecken**
Wenn die Ecken und Umkehrpunkte beim Druck-Objekt nicht mit anderen Punkten abschließen,  
kann es daran liegen, dass es eine Under Extrusion ist.  
Für eine Lösung schauen sie unter Under Extrusion. 


**Lücken in den Bottom Layer**
Dabei kommt es zu keinem guten Abschluss bei der ersten Schicht.
1. Sie müssen das Leveling neu machen.
2. Es handelt sich um einen temporeren Fall von Underextrusion,  
der sich beim Druck selbst gelöst hat.


**Lücken zwischen dem Infill und den Outlines**

1. Sie drucken zu schnell. Stellen sie die Druckgeschwindigkeit runter
2. Es handelt sich um eine Under Extrusion. Sehen sie Under Extrusion
3. Es ist beides.

**Lücken bei Dünnen Wänden \(z.B. Bei Schriftzügen\)**
Zwischen den Wänden herscht leere.

1. Es handelt sich um eine zu geringe Extrusion Dicke. Stellen sie die Extrusion höher.
2. Es handelt sich um eine zu hohe Wanddicke. Ändern sie sie in Cura.

### Keine / zu geringe Extrusion

**Keine Ausgabe des Filaments am Anfang des Druckers**
Es könnte sein, dass die Düse verstopft ist, oder die Drucktemperatur zu niedrig eingestellt ist.  
Oder der Z-Offset ist zu niedrig eingestellt.

1. Nehmen sie eine sehr feine Nadel (kleiner als 0,4mm) und lösen sie die Verstopfung.
2. Stellen sie in CUra die Drucktempereatur um 5°C höher, solange bis das Filament genügend fließt.
3. Die Wahrschnlichste Lösung. Stellen sie mit der vorher erklärten Methode  
(Einstellen des Druckers) den Z-Offste niedriger, sodass der Abstand zwischen Düse und Heatbed größer wird.

**Beendigung des Extrudens während des Druckers**
Es könnte sein, dass die Düse verstopft ist. Dies kann verschiedene Gründe haben.

1. Die Temperatur ist an sich zu niedrig eingestellt.
Als Lösung gehen sie in die Cura Print-Einstellungen und stellen sie die Temperatur um 5°C schrittweise nach oben,  
bis das Problem gelöst ist und das Filament dauerhaft und gleichmäßig fließt. Dieses Problem ist bei der Art des  
Problems jedoch unwahrscheinlich.
2. Die Temperatur ist kurzzeitig abgefallen.
   Dadurch ist das Filament in der Düse ausgehärtet und blockiert das Drucken.
3. Die Temperatur ist über einen Zeiraum von über 45s abgefallen.
   Dadurch wurde der Druck abgebrochen um die Sicherheit zu gewähr leisten.
   Dabei wird auch eine Fehlermeldung ausgegeben: "Thermal Runaway".
   Dazu finden sie weiteres unter dem Punkt Diverses.

**Under Extrusion** 
Die Filament-Reihen sind zu dünn und es sieht so aus, als ob Löcher im Druckobjekt sind.

1. Der Filamentdurchmesser ist zu klein.
Dies kan nur passieren wenn sie eine Düse im Bereich von über 1mm Durchmesser und dabei einen Filament Durchmesser von
1,75mm bei behalten wird. Alternativ kann man das Filament zu einem Durchmesser von 3,85mm wechseln.
Oder man wechselt zu einer anderen Düse, eine 0,4mm Düse wäre zu empfehlen.
Auch die 0,4mm Düsen sollte man alle 20.000 Druckstunden austauschen.

2. Die Flow-Rate ist zu niedrig. 
Gehe sie in die Cura Print Einstellungen und stellen sie den Wert solange höher bis sie ihn angepasst haben.

**Over Extrusion**
Die Filament Reihen sind zu dick, und das Filament "quillt" über.
1. Sie haben eine zu hohe Flow-Rate bei zu niedriger Druckgeschwindigkeit.
Stellen sie die Flow-Rate runter und oder stellen sie die Druckgeschwindigkeit hoch.

### Ästhetik

**Stringing**
Das Druckobjekt zeigt unansehnliche feine Fäden auf. Dabei wird das zu flüssige Filament beim Traveln über das Objekt verteilt.

1. Die Temperatur ist zu Hoch eingestellt.
Je nach Filament gibt es eine andere geeignete Drucktemperatur.
Stellen sie die Temperatur um 5°C Schritte runter bis das stringing aufhört. 

2. Die Temperatur ist zu Hoch eingestellt.
Nehmen sie einen Heisluftfön und schwenken sie ihn kurz über das Druckobjekt.
Dabei müssen sie sorgfältig arbeiten, sodass sie das Objekt nicht schmelzen.
Dabei "verbrennen" die kleinen Strings.

**"Blobs und Zits"**
Blobs oder Zits, sind kleine, dickere Unregelmäßigkeiten in der Äußersten Schicht.
Sie entstehen durch das Neuansetzen an dem Punkt und stellen eine Unregelmäßigkeit dar und sind 
gleichzeitig eine punktuelle Over-Extrusion.

1. Dieses Problem lässt sich durch die Benutzung von Simplify 3D (Slicer) beheben. Da wir diesen kostenpflichtigen Slicer nicht besitzen.
Können wir ihnen die Lösung zu diesem Problem nicht geben.

**Rillen in den Top Layern**
Das Problem beschreibt sich selbst durch den Namen: In der obersten Schichten befinde ishc regelmäßige Rillen.

1. Die allgemeine Layerheight ist zu niedrig, dadurch drückt die Düse auf das vorher gedruckte Filament.
Erhöhen sie die Layerheight in Cura.

2. Die Top/Bottom thickness ist zu niedrig, dadurch drückt die Düse auf das vorher gedruckte Filament.
Erhöhen sie die Top/Bottom thickness.

**Unterer Teil des Objekts ist eingedrückt**
Der untere Teil eines Druckobjekts ist eingedrückt(eingebrochen).

1. Die Heatbed Temperatur ist zu hoch eingestellt.
Stellen sie die Heatbed Temperatur in Cura runter.

**Unschöne Überhänge**
Überhänge sind nicht gedruckt oder sehen unsauber aus.

1. Es werden keine Support Verstrebungen gedruckt.
Stellen sie in Cura den Support ein und nehmen sie die Einstellung "Everywhere"

**Schlechtes Bridging**
Verbindungen ohne Support zu einer anderen Säule ist durchhängend und nicht sauber gedruckt.

1. Der Printspeed ist zu schnell, dadurch wird das Bridging unsauber.
Stellen sie den Printspeed in Cura um 20mm runter.

**Elephantenfuß**
Die unteren Schichten des Objekts wölben sich nach außen, weil das Gewicht die unteren Schichten zusammendrückt.

1. Die Heatbed Temperatur ist zu hoch.
Stellen sie die Heatbed Temperatur runter.

**Pillowing**
Über den Punkten bei denen siche kein Infill darunter befindet, senkt sich die Obefläch deutlich ab.

1. Die Kühlung ist zu niedrig oder es wurde gar nicht gekühlt.
Stellen sie die Kühlung an oder stellen sie sie hoch.

2. Die Oberfläche ist zu dick.
Rechnen sie die Schichtdicke und die Top thickness so dass die oberste Schicht mindestens 8 Layer dick ist.

**Vibration and Ringing**
Es bilden sich regelmäßige Muster in der Wand des Druckobjekts.

1. Sie drucken zu schnell durch das spezifiesche Druckmuster bilden sich die diese regelmäßigen Unregelmäßigkeiten.
Stellen sie in Cura die Druckgeschwindigkeit runter.

**Warping**
Die Ecken des Druckobjekts wölben sich nach oben.

1. Das Heatbed ist garnicht oder zu gering beheizt.
Stellen sie die Heatbed Temperatur hoch.

**Z Wobbles**
Dabei hat das Druckobjekt auf der Z-Achse regelmäßige Verschiebungen, sie haben Ähnlichkeit mit kleinen Wellen.

1. Das Druckobjekt wackelt, da es zu hoch wird und ein zugeringes Infill hat und es dadurch instabil wird.
Stellen sie die Infill-Zahl in Cura hoch.

2. Das Heatbed wackelt zu sehr beim Druck. 
Wechseln sie zu einer leichteren Heatbedhalterung.

3. Das Heatbed reagiert zu verzögert.
Spannen sie den Y-Achsen-Riemen nach.

**Schlechte Oberflächenqualität bei Supportflächen**
Bei der ehemaligen Kontaktfläche von Support und Oberfläche sind unschöne Unebenheiten zu sehen.
Wenn sie ABS benutzt haben , können sie das gesamte Objekt mit Aceton bedampfen und die Layerübergänge so glätten, 
dabei glättet man auch gleichzeitig die Unebenheiten die durch das Supportmaterial hervorgerufen wurde.
Alternativ können sie die Unebenheiten mit einem scharfen Skalpell abschaben.

### Layer

**Verschiebung von Layern in eine Achsenrichtung**
Wenn sie z.B. einen Würfel drucken und der obere Teil nicht auf dem unteren Teil sitzt, sondern daneben. 
Haben sie folgende Probleme: 

1. Die Riemen sind nicht richtig gespannt.
Spannen sie die Riemen nach.

2. Das Heatbed ist nicht richtig befestigt.
Befestigen sie die Platte wieder an dem Riemen und oder am Heatbed selber.

3. Bei nich gerader Achsenverschiebung kann es bei anderen Druckern sein, dass eine Z-Achse nicht ganz gerade ist.
Dieses Problem sollte nicht beim Anet A8 auftreten, andernfalls achten sie auf die parallelität.

**Trennung von verschiedenen Layern**
Das Druckobjekt hat größere Risse.

1. Die verschiedenen Layer kühlen unterschiedlich stark aus.
Erhöhen sie die Extruder Temperatur und oder die Heatbed Temperatur.

### Infill

**Schwaches / Fehlerhaftes Infill**
Das Infill ist eingebrochen. Dies kann mehrere Gründe haben.

1. Die Infilldicke ist zu klein eingestellt.
Wie man diese Einstellung ändert entzieht sich unserem Wissensbereich. Vermutlich ist dies bei Cura nicht möglich.

2. Die Infillzahl ist zu niedrig
Stellen sie sie hoch.

**Das Infill ist von außen zu sehen**
Wie gesagt kann man das Infill von außen sehen. Dabei ist die Außen-Wand zu dünn. 
1. Stellen sie in Cura die Wanddicke hoch.


### Diverses

**Thermal Runaway**
Nach längerem Druck oder Aufheizen, kommt die Fehlermeldung "Thermal Runaway", dabei wird das Aufheizen 
abgebrochen um das Gerät vor einem fehlerhaften Aufheizen und folgendem Kabelbrand zu schützen, hierbei trifft 
der Satz zu: "Das ist kein Bug, sondern ein Feature!"
Das passiert dann wen der Thermistor(Wärmesensor) aus dem Düsen-Block gefallen ist, oder die Umgebungstemperatur
unter 20°C-22°C gefallen ist, dabei hat das Netzteil nicht genug Leistung um das Heatbed und oder den Extruder 
aufzuheizen. Dann wird das Drucken aus Sicherheitsgründen abgebrochen.

Heizen sie zur Lösung den Raum auf, oder drpcken sie den Thermistor wieder hinein.
Trotz Thermal Runawy kann es sein das der Heatbedkabelstecker am Plus oder Minuspol durchschmort.
Tauschen sie bei Bedarf das Kabel und prüfen sie das Heatbed per Durchgangsprüfer auf Funktionstüchtigkeit.
Bei einer Neuvekabelung des Kabels gibt es die Empfehlung das Kabel per Mosfet anzuschließen und oder die anderen Litzen zu nutzen, 
und die anderen ungenutzten Kontakte des Heatbeds anschließen um so die Ampere-Belastung niedrig zu halten. 

**Heating Failed**
Nach kurzem Aufheizen, bzw. dem Versuch, kommt es zum Abrruch des Vorgangs und zur Ausgabe der Fehlermeldung "Heating Failed".
Dabei wird vom OS erkannt, dass das Aufheizen eines Teils, Bed oder Extruder, nicht funktioniert hat.

1. Der Sensor ist rausgefallen, und misst deshalb falsche Messwerte.
Um das Problem zu beheben, müssen sie den Sensor, das ist eine ganz kleine "Glasperle", wieder in das untere kleine Loch schieben.
Im gleichen Zug können sie dann die Heizpatrone fixieren. Dafür müssen sie auf der Unterseite 
des Heizblocks eine kleine Schraube festziehen.

2. Wenn der Punkt eins nicht zutrifft sollten sie beim Aufheizen die Temperatur des Heatbeds beobachten, und, bei zu langsamer Erwärmung,
Die Stromkabel zur Wärmeversorgung aufsplitten und sie an den jeweiligen Kontakten (minus und minus, plus und plus) festlöten.
Da es wie bei "Thermal Runaway" dazu gekommen sein kann, dass der Heatbed-Stecker durchgeschmort ist, und dadurch die Leistung des Beds
stark herabsetzt. Durch das anlöten konnte ich persöhnlich eine, eventuell subjektive, schnellere Aufheizung beobachten.

**Der Extruder hört nicht auf nach unten zu fahren**
Wenn der Extruder nach unten fährt, und auf das Druckbett fährt und gleichzeitig das Druckbett verbiegt,
dann solltensie schnell das Gerät vom Strom trennen (ausschalten).

Dann ist der Leveling-Sensor kaputt oder das Sensor-Kabel hat sich durch mechanischen Einfluss gelöst.
Wenn sie den Drucker umstellen oder andere mechanische Dinge daran ändern, kontrollieren sie vor in Betrieb nahme, 
dass alle Sensor und Motorkabel korrekt angeschlossen sind.

Wenn dies nicht der Fall ist, ist vermutlich der Sensor oder das Mainboard kaputt. 
Tauschen sie eins oder beides davon aus.

**Overheating**
Wenn der obere Teil, der der ganze Teil des Druckobjekts verzogen ist, dann
ist das Druckobjekt zu heiß. Es kann nixht abkühlen und wird immer weiter erhitzt, 
bis das Objekt nur noch undefinierte Dinge druckt die komplett verzogen sind.

**Verstopfte Düse**
Wenn das Filament überhalb der Düse herausquillt, dann ist vermutlich die Düse verstopft.
Nehmen sie eine sehr dünne Nadel und erhitzen sie sie. Drücken sie sie von unten in die herausmontierte Düse 
um die Verstopfung zu lösen.
Wenn sie ABS nutzen können sie es mit einem Bad in Aceton versuchen.

**Sehr kleine Designelemente werden nicht Gedruckt**
Dabei werden die feinen Elemente des Druckobjekts nicht gedruckt.
Das liegt daran, dass diese Elemente von Cura ignoriert werden, 
da sie zu klein sind und die Genauigkeit des Druckers unterschreiten würden.

Wenn sie diese Element unbedingt haben wollen, skalieren sie das Objekt hoch,
sodass die Elemente gedruckt werden.

**Drucktoleranzen**
Die Drucktoleranz des Druckers hängt davon ab wie gut die Schienen geölt und die Kugellager freigängig sind
und wie gut die Riemen gespannt sind.

Dabei hat auch das Gewicht des gesamten Extruders Einfluss auf die Druckgeschwindigkeit und die Toleranz,
je leichter der Extruder, wird desto schneller und genauer kann man im Endeffekt drucken.


## Mögliche Verbesserungen

#### Hardware
Mann kann die Kabel des Extruders und des Heatbeds an das Mainboard löten.
Dabei bindet man am besten den Optokopler des (aktuellen) Leveling-Sensors ein,
falls dieser einen Optokopler benötigt.
Wenn sie jedoch einen Sensor benutzen der eine eckige charakteristische Spitze hat und keine metallene Hülle,
müssen sie die Kontakte des Sensors (n und p) abzwicken und gewechselt erneut anlöten.
Dann Tauschen sie den Z-Achsen Sensor pin mit dem des Level-Sensors aus.

Man kann auche einen anderen Extruder benutzen.
Denn Bowden-Extruder, dieser Extruder kann die Genauigkeit und Geschwindigkeit des Druckers rapide Erhöhen. 
Jedoch wird das Wechseln des Filaments eine kleine Herausforderung werden, da man das Filament durch einen kleinen Pneumatik-Schlauch 
bringen muss.
Im Internet gibt es zahlreiche kompetente und deutlich fachlich versiertere Anleitungen, auch mit Video, die den Einbau 
deutlich besser erklären können als wir.
Soviel sei gesagt, das man dazu den Extruder kaufen muss, und vorher eine passende Halterung dafür Drucken sollte.
Wenn sie die Halterung dafür optimiert haben, sollten sie diese zur Sicherheit vordrucken, denn wenn diese bricht, 
was schonmal passieren kann, haben sie keine weder eine direkte Möglichkeit weiter zu drucken, noch die Möglichkeit eine neue Halterung
zu drucken.

Um die gesamte Stabilität des Druckers zu verbessern, und damit auch die Druckqualität, kann man Verstärkungen für die Verstrebungen drucken und so den Relativ instabilen Anet A8 Drucker stabilisieren.

##### Software Anpassungen
Zurzeit (26.04.2018) ist das neuste, und damit meiner Meinung nach beste, SkyNet 3D-Drucker OS auf dem Drucker installiert, persönlich würde ich empfehlen, nachdem sie den Offset extern gespeichert haben, das Betriebssystem alle 6 Monate upzudaten.

#### Verbesserung von Druckobjekten

Man kann verschieden Kunststoffe mit verschieden Chemikalien verschönen.

<b>Achtung, Warnhinweis! folgender Textabschnitt dient nur zu Informationszwecken. 
Wir übernehmen keine Haftung für Sach- oder Personenschäden!</b>

ABS-Objekte können mit Aceton bedampft werden.
Dabei gehen die Übergänge zwischen den Layern verloren, was eine Spritzguss-Optik erzeugt.

PLA-Objekte können mit Methylchlorid bedampft/poliert werden, der Effekt ist der gleiche wie bei Aceton.

#### Software

##### SkyNet
Standartmäßig ist auf unserem Anet A8 Drucker SkyNet als Software installiert. Falls diese Software noch einmal neu aufgesetzt werden muss, kann man sie unter der GitHub Seite https://github.com/thijsk/Skynet3d herunterladen. Dabei befindet sich auch eine geupdatete Anleitung zum Flashen des Betriebssystems.

#### Materialien

| Name | PLA | ABS | PVA |
| :--- | :--- | :--- | :--- |
| **Vollständiger Name** | Polylactide | Acrylnitril-Butadien-Styrol- Copolymere | Polyvinylalkohol |
| **Preis \(in €/kg\)** | 20 | 20-40 | ca. 100 |
| **Gefahrenbezeichung \(Kennbezeichnung\)** | keine | Reizend \(Xi\) | keine |
| **Eigenschaften** | biologisch abbaubar | hohe Belastbarkeit | wasserlöslich \(Druck von Stützmaterialien\) |
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />Dieses Werk ist lizenziert unter einer <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Namensnennung - Nicht-kommerziell - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz</a>.
