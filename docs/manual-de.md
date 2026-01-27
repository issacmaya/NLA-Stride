<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Benutzerhandbuch 

> Dieses Handbuch stellt die Funktionen und Techniken des NLA-Stride Blender Add-ons vor und beantwortet einige häufige bekannte Probleme.

---

## 📘 Inhaltsverzeichnis

1. [Schnellstart](#Quick_Start)  
2. [Update-Highlights](#Version_Updates)
3. [Funktionsübersicht](#Feature_Overview)      
4. [Häufig gestellte Fragen (FAQ)](#FAQ) 
5. [Sonstiges](#Others) 
6. [Technische Referenz](#Technical_Reference)

---

## 🚀 Schnellstart
<a id="Quick_Start"></a>

### 1. Add-on-Installation

1. Folgen Sie den offiziellen Installationsschritten von Blender ( **[Allgemeine Installationsanleitung](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Nach der Installation finden Sie das **NLA Stride Tool** im Blender 3D Viewport unter der Registerkarte **Seitenleiste → Animation**. 
<br>![alt text](images/img_1001.png)



---

### 2. Objekte mit Animation auswählen  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Wählen Sie ein oder mehrere Objekte aus, die Animationsdaten enthalten. Wenn es sich um Standardanimationen statt NLA-Animationen handelt, lesen Sie bitte die Anweisungen unter „NLA-Stapelverarbeitung“.

---

### 3. Zur Liste hinzufügen

![alt text](images/img_1003.png)

⚠️ Hinweis: Das Add-on arbeitet basierend auf der Liste, unabhängig von der aktuellen Objektauswahl im Viewport.

---

### 4. NLA-Ausrichtung / Offset-Operationen


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Oben sehen Sie Demonstrationen der NLA-Ausrichtungs- und Offset-Funktionen.

---

### 5. Genießen Sie die Animationsmagie

<a href="images/DEMO_01.mp4">
  <img src="images/DEMO_01.gif" width="720">
</a>  

<a href="images/DEMO_02.mp4">
  <img src="images/DEMO_02.gif" width="720">
</a>  

<a href="images/DEM3_03.mp4">
  <img src="images/DEMO_03.gif" width="720">
</a>  

<a href="images/DEM3_04.mp4">
  <img src="images/DEMO_04.gif" width="720">
</a>  

Besonderer Dank geht an die taiwanesische Marke [SANSUI / 山水品牌](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) für die Bereitstellung der Beispielmodelle.

---
## 🌟 Update-Highlights
<a id="Version_Updates"></a>
  
#### v1.0.0 Wichtige Updates
- Liste exportieren / importieren / anhängen 
  ![alt text](images/v100_001.png)  
  1. Drei neue Funktionen zu den Listenoperationen hinzugefügt.
  2. Export und Import erfolgen über *.json Dateien.
  3. „Anhängen“ fügt Elemente am Ende der Liste hinzu.
  4. Bei doppelten Namen hat das vorhandene Element Vorrang.
#### v0.9.8 Wichtige Updates  
- Erste öffentliche Version  
---
## 🧰 Funktionsübersicht
<a id="Feature_Overview"></a>
 

#### 1. Animationsquelle 

![alt text](images/img_2001.png)

- A : Initialisieren und Ausgewählte hinzufügen    
  Löscht die aktuellen Listendaten und fügt die in der Szene ausgewählten Objekte hinzu.  
  <br>
- B : Liste leeren  
  Löscht alle Daten in der Liste.  
  <br>
- C : Animationsquelle  
    Unterstützt derzeit drei Typen:  
    -  Objekt-Animation  
    -  Shape-Key-Animation  
    -  Material-Animation
  <br>
- D : Objekte in Liste hinzufügen / entfernen  
  Beim Hinzufügen wird die Liste **nicht** geleert; Objekte werden **gemäß der Auswahlreihenfolge** am Ende hinzugefügt. Bereits vorhandene Objekte werden ans Ende verschoben. Dies unterscheidet sich von Methode A. Das Entfernen unterscheidet sich ebenfalls von 1-J.  
  <br>

- E : Listenoperationen (Dropdown-Menü)  
  Details unter [1-1 Listenoperationen](#List_Functions).
  <br>

- F : Ausgewähltes Element nach oben / unten bewegen  
  Manuelle Anpassung der Reihenfolge. Sobald die Reihenfolge manuell geändert wurde, wird dies als **„Gecachte Originalreihenfolge“** definiert.
  <br>

- G : In NLA umwandeln (Dropdown-Menü)  
  Konvertiert nur die Objekte in der Liste in NLA-Strips.
  <br>  
  
-  PS. [3. Bedeutung der Symbole in der Liste](#List_Icon_Meanings)

#### 1-1. Listenoperationen
<a id="List_Functions"></a>

![alt text](images/img_2002.png)

- H : Initialisieren und Ausgewählte hinzufügen   
  Löscht die Listendaten und fügt die in der Szene ausgewählten Objekte hinzu.
  <br>

- I : Vier Sortierzustände    
  Der wichtigste ist die vom Add-on aufgezeichnete **Originalreihenfolge**; die anderen drei sind temporäre Sortierzustände.
  <br>

- J : Ausgewählte aus Szene entfernen   
  Entfernt die derzeit in der 3D-Szene ausgewählten Objekte aus der Liste (anders als 1-D).
  <br>

#### 2. Offset-Strips festlegen

![alt text](images/img_2003.png)

- K : Drei Strip-Modi (Strip-Modus)  
  - Einzelner Strip : Bezieht sich nur auf einen bestimmten Strip.
  - Einzelne Spur : Behandelt alle Strips auf einer Spur als eine Einheit (relative Positionen bleiben erhalten).
  - Alle Spuren : Alle Spuren des Objekts ändern sich gemeinsam (relative Positionen bleiben erhalten).
  <br>

- L : Drei Lokalisatoren  
  - Welcher Slot : Nur für Material-Modus, berechnet von **oben nach unten** im NLA-Interface.
  - Welche Spur : Berechnet von **unten nach oben** im NLA-Interface.
  - Welcher Strip : Berechnet von **links nach rechts** im NLA-Interface.
  <br>

  **!! HINWEIS: Wenn das Ziel nicht korrekt spezifiziert ist, kann kein NLA-Offset ausgeführt werden.**

#### 3. NLA-Ausrichtungstools (Initialisierungswerte)
![alt text](images/img_2004.png)

- M : Fünf Ausrichtungsmodi (Ausrichtungsmodus)  
  - Nach max. Startframe : Basierend auf dem **spätesten** Startpunkt der Strips in der Liste.
  - Nach min. Startframe : Basierend auf dem **frühesten** Startpunkt der Strips in der Liste (Häufig genutzt).
  - Nach max. Endframe : Basierend auf dem **spätesten** Endpunkt der Strips in der Liste (Häufig genutzt).
  - Nach min. Endframe : Basierend auf dem **frühesten** Endpunkt der Strips in der Liste.
  - Nach aktueller Zeit : Basierend auf der aktuellen Position des Abspielkopfs (Am häufigsten genutzt).
  <br>

- N : Drei Ausrichtungsmethoden  
  - Start ausrichten : Richtet die linke Seite am Ziel aus (häufig für Startpunkte).
  - Mitte ausrichten : Richtet die Mitte am Ziel aus.
  - Ende ausrichten : Richtet die rechte Seite am Ziel aus (häufig für Endpunkte).
  <br>

- O : Skalierung zurücksetzen  
  Setzt den Skalierungswert aller NLA-Strips in der Liste auf 1 zurück.
  <br>


#### 4. Einfacher Modus

![alt text](images/img_2005.png)  
- P : Falloff im einfachen Modus [(Detaillierte Erklärung)](#Stride_Description)  
  Es gibt vier Formeln für die Offset-Berechnung: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- Q : Offset-Betrag (Einheit: **Frames**)  
  Dies ist die Gesamtdifferenz zwischen dem ersten und dem letzten Objekt in der Liste (negative Werte möglich).
  <br>

- R : Skalierung  
  Dies ist die Skalierungsdifferenz zwischen dem ersten und dem letzten Objekt in der Liste (0 ~ 1).
  <br>

- S : Einfaches NLA-Stride ausführen (Wiederholtes Klicken kumuliert die Berechnung).
  <br>

#### 5. Profi-Modus
![alt text](images/img_2006.png)  
  **>> Der Kern dieses Add-ons: Mit einfachen Einstellungen werden Offset und Skalierung der Strips automatisch angepasst <<**

- T : Profi-Start-Falloff [(Detaillierte Erklärung)](#Stride_Description)  
  Vier Formeln: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- U : Startframe festlegen  
  Legt die **Startzeit** der Gesamtanimation für alle Objekte in der Liste fest.
  <br>

- V : Offset-Verhältnis (Start)    
  Der mit dem Falloff (T) multiplizierte Offset-Betrag, der zur automatischen Einstellung der Startpunkte aller Strips verwendet wird.
  <br>

- W : Profi-End-Falloff [(Detaillierte Erklärung)](#Stride_Description)    
  Vier Formeln: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- X : Endframe festlegen    
  Legt die **Endzeit** der Gesamtanimation für alle Objekte in der Liste fest.
  <br>

- Y : Offset-Verhältnis (Ende)    
  Differenz zwischen dem ersten und letzten Objekt (negative Werte möglich).
  <br>

- Z : Profi-NLA-Stride ausführen (Wiederholtes Klicken kumuliert **nicht**).
  <br>


---

## ❓ Häufig gestellte Fragen (FAQ)
<a id="FAQ"></a>


#### 1. ⚠️ Beachten Sie Details zu „Instanzierten Daten (Instanced Data)“

Dieses Add-on konzentriert sich primär auf das Verschieben und Ausrichten der NLA-Strips selbst  
und verarbeitet **nicht** automatisch die „Instanced Data“-Beziehungen von Blender.

#### Was sind instanzierte Daten?

Wenn **mehrere Objekte dieselben Datenblöcke teilen**, sind diese Daten „instanziert“.

- Zum Beispiel:  
  - Zwei Objekte teilen sich dasselbe Material.  
  - Oder sie teilen dieselbe Action (Animation), Mesh oder andere Datenblöcke.  

Im NLA-Editor sehen diese wie unabhängige Strips aus, aber sie **verweisen auf dieselben zugrunde liegenden Daten**.
Das Ergebnis ist, dass bei Verwendung von **NLA Stride für den Offset** das Add-on zwar Strips zu verschieben scheint, diese aber immer noch dieselben Daten beeinflussen, wodurch der **gewünschte Offset-Effekt nicht erreicht wird**.


#### ✅ Lösung (Folgen Sie diesen Schritten)

> 💡 **Kernlösung: Machen Sie die Daten vor dem Offset unabhängig (Single User).**

Schritte (wie im Bild gezeigt):

1. Wählen Sie die Objekte im 3D Viewport aus.  
2. Gehen Sie zu **Objekt → Beziehungen (Relations)**.  
3. Klicken Sie auf **Einzelnutzer machen (Make Single User)**.  
4. Wählen Sie den gewünschten Datentyp (z.B. Objekt-Animation).
5. Nachdem die Daten unabhängig sind, verwenden Sie **NLA Stride** für den Offset.  



![alt text](images/img_3001.png)

> Sobald die Daten unabhängig sind, hat jedes Objekt seine eigenen „echten NLA-Daten“.
> NLA Stride kann dann **NLA-Strips normal und vorhersehbar verschieben**.
---


#### 2. ⚠️ NLA-Stapelverarbeitung

Dieses Add-on verarbeitet NLA-Strips. Animationen, die noch nicht in NLA-Strips umgewandelt wurden (Aktive Actions), werden nicht beeinflusst.

#### ✅ Lösung: Stapelverarbeitungs-Tool

Das Add-on bietet ein Tool, um Objekte in der Liste in einem Rutsch in NLA umzuwandeln (grüner Pfeil unten). Hinweis: Dies betrifft die **Liste**, nicht nur die 3D-Auswahl.

![alt text](images/img_3002.png)

---



## 📖 Sonstiges
<a id="Others"></a>


#### 1. Tipps für Ausrichtungs- und Offset-Strategien

- Sie können im 3D Viewport **Alt A** drücken, um alles abzuwählen, und dann die Funktion **Listenobjekte auswählen** nutzen, um zu prüfen, was genau in der Liste enthalten ist.  
<br>

- Die **Reihenfolge** ist sehr wichtig, da sie den Animationszustand nach dem Offset direkt beeinflusst. Nutzen Sie wenn möglich Namen zur Bestimmung der Reihenfolge. Bei sehr vielen Objekten empfiehlt sich die Stapelverarbeitung oder die Nutzung der [`Export / Import`](#Version_Updates) Funktion.  
<br>

- Wenn es unübersichtlich wird, nutzen Sie die Ausrichtungstools, um alles wieder auf einen Ausgangspunkt zu synchronisieren.  
<br>

- Da Animations-Offsets nun sehr einfach sind, konzentrieren Sie sich darauf, eine **perfekte Bewegung** zu erstellen.  
<br>

- Zum Bewegungsdesign: Wenn die **Position** per Keyframe festgelegt ist, beachten Sie beim Kopieren, dass die Animation zur selben Position zurückspringt, da die Positionsdaten im NLA festgeschrieben sind. Nutzen Sie in diesem Fall **Ctrl A** (Transformation anwenden), um die neue Position in die **Delta-Transform** Daten zu schreiben.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Stride-Erklärung
<a id="Stride_Description"></a>

- Linearer Stapelmodus :  
  - Einfacher Modus :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Der einfache Modus berechnet basierend auf dem Originalzustand (ganz links im Bild). Bei beispielsweise Offset 100 und Skalierung 1.5 werden Startpunkt und Länge des letzten Strips immer gleich sein; aber die verschiedenen Falloff-Modi erzeugen unterschiedliche Zwischen-Startpunkte, was ein anderes Offset-Gefühl vermittelt.

    ---
  - Profi-Modus :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Im Unterschied zum einfachen Modus kann der Profi-Modus Anfang und Ende separat steuern, wodurch für beide ein eigener Falloff-Modus eingestellt werden kann.  
  
    ---
  - **Achtung** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Wenn die Falloff-Modi für Anfang und Ende **unterschiedlich** sind, achten Sie darauf, ob die Animationsstrips zu kurz werden oder verschwinden.
---

#### 3. Bedeutung der Symbole in der Liste
<a id="List_Icon_Meanings"></a>

![alt text](images/img_3003.gif)

Symbol A : Datenmodus
Symbol B : Action steht für allgemeine Animationsdaten (kein NLA)
Symbol C : Verfügbare NLA-Daten

- Die Bedeutung der Symbole in B und C ändert sich je nach im Spalte A ausgewähltem Datenmodus:
  - ✔ : Enthält **korrekte** Daten passend zum Modus in Spalte A.
  - ・ : Enthält Daten, aber **nicht** vom in Spalte A eingestellten Typ.
  - ✕ : Enthält keine Daten.

Daten im Beispiel:
| Element | Objekt-Animation | Material-Animation | Shape-Key-Animation |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Aktive Action** | cube.027 | cube.037 | cube.038 | 

- Sonstiges: cube.000 (Hat alle 3 NLA-Typen) / cube.039 (Hat keinerlei Animationsdaten)

---




## 🔧 Technische Referenz
<a id="Technical_Reference"></a>

  [Blender NLA Offizielles Handbuch](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Blender API Offizielles Handbuch](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Inhaltsverzeichnis

1. [Schnellstart](#Quick_Start) 
2. [Update-Highlights](#Version_Updates) 
3. [Funktionsübersicht](#Feature_Overview)      
4. [Häufig gestellte Fragen (FAQ)](#FAQ) 
5. [Sonstiges](#Others) 
6. [Technische Referenz](#Technical_Reference)