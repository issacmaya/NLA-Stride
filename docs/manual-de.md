<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Benutzerhandbuch (Deutsch)

> Dieses Handbuch stellt die Funktionen und Tipps für das NLA-Stride Blender Add-on vor und beantwortet einige häufig gestellte bekannte Probleme.

---

## 📘 Inhaltsverzeichnis

1. [Schnellstart](#-schnellstart)  
2. [Funktionsübersicht](#-funktionsübersicht)      
3. [Häufig gestellte Fragen](#-häufig-gestellte-fragen) 
4. [Sonstiges](#-sonstiges) 
5. [Technische Referenz](#-technische-referenz)

---

## 🚀 Schnellstart

### 1. Add-on Installation

1. Folgen Sie den offiziellen Blender-Installationsschritten ( **[Allgemeine Installationsanleitung](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Nach der Installation finden Sie das **NLA Stride Tool** im Blender 3D Viewport unter dem Reiter **Seitenleiste → Animation**. 
<br>![alt text](images/img_1001.png)



---

### 2. Objekte mit Animation auswählen  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Wählen Sie ein oder mehrere Objekte aus, die Animationsdaten enthalten. Wenn diese Standard-Actions anstelle von NLA-Strips enthalten, lesen Sie bitte den Abschnitt "Batch-Push nach NLA" weiter unten.  

---

### 3. Zur Liste hinzufügen  
![alt text](images/img_1003.png)  

⚠️ Hinweis: Das Add-on arbeitet auf Basis der Liste, unabhängig von der aktuellen Auswahl im Viewport.  

---

### 4. NLA Ausrichtung / Offset-Operationen  
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

Besonderer Dank geht an die taiwanische Marke [SANSUI](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) für die Bereitstellung der Beispielmodelle.  

---

## 🧰 Funktionsübersicht

#### 1. Animationsquelle 
![alt text](images/img_2001.png)  

- A : Initialisieren & Auswahl hinzufügen  
  Leert zuerst die Liste und fügt dann die aktuell in der Szene ausgewählten Objekte hinzu.  
<br>

- B : Liste leeren  
  Löscht alle Daten aus der Liste.  
<br>

- C : Animationsquelle  
  Unterstützt derzeit drei Typen: Objekt-Animation / Shape-Key-Animation / Material-Animation.  
<br>

- D : Listeneinträge hinzufügen / entfernen  
  Hinzufügen leert die Liste **nicht**; Objekte werden am Ende in der **Reihenfolge der Auswahl** hinzugefügt. Wenn ein Objekt bereits in der Liste ist, wird es ans Ende verschoben. Die Logik unterscheidet sich von A. Das Entfernen-Werkzeug unterscheidet sich ebenfalls von 1-J.  
<br>

- E : Listenoperationen (Dropdown-Menü)  
  Siehe "1-1 Listenoperationen" für Details.  
<br>

- F : Eintrag nach oben / unten verschieben  
  Passt die Reihenfolge manuell an. Einmal angepasst, wird dieses Ergebnis als die **"Ursprüngliche Reihenfolge"** definiert.  
<br>

- G : Push nach NLA (Dropdown-Menü)  
  Wandelt die aktuelle Action in NLA-Strips um, nur für Objekte in der Liste.  
<br>

- PS. [3. Bedeutung der Listensymbole](#3-bedeutung-der-listensymbole)  

#### 1-1. Listenoperationen
![alt text](images/img_2002.png)  

- H : Initialisieren & Auswahl hinzufügen  
  Leert zuerst die Liste und fügt dann die aktuell in der Szene ausgewählten Objekte hinzu.  
<br>

- I : Vier Sortieroptionen  
  Die wichtigste ist **Ursprüngliche Reihenfolge wiederherstellen**, da dieses Add-on diese Sequenz speichert. Die anderen drei sind automatische Sortierungen.  
<br>

- J : Szenenauswahl entfernen  
  Entfernt Objekte aus der Liste basierend auf der aktuellen Auswahl im Viewport. Dies unterscheidet sich vom 1-D Entfernen-Werkzeug.  

#### 2. Datenpositionierung
![alt text](images/img_2003.png)  

- K : Drei Strip-Modi  
  - Einzelner Strip : Konzentriert sich auf nur einen spezifischen Strip.  
  - Einzelne Spur : Behandelt alle Strips auf einer Spur als eine Gruppe (relative Positionen ändern sich nicht).  
  - Alle Spuren : Entspricht dem gleichzeitigen Ändern aller Spuren des Objekts (relative Positionen ändern sich nicht).  
<br>

- L : Drei Positionierungspunkte  
  - Welcher Slot : (Nur Material-Modus) Berechnet von **oben nach unten** im UI.  
  - Welche Spur : Berechnet von **unten nach oben** im NLA-Editor.  
  - Welcher Strip : Berechnet von **links nach rechts** im NLA-Editor.  
<br>

  **!! Hinweis: Wenn das Ziel nicht korrekt positioniert ist, kann NLA Stride den Versatz nicht ausführen.** #### 3. NLA Ausrichtungswerkzeuge (Initialisierungswerte)
![alt text](images/img_2004.png)  

- M : Fünf Ausrichtungsziele  
  - Bei Max Startframe : Richtet sich am **Startpunkt** des Strips aus, der in der Liste am **spätesten** beginnt.  
  - Bei Min Startframe : Richtet sich am **Startpunkt** des Strips aus, der am **frühesten** beginnt (häufig verwendet).  
  - Bei Max Endframe : Richtet sich am **Endpunkt** des Strips aus, der am **spätesten** endet (häufig verwendet).  
  - Bei Min Endframe : Richtet sich am **Endpunkt** des Strips aus, der am **frühesten** endet.  
  - Bei aktueller Zeit : Richtet sich an der aktuellen Position des Abspielkopfs aus (am gebräuchlichsten).  
<br>

- N : Drei Ausrichtungsmodi  
  - An Start ausrichten : Die linke Seite des Strips wird am Ziel ausgerichtet. Meist für die **Start**-Ausrichtung verwendet.  
  - An Mitte ausrichten : Die Mitte des Strips wird am Ziel ausgerichtet.  
  - An Ende ausrichten : Die rechte Seite des Strips wird am Ziel ausgerichtet. Meist für die **End**-Ausrichtung verwendet.  
<br>

- O : Skalierung zurücksetzen  
  Setzt den Skalierungswert aller NLA-Strips in der Liste auf 1.0 zurück.  


#### 4. Einfacher Modus
![alt text](images/img_2005.png)  

- P : Abfall-Modus [(Detailbeschreibung)](#2-versatz-erklärung)  
  - Vier Rechenformeln: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- Q : Versatzbetrag (Einheit: **Frames**)  
  - Dies ist nicht der Abstand zwischen einzelnen Strips, sondern die Gesamtdifferenz zwischen dem ersten und letzten Objekt in der Liste (negative Werte zulässig).  
<br>

- R : Skalierung  
  - Keine inkrementelle Skalierung, sondern die Skalierungsdifferenz zwischen dem ersten und letzten Objekt in der Liste (0 ~ 1).  
<br>

- S : Einfachen NLA Stride ausführen (wiederholtes Klicken kumuliert die Berechnung).  
<br>

#### 5. Profi-Modus
![alt text](images/img_2006.png)  
  **>> Das Herzstück dieses Add-ons. Durch einfache Einstellungen werden Strip-Versatz und Skalierung automatisch angepasst <<** - T : Abfall-Modus [(Detailbeschreibung)](#2-versatz-erklärung)  
  - Vier Rechenformeln: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- U : Startframe festlegen  
  - Definiert den **Startzeitpunkt** für die gesamte Animationssequenz aller Objekte in der Liste.  
<br>

- V : Versatzverhältnis (Kopf)  
  - Wird mit dem Abfall-Modus (T) multipliziert, um den Versatzwert zu berechnen, der zur automatischen Positionierung aller Strip-Startpunkte verwendet wird.  
<br>

- W : Abfall-Modus [(Detailbeschreibung)](#2-versatz-erklärung)  
  - Vier Rechenformeln: 1. Linear / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- X : Endframe festlegen  
  - Definiert den **Endzeitpunkt** für die gesamte Animationssequenz aller Objekte in der Liste.  
<br>

- Y : Versatzverhältnis (Ende)  
  - Das Versatzverhältnis für die Endpunkte der Strips.  
<br>

- Z : Profi-NLA Stride ausführen (wiederholtes Klicken kumuliert die Berechnung **nicht**).  
<br>


---

## ❓ Häufig gestellte Fragen


#### 1. ⚠️ Achtung bei "Instanzierten Daten (Instanced Data)"

Dieses Add-on verarbeitet hauptsächlich den Versatz und die Ausrichtung von NLA-Strips selbst; es verwaltet **nicht** automatisch Beziehungen von "instanzierten Daten" innerhalb von Blender.  

#### Was sind instanzierte Daten?

Wenn **mehrere Objekte dieselben Daten teilen**, sind diese Datenblöcke "instanziert".  

- Zum Beispiel:  
  - Zwei Objekte, die dasselbe Material teilen.  
  - Gemeinsame Nutzung derselben Action, desselben Meshs oder anderer Datenblöcke.  

Im NLA-Editor können dies wie zwei unabhängige Strips aussehen, aber in Wirklichkeit **verweisen sie auf denselben zugrunde liegenden Datenblock**.
Dies führt dazu, dass das Add-on bei Verwendung von **NLA Stride für den Versatz** zwar verschiedene Strips zu verschieben scheint, in Wirklichkeit aber dieselben Daten ändert, wodurch der **erwartete Versatzeffekt nicht erzielt wird**.


#### ✅ Lösung (Folgen Sie den Schritten im Bild)

> 💡 **Kernidee: Daten unabhängig machen, bevor der Versatz durchgeführt wird.** Schritte (wie im Bild gezeigt):  

1. Wählen Sie die zu verarbeitenden Objekte im 3D Viewport aus.  
2. Gehen Sie zu **Objekt (Object) → Beziehungen (Relations)**.  
3. Klicken Sie auf **Einzelbenutzer machen (Make Single User)**.  
4. Wählen Sie die Datentypen aus, die unabhängig werden sollen (z. B. Objekt-Animation).  
5. Sobald die Daten unabhängig sind, verwenden Sie **NLA Stride**, um den Versatz durchzuführen.  



![alt text](images/img_3001.png)  

> Wenn die Daten unabhängig sind, hat jedes Objekt seine eigenen exklusiven NLA-Daten.
> NLA Stride kann dann **helfen, die NLA-Strips normal und vorhersehbar zu versetzen**.  

---


#### 2. ⚠️ Batch-NLA-Erstellung

Das Ziel dieses Add-ons sind NLA-Strips. Wenn Animationsdaten noch nicht "gepusht" wurden, um NLA-Strips zu werden, sind sie nicht betroffen.  

#### ✅ Lösung: Push nach NLA Werkzeug

Das Add-on bietet ein Batch-Konvertierungswerkzeug (unten mit grünen Pfeilen markiert). Beachten Sie, dass dies für Objekte **in der Liste** gilt, nicht für die Auswahl im Viewport.  

![alt text](images/img_3002.png)  

---



## 📖 Sonstiges


#### 1. Strategietipps für Ausrichtung und Versatz

- Sie können zuerst **Alt A** im 3D Viewport drücken, um alles abzuwählen, und dann die Funktion **Listenobjekte auswählen** verwenden, um genau zu bestätigen, wer sich in Ihrer Liste befindet.  
<br>

- Die **Reihenfolge** ist entscheidend, da sie den Animationszustand nach dem Versatz direkt beeinflusst. Verwenden Sie nach Möglichkeit Benennungsregeln, um die Reihenfolge festzulegen. Verarbeiten Sie große Mengen an Objekten schubweise.  
<br>

- Wenn alles durcheinander gerät, verwenden Sie die Ausrichtungswerkzeuge, um zuerst alles zu vereinheitlichen.  
<br>

- Da das Versetzen von Animationen sehr einfach wird, konzentrieren Sie Ihre Energie darauf, eine **perfekte Bewegung** zu erstellen.  
<br>

- Wenn Ihr Bewegungsdesign **Standort (Location)** beinhaltet, seien Sie vorsichtig beim Duplizieren; beim Abspielen der Animation springt sie möglicherweise an dieselbe Position zurück, da die Standortinformationen im NLA festgeschrieben sind. In diesem Fall können Sie **Strg A** verwenden, um Transformationen anzuwenden und die neue Position in die **Delta-Transformationen** zu schreiben.  
<br>![alt text](images/img_4001.png)  

---

#### 2. Versatz Erklärung
- Linearer Stapelmodus :  
  - Einfacher Modus :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Der einfache Modus berechnet im Stapelmodus basierend auf dem ursprünglichen Zustand (ganz links im Bild). Wie gezeigt, bei Versatz 100 und Skalierung 1.5, bleiben Startpunkt und Länge (Endpunkt) des letzten Strips immer gleich; aber man sieht, dass aufgrund der verschiedenen Abfall-Modi die Startpunkte der anderen Strips variieren, was ein unterschiedliches Versatzgefühl erzeugt.  

    ---
  - Profi-Modus :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Der einzige Unterschied zum einfachen Modus besteht darin, dass der Profi-Modus die Steuerung für Kopf (Head) und Ende (Tail) ermöglicht und somit zwei separat einstellbare Abfall-Modi bietet.  
  
    ---
  - **Hinweis** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Beachten Sie, dass bei **unterschiedlichen** Abfall-Modi für Kopf und Ende darauf geachtet werden muss, ob Probleme mit den Animationsstrips auftreten (zu kurz oder verschwinden).  

---

#### 3. Bedeutung der Listensymbole

![alt text](images/img_3003.gif)  

Symbol A : Datenmodus  
Symbol B : Action steht für Standard-Animationsdaten (nicht NLA).  
Symbol C : Vorhandene NLA-Daten.  

- Die Bedeutung der Symbole B und C ändert sich basierend auf dem Datenmodus in Spalte A:  
  - ✔ : Enthält die **korrekten** Daten passend zum Modus in Spalte A.  
  - ・ : Enthält Daten, aber **nicht** vom in Spalte A konfigurierten Typ.  
  - ✕ : Keine Daten gefunden.  

Daten im Viewport:  
| Element | Objekt-Animation | Material-Animation | Shape-Key-Animation |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Aktive Action** | cube.027 | cube.037 | cube.038 |  

- Sonstiges : cube.000 (hat alle drei NLA-Typen) / cube.039 (keine Animationsdaten).  

---

## 🔧 Technische Referenz

  [Offizielles Blender NLA Handbuch](https://docs.blender.org/manual/en/latest/editors/nla/index.html)  

  [Offizielles Blender API Handbuch](https://docs.blender.org/api/current/bpy.ops.nla.html)  

  


## 📘 Inhaltsverzeichnis

1. [Schnellstart](#-schnellstart)  
2. [Funktionsübersicht](#-funktionsübersicht)      
3. [Häufig gestellte Fragen](#-häufig gestellte fragen) 
4. [Sonstiges](#-sonstiges) 
5. [Technische Referenz](#-technische-referenz)
