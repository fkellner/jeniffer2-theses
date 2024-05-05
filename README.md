# Masterarbeiten über Jeniffer2

Untenstehend die Abstracts der jeweiligen Arbeiten, die in diesem Ordner enthalten sind:

## Eugen Ljavin, 2020

Digitale Aufnahmen werden von Bildsensoren aufgezeichnet und häufig in Form von
unverarbeiteten Sensordaten gespeichert. Dazu existieren sogenannte RAW Formate,
bei den es sich um proprietäre Dateiformate handelt. Eine Ausnahme bietet das
offen spezifizierte Digital Negative (DNG), das ein nicht proprietäres RAW Format
ist. Um aus den Sensordaten eine Aufnahme zu erhalten, müssen RAW Formate
von RAW Konvertern verarbeitet werden und durchlaufen dazu eine Vielzahl von
Verarbeitungsschritten. Von besonderer Bedeutung ist dabei ein Verarbeitungsschritt,
der Demosaicing genannt wird. Dieser kann vom Java Extended NEF Image File
Format Editor (JENIFFER), einem Open Source RAW Konverter, beeinflusst werden.
JENIFFER unterstützt jedoch nur das Nikon Electronic Format (NEF), ein proprietäres
RAW Format des Herstellers Nikon.

In der vorliegenden Arbeit wurde das DNG Format in Bezug auf die RAW Konver-
tierung analysiert und es wurde auf Basis von JENIFFER ein RAW Konverter für
die Verarbeitung von DNG Dateien entwickelt. Dazu wurden zunächst in einem
theoretischen Teil die Dateistruktur, die Verarbeitungsschritte und die Erzeugungs-
möglichkeiten von DNG Dateien an einem laufenden Beispiel untersucht. Gezeigt
wurde, dass verschiedene Dateistrukturen, unterschiedlich kodierte Sensordaten
sowie diverse Verarbeitungsschritte beim Auslesen und Verarbeiten von DNG Da-
teien berücksichtigt werden müssen. Ferner wurden Charakteristiken des DNG
Formats identifiziert, welche dessen herstellerübergreifende Nutzung ermöglichen.
Auf Grundlage der Analyse konnten in einem darauffolgenden praktischen Teil
Komponenten zum Auslesen und Verarbeiten von DNG Dateien einschließlich
einer grafischen Benutzeroberfläche implementiert werden. Abschließend wurden
mehrere Vergleiche durchgeführt, um die Auswirkungen des Demosaicings auf die
Qualität einer digitalen Aufnahme zu veranschaulichen sowie die Ausführungs-
zeiten unterschiedlicher Verarbeitungsschritte zu erörtern. Aus diesen geht hervor,
dass die Pixelwiederholung der schnellste der vier implementierten Demosaicing
Algorithmen ist, jedoch die schlechtesten Ergebnisse erzeugt. Deutlich länger braucht
die bikubische Interpolation, erzielt jedoch die vergleichsweise besten Ergebnisse.

## Andreas Reiter, 2023

<details>
<summary>Zusammenfassung von s.o.</summary>
Aufnahmen von digitalen Kameras werden oft zu fertigen Bildern verarbeitet, oh-
ne zusätzliche Einflussnahme des Nutzers. Mit RAW-Formaten kann eine digitale
Aufnahme nahezu unverarbeitet abgespeichert werden. Die meisten RAW-Formate
sind allerdings proprietär. Dies trifft nicht auf das Digital Negative (DNG)-Format
zu. Dieses Format ist öffentlich dokumentiert und mit einem kostenlosen Konver-
ter können andere RAW-Formate in das DNG-Format überführt werden. Um eine
Aufnahme im DNG-Format in ein fertiges Bild zu überführen, wurde Java Exten-
ded NEF Image File Format Editor (JENIFFER) 2 entwickelt. Dieses Programm
ermöglicht eine transparente Verarbeitung des Bildes, im Gegensatz zu vielen kom-
merziellen Anwendungen.

Digitale Kamerasensoren sind in der Regel monochrom und können deswegen nur
Graustufenbilder erzeugen. Um ein Farbbild zu erzeugen, müssen in jedem Bildpunkt
drei Farbwerte vorhanden sein. Dazu wird am häufigsten das Bayer-Mosaik verwen-
det. Das Bayer-Mosaik besteht aus sich wiederholenden Blöcken aus vier Farbfil-
tern, einmal für die Farben Rot, zweimal Grün und einmal Blau. Die fehlenden zwei
Farbwerte in jedem Bildpunkt müssen durch sogenannte Demosaicing-Algorithmen
berechnet werden.
</details>

In dieser Arbeit wurde JENIFFER2 um sechs Demosaicing-Algorithmen erweitert.
Zwei dieser Algorithmen wurden in jeweils zwei unterschiedlichen Variationen im-
plementiert, was die Gesamtzahl der in JENIFFER2 verfügbaren Demosaicing-Algo-
rithmen auf zwölf bringt. Die neu implementierten Algorithmen wurden aus existie-
renden Algorithmen ausgewählt, die in wissenschaftlicher Literatur oft referenziert,
oder in anderen Open-Source RAW-Konvertern genutzt werden. Zusätzlich wurde
ein Kombinationsalgorithmus entworfen, welcher aus Teilen von zwei bereits existie-
renden Algorithmen besteht. Die implementierten Algorithmen wurden abschließend
bezüglicher ihrer erzeugten Bildqualität und Laufzeit untersucht. Hier konnte fest-
gestellt werden, dass in Abhängigkeit von den Bildeigenschaften, Ratio Corrected
Demosaicing (RCD) oder der Kombinationsalgorithmus die beste Bildqualität er-
zeugen, allerdings auch die höchsten Rechenzeiten benötigen.

## Florian Kellner, 2023

<details>
<summary>Zusammenfassung von s.o.</summary>
Digitale Kamerasensoren nehmen Farben nicht simultan wahr, sondern bestehen
aus Helligkeitssensoren, vor die in einem nach seinem Erfinder benannten Bayer-
Mosaik Farbfilter der Farben rot, grün und blau geschaltet sind. Mit welchem
Algorithmus die jeweils fehlenden Farbwerte interpoliert werden, hat einen
großen Einfluss auf die Schärfe und Detailtreue des resultierenden Farbbildes.
Auf professionellen Kameras können die Sensordaten deswegen weitestgehend
unverarbeitet gespeichert werden.

Mit Jeniffer2 wurde von Ljavin (2020) eine Java-Anwendung zur Verarbeitung
von Bildern im offen standardisierten Adobe DNG (Digital Negative) Rohda-
tenformat geschaffen. Reiter (2023) erweiterte diese um einige aktuelle und
teils recht komplexe Demosaicing-Algorithmen, zwischen denen frei gewählt
werden kann. Diese Algorithmen sowie die Schritte zum Postprocessing stellten
sich als teilweise sehr zeitintensiv heraus.
</details>

In dieser Arbeit wurden verschiedene Ansätze erkundet, die implementierten
Berechnungen zu beschleunigen, wobei ein besonderer Fokus auf der Platt-
formunabhängigkeit, der Integration in Java und dem Erhalt der Les- und
Wartbarkeit der Software lag. Nach einer Zusammenfassung der technischen
Möglichkeiten wurde zunächst die Portierung eines Demosaicing-Algorithmus
und des Postprocessing auf die Grafikkarte mittels OpenGL umgesetzt und in
einem Feldtest auf den Endgeräten von 20 Teilnehmenden validiert.

Aufgrund der aufgetretenen Schwierigkeiten bei der Cross-Platform-
Kompatibilität der GPU-Version wurden die bei der Portierung gewonnenen
Kenntnisse über den Datenfluss innerhalb des Algorithmus für die Optimierung
aller Algorithmen auf der CPU genutzt. So konnte für die drei komplexesten
Algorithmen eine Beschleunigung um etwa das zehnfache erreicht werden,
bei einer gleichzeitigen Verbesserung der Verständlichkeit des Quellcodes.
Zusätzlich wurde eine Verarbeitung der Bilder in Kachelabschnitten getestet,
was die Performance nochmals geringfügig verbessert, aber vor allen den
Speicherbedarf der Anwendung reduziert. Ermittelt wurden diese Werte in
extensiven Benchmarks sowohl auf einem etwas älteren Laptop mit x86-
Architektur als auch auf einem modernen Mac Mini mit M1-Chiparchitektur.
Aufgrund verschiedener Faktoren ist die finale CPU-Version fast so schnell wie
die Version auf der GPU (sofern vorhanden).

Im Verlauf der Arbeit wurde die Codebasis von Jeniffer2 weiter gepflegt. Au-
ßerdem wurden mit der Pixellupe mit verschiedenen Vergleichsmodi und dem
schnellen Konfigurationswechsler zwei neue Elemente hinzugefügt, die zum
Erkunden und Vergleichen der Demosaicing-Algorithmen einladen.

