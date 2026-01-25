<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Benutzerhandbuch (Deutsch)

> Dieses Handbuch stellt die Funktionen und Tipps für das NLA-Stride Blender Add-on vor und beantwortet einige bekannte Probleme.

---

## 📘 Inhalt

1. [Schnellstart](#-schnellstart)  
2. [Version-Highlights](#-version-highlights)
3. [Funktionsübersicht](#-funktionsübersicht)      
4. [FAQ](#-faq) 
5. [Andere Tipps](#-andere-tipps) 
6. [Technisches Referenz](#-technisches-referenz)

---

## 🚀 Schnellstart

### 1. Add-on Installation

1. Verwenden Sie die offiziellen Blender-Installationsschritte ( **[Allgemeine Installationsanleitung](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Nach der Installation finden Sie das **NLA Stride Tool** in der Blender 3D-Ansicht unter **Seitenleiste → Animation**. 
<br>![alt text](images/img_1001.png)



---

### 2. Objekte mit Animationen auswählen  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Wählen Sie ein oder mehrere Objekte aus, die Animationsdaten enthalten. Wenn Sie Standard-Animationen anstelle von NLA-Strips verwenden, lesen Sie bitte die Anweisungen unter „Push-Animation zum NLA“.

---

### 3. Zur Liste hinzufügen

![alt text](images/img_1003.png)

⚠️ Hinweis: Das Add-on arbeitet auf Basis der Liste, unabhängig von den aktuell in der Szene ausgewählten Objekten.

---

### 4. NLA Ausrichtung / Versatz-Operationen


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Die obigen Diagramme veranschaulichen die NLA-Ausrichtungs- und Versatzfunktionen.

---

### 5. Animation genießen

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

Beispielmodell mit Dank an [SANSUI Taiwan](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) für die Bereitstellung.

---
## 🌟 Version-Highlights
#### v1.0.0 Highlights
- Liste exportieren / importieren / hinzufügen 
  ![alt text](images/v100_001.png)  
  1. Drei Funktionen innerhalb der Listenoperationen hinzugefügt.
  2. Export und Import verwenden das *.json Format.
  3. „Hinzufügen“ fügt Elemente am Ende der Liste hinzu.
  4. Bei Namensdopplungen hat das zuerst gefundene Objekt Vorrang.
#### v0.9.8 Highlights  
- Erste öffentliche Veröffentlichung  
---
## 🧰 Funktionsübersicht

#### 1. Liste Initialisierungstool 

![alt text](images/img_2001.png)

- A : Initialisieren & Auswahl hinzufügen    
  Löscht die Listendaten und fügt dann die aktuell ausgewählten Objekte aus der Szene hinzu.
  <br>
- B : Liste leeren  
  Löscht alle Daten in der Liste.
  <br>
- C : Animationsquelle  
    Unterstützt derzeit drei Typen:
    - Objekt-Animation  
    - Shape-Key-Animation  
    - Material-Animation
  <br>
- D : Objekte zur Liste hinzufügen / entfernen  
  Hinzufügen löscht keine bestehenden Elemente; Objekte werden am Ende **in der Reihenfolge der Auswahl** hinzugefügt. Das Entfernen hier unterscheidet sich von 1-J.
  <br>

- E : Listenoperationen (Dropdown-Menü)  
  Details siehe [1-1 Listenoperationen](#1-1-listenoperationen).
  <br>

- F : Ausgewähltes Element Hoch / Runter  
  Manuelle Anpassung der Sortierung. Wenn die Reihenfolge angepasst wird, wird das Ergebnis als **„Originalreihenfolge“** definiert.
  <br>

- G : Push-Animation zum NLA (Dropdown-Menü)  
  Konvertiert Animationen in NLA-Strips nur für Objekte in der Liste.
  <br>  
  
-  PS. [3. Legende für Listensymbole](#3-legende-für-listensymbole)

#### 1-1. Listenoperationen

![alt text](images/img_2002.png)

- H : Initialisieren & Auswahl hinzufügen   
  Löscht die Listendaten und fügt die aktuell ausgewählten Objekte hinzu.
  <br>

- I : Sortierstatus    
  Beinhaltet **Originalreihenfolge** (die das Add-on verfolgt) und drei andere Sortiermethoden.
  <br>

- J : In Szene Ausgewähltes entfernen   
  Entfernt Objekte, die aktuell in der Szene ausgewählt sind, aus der Liste.
  <br>

#### 2. Offset-Strips angeben

![alt text](images/img_2003.png)

- K : Strip-Modus  
  - Einzelner Strip: Zielt nur auf einen bestimmten Strip ab.
  - Einzelne Spur: Behandelt alle Strips auf einer Spur als eine Einheit (behält relative Positionen bei).
  - Alle Spuren: Alle Spuren des Objekts ändern sich gemeinsam (behält relative Positionen bei).
  <br>

- L : Slot/Spur/Strip Positionierung  
  - Slot: Nur Materialmodus, wird von **oben nach unten** in der Benutzeroberfläche berechnet.
  - Spur: Wird von **unten nach oben** im NLA-Editor berechnet.
  - Strip: Wird von **links nach rechts** im NLA-Editor berechnet.
  <br>

  **!! Hinweis: Wenn das Ziel nicht korrekt lokalisiert ist, kann NLA Stride nicht funktionieren.**

#### 3. NLA Ausrichtungswerkzeuge (Initialisierungswerte)
![alt text](images/img_2004.png)

- M : Ausrichtungsmodus Ziel  
  - Nach max. Start-Frame: Richtet am **Start** des am **spätesten** beginnenden Strips in der Liste aus.
  - Nach min. Start-Frame: Richtet am **Start** des am **frühesten** beginnenden Strips in der Liste aus (Häufig).
  - Nach max. End-Frame: Richtet am **Ende** des am **spätesten** endenden Strips in der Liste aus (Häufig).
  - Nach min. End-Frame: Richtet am **Ende** des am **frühesten** endenden Strips in der Liste aus.
  - Nach aktueller Zeit: Richtet an der aktuellen Abspielposition aus (Am häufigsten).
  <br>

- N : Ausrichtungsposition  
  - An Start ausrichten: Richtet die linke Seite am Ziel aus.
  - An Mitte ausrichten: Richtet die Mitte am Ziel aus.
  - An Ende ausrichten: Richtet die rechte Seite am Ziel aus.
  <br>

- O : Skalierung zurücksetzen  
  Setzt die Skalierung aller angegebenen NLA-Strips in der Liste auf 1 zurück.
  <br>


#### 4. Einfacher Modus

![alt text](images/img_2005.png)  
- P : Falloff (Einfacher Modus) [(Detaillierte Beschreibung)](#2-versatzbeschreibung)  
  Vier Berechnungsformeln: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- Q : Versatzbetrag (Einheit: **Frames**)  
  Nicht der äquidistante Abstand zwischen den Strips, sondern die Gesamtdifferenz zwischen dem ersten und dem letzten Objekt in der Liste (erlaubt negative Werte).
  <br>

- R : Skalierung  
  Nicht die äquidistante Skalierung, sondern die Skalierungsdifferenz zwischen dem ersten und dem letzten Objekt (0 ~ 1).
  <br>

- S : Einfachen NLA Stride ausführen (Werte summieren sich bei wiederholtem Drücken).
  <br>

#### 5. Profi-Modus
![alt text](images/img_2006.png)  
  **>> Das Kernmerkmal: Definieren Sie Start- und Endpunkte, und Strips werden automatisch versetzt und skaliert. <<**

- T : Pro Start Falloff [(Detaillierte Beschreibung)](#2-versatzbeschreibung)  
  Berechnungsformel für den Versatz: Linear, Ease In, Ease Out oder Ease In Out.
  <br>

- U : Start-Frame setzen  
  Legt die globale **Startzeit** für die gesamte Animationssequenz in der Liste fest.
  <br>

- V : Versatzverhältnis  
  Der Versatzbetrag multipliziert mit dem Falloff-Modus (T), wird verwendet, um Start-Frame-Positionen zu automatisieren.
  <br>

- W : Pro End Falloff [(Detaillierte Beschreibung)](#2-versatzbeschreibung)    
  Berechnungsformel für den Versatz: Linear, Ease In, Ease Out oder Ease In Out.
  <br>

- X : End-Frame setzen    
  Legt die globale **Endzeit** für die gesamte Animationssequenz in der Liste fest.
  <br>

- Y : Versatzverhältnis    
  Differenz zwischen den End-Frames des ersten und letzten Objekts (erlaubt negative Werte).
  <br>

- Z : Profi NLA Stride ausführen (Werte summieren sich **nicht**).
  <br>


---

## ❓ FAQ


#### 1. ⚠️ Vorsicht mit Details zu „Instanziierte Daten (Instanced Data)“

Dieses Add-on zielt auf die NLA-Strips selbst für Versatz und Ausrichtung ab,  
es behandelt **nicht** automatisch die Blender-Beziehungen für „Instanziierte Daten“.

#### Was sind instanziierte Daten?

Wenn **mehrere Objekte denselben Datenblock teilen**, sind diese Daten „Instanziiert“.

- Zum Beispiel:  
  - Zwei Objekte teilen sich dasselbe Material.  
  - Teilen sich dieselbe Action, dasselbe Mesh oder andere Datenblöcke.  

Im NLA-Editor sehen sie wie zwei unabhängige Strips aus, aber sie **verweisen hinter den Kulissen auf dieselben Daten**.
Infolgedessen bewegt das Add-on beim Verwenden von **NLA Stride zum Versetzen** zwar die Strips, da diese aber dieselben zugrunde liegenden Daten beeinflussen, wird der **erwartete Versatzeffekt nicht erzielt**.


#### ✅ Lösung (Folgen Sie dem Screenshot unten)

> 💡 **Wichtige Praxis: Daten vor dem Versetzen unabhängig machen**

Schritte:

1. Wählen Sie die Objekte in der 3D-Ansicht aus.  
2. Gehen Sie zu **Objekt →关聯資料 (Relations)**.  
3. Klicken Sie auf **使單一使用者 (Make Single User)**.  
4. Wählen Sie die Datentypen aus, die unabhängig sein müssen.
5. Sobald die Daten unabhängig sind, verwenden Sie **NLA Stride**, um sie zu versetzen.  



![alt text](images/img_3001.png)

> Sobald die Daten unabhängig sind, hat jedes Objekt seine eigenen „wirklich einzigartigen NLA-Daten“.
> NLA Stride wird dann **NLA-Strips normal und vorhersehbar versetzen**.
---


#### 2. ⚠️ Batch-Push zum NLA

Dieses Add-on arbeitet speziell auf NLA-Strips. Animationsdaten, die noch nicht zum NLA gepusht wurden, werden nicht beeinflusst.

#### ✅ Lösung: Batch-Konvertierungswerkzeug

Das Add-on bietet ein Werkzeug, um Animationen für alle Objekte **in der Liste** zum NLA zu pushen (grüner Pfeil unten). Hinweis: Dies zielt auf die Liste ab, nicht nur auf die 3D-Auswahl.

![alt text](images/img_3002.png)

---



## 📖 Andere Tipps


#### 1. Ausrichtungs- und Versatzstrategie

- Sie können **Alt A** in der 3D-Ansicht drücken, um alles abzuwählen, und dann die Funktion **Listenobjekte auswählen** verwenden, um zu überprüfen, welche Objekte sich genau in Ihrer Liste befinden.  
<br>

- Da die **Reihenfolge** entscheidend ist (sie beeinflusst direkt das Versatzergebnis), versuchen Sie, Namen zur Bestimmung der Reihenfolge zu verwenden. Wenn Sie viele Objekte haben, bearbeiten Sie diese in Chargen.  
<br>

- Wenn es unübersichtlich wird, verwenden Sie das Ausrichtungswerkzeug, um alles auf einen einheitlichen Startpunkt zurückzusetzen.  
<br>

- Da das Versetzen einfach wird, konzentrieren Sie sich zuerst darauf, eine **perfekte dynamische Bewegung** zu erstellen.  
<br>

- Wenn Ihre Animation **Positionen (Location)** beinhaltet, könnten Duplikate an dieselbe Stelle zurückspringen. Verwenden Sie **Ctrl A**, um Transformationen auf die **增減變換 (Delta Transform)** Daten anzuwenden.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Versatzbeschreibung
- Linearer Falloff-Modus:  
  - Einfacher Modus:   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Der einfache Modus berechnet basierend auf dem Originalzustand (links). Beispiel: Versatz 100, Skalierung 1.5. Der Startpunkt und die Länge des letzten Strips entsprechen den Einstellungen, aber die dazwischen liegenden Strips variieren je nach Falloff-Modus.

    ---
  - Profi-Modus:    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Im Gegensatz zum einfachen Modus steuert der Profi-Modus sowohl den Anfang als auch das Ende, was separate Falloff-Modi für beide ermöglicht.  
  
    ---
  - **Hinweis**:   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Wenn die Falloff-Modi für Start und Ende **unterschiedlich** sind, achten Sie darauf, dass Strips nicht zu kurz werden oder verschwinden.
---

#### 3. Legende für Listensymbole

![alt text](images/img_3003.gif)

Symbol A: Animationsquellen-Modus
Symbol B: Action repräsentiert allgemeine Animationsdaten (Noch nicht im NLA)
Symbol C: Verfügbare NLA-Daten

- Die Symbole in B und C ändern sich basierend auf dem Quellen-Modus (A):
  - ✔ : Enthält **korrekte** Daten, die mit Modus A übereinstimmen.
  - ・: Enthält Daten, die aber **NICHT** mit Modus A übereinstimmen.
  - ✕ : Keine Daten gefunden.

Daten im Beispiel:
| Element | Objekt Anim | Material Anim | Shape-Key Anim |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Aktiv Aktion** | cube.027 | cube.037 | cube.038 | 

- Andere: cube.000 (Hat NLA für alle 3 Typen) / cube.039 (Überhaupt keine Animationsdaten)

---




## 🔧 Technisches Referenz

  [Blender NLA Offizielles Handbuch](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Blender API Offizielles Handbuch](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Inhalt

1. [Schnellstart](#-schnellstart) 
2. [Version-Highlights](#-version-highlights) 
3. [Funktionsübersicht](#-funktionsübersicht)      
4. [FAQ](#-faq) 
5. [Andere Tipps](#-andere-tipps) 
6. [Technisches Referenz](#-technisches-referenz)