<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Gebruikershandleiding (Nederlands)

> Deze handleiding introduceert de functies en technieken van de NLA-Stride Blender add-on, evenals antwoorden op enkele veelvoorkomende bekende problemen.

---

## 📘 Inhoudsopgave

1. [Snel aan de slag](#-snel-aan-de-slag)  
2. [Belangrijke updates](#-belangrijke-updates)
3. [Functieoverzicht](#-functieoverzicht)      
4. [Veelgestelde vragen](#-veelgestelde-vragen) 
5. [Overige](#-overige) 
6. [Technische referentie](#-technische-referentie)

---

## 🚀 Snel aan de slag

### 1. Installatie van de add-on

1. Volg de officiële installatiestappen van Blender ( **[Algemene installatiehandleiding](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Na de installatie vind je de **NLA Stride Tool** in de Blender 3D Viewport onder het tabblad **Zijbalk → Animatie**. 
<br>![alt text](images/img_1001.png)



---

### 2. Selecteer objecten met animatie  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Selecteer een of meer objecten die animatiegegevens bevatten. Als het om standaard animaties gaat in plaats van NLA-animaties, raadpleeg dan de instructies voor "Grootschalige NLA-aanmaak".

---

### 3. Toevoegen aan de lijst

![alt text](images/img_1003.png)

⚠️ Let op: De add-on werkt op basis van de lijst, onafhankelijk van de momenteel geselecteerde objecten in de viewport.

---

### 4. NLA Uitlijning / Offset bewerkingen


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Hierboven ziet u een demonstratie van de NLA-uitlijnings- en offsetfuncties.

---

### 5. Geniet van de animatie-magie

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

Met dank aan het Taiwanese merk [SANSUI / 山水品牌](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) voor het leveren van de voorbeeldmodellen.

---
## 🌟 Belangrijke updates
#### v1.0.0 Belangrijke updates
- Lijst exporteren / importeren / toevoegen  
  ![alt text](images/v100_001.png)  
  1. Drie nieuwe functies toegevoegd aan Lijstbewerkingen.
  2. Exporteren en importeren van lijsten gebeurt via *.json bestanden.
  3. "Toevoegen" plaatst items aan het einde van de lijst.
  4. Bij dubbele namen krijgt het eerste item voorrang.
#### v0.9.8 Belangrijke updates  
- Eerste publieke release  
---
## 🧰 Functieoverzicht

#### 1. Lijst initialisatie tool 

![alt text](images/img_2001.png)

- A : Initialiseer en voeg geselecteerde toe    
  Wist de huidige lijstgegevens en voegt de in de Scène geselecteerde objecten toe.  
  <br>
- B : Lijst wissen  
  Wist alle gegevens in de lijst.  
  <br>
- C : Animatiebron  
    Momenteel worden drie typen ondersteund:  
    -  Objectanimatie  
    -  Shape Key animatie  
    -  Materiaalanimatie
  <br>
- D : Objecten in lijst Toevoegen / Verwijderen  
  Bij het toevoegen wordt de lijst **niet** gewist; objecten worden **volgens selectievolgorde** achteraan toegevoegd. Reeds bestaande objecten worden opnieuw achteraan geplaatst. Dit verschilt van de hierboven beschreven methode A. Het verwijderen verschilt ook van 1-J.  
  <br>

- E : Lijstbewerkingen (Dropdown menu)  
  Zie details bij [1-1 Lijstbewerkingen](#1-1-lijstbewerkingen).
  <br>

- F : Geselecteerd item Omhoog / Omlaag  
  Handmatige volgorde aanpassen. Zodra de volgorde handmatig is gewijzigd, wordt dit gedefinieerd als de **"Gecachte originele volgorde"**.
  <br>

- G : Push naar NLA (Dropdown menu)  
  Converteert alleen de objecten in de lijst naar NLA-strips.
  <br>  
  
-  PS. [3. Betekenis van iconen in de lijst](#3-betekenis-van-de-iconen-in-de-lijst)

#### 1-1. Lijstbewerkingen

![alt text](images/img_2002.png)

- H : Initialiseer en voeg geselecteerde toe   
  Wist de lijstgegevens en voegt de in de Scène geselecteerde objecten toe.
  <br>

- I : Vier soorten sortering    
  De belangrijkste is de **Originele volgorde**. Deze add-on onthoudt deze volgorde; de andere drie zijn tijdelijke sorteerstanden.
  <br>

- J : Verwijder geselecteerde uit scène   
  Verwijdert objecten die momenteel in de 3D-scène zijn geselecteerd uit de lijst, in tegenstelling tot 1-D.
  <br>

#### 2. Specificeer offset strips

![alt text](images/img_2003.png)

- K : Drie modi (Strip modus)  
  - Enkele strip : Richt zich op slechts één specifieke strip.
  - Enkel spoor : Behandelt alle strips op een spoor als één geheel (relatieve posities blijven gelijk).
  - Alle sporen : Alle sporen van het object veranderen samen (relatieve posities blijven gelijk).
  <br>

- L : Drie lokatie-instellingen  
  - Welk Slot : Alleen voor Materiaal Modus, berekend van **boven naar beneden** in de NLA-interface.
  - Welk Spoor : Alleen voor Materiaal Modus, berekend van **onder naar boven** in de NLA-interface.
  - Welke Strip : Alleen voor Materiaal Modus, berekend van **links naar rechts** in de NLA-interface.
  <br>

  **!! LET OP: Als het doel niet correct is gespecificeerd, kan NLA geen offset uitvoeren.**

#### 3. NLA uitlijningstools (Initialisatie waarden)
![alt text](images/img_2004.png)

- M : Vijf uitlijningsdoelen (Uitlijningsmodus)  
  - Op max beginframe : Gebaseerd op het **laatste** beginpunt van de strips in de lijst.
  - Op min beginframe : Gebaseerd op het **eerste** beginpunt van de strips in de lijst (Veelgebruikt).
  - Op max eindframe : Gebaseerd op het **laatste** eindpunt van de strips in de lijst (Veelgebruikt).
  - Op min eindframe : Gebaseerd op het **eerste** eindpunt van de strips in de lijst.
  - Op huidige afspeelcursor : Gebaseerd op de huidige positie van de tijdlijn (Meest gebruikt).
  <br>

- N : Drie uitlijningsmethoden  
  - Uitlijnen op begin : Lijn de linkerzijde uit op het doel.
  - Uitlijnen op midden : Lijn het midden uit op het doel.
  - Uitlijnen op einde : Lijn de rechterzijde uit op het doel.
  <br>

- O : Schaal resetten  
  Zet de schaalwaarde van alle NLA-strips in de lijst terug naar 1.
  <br>


#### 4. Eenvoudige modus

![alt text](images/img_2005.png)  
- P : Eenvoudige modus afname [(Gedetailleerde uitleg)](#2-offset-uitleg)  
  Er zijn vier formules voor de offset-berekening: 1. Lineair / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- Q : Offset bedrag (Eenheid: **Frames**)  
  Dit is niet de afstand tussen individuele strips, maar het totale verschil tussen het eerste en het laatste object in de lijst (negatieve waarden zijn mogelijk).
  <br>

- R : Schaal  
  Dit is niet de individuele schaal, maar het verschil in schaal tussen het eerste en het laatste object in de lijst (0 ~ 1).
  <br>

- S : Voer eenvoudige NLA Stride uit (Herhaaldelijk klikken cumuleert de berekening).
  <br>

#### 5. Professionele modus
![alt text](images/img_2006.png)  
  **>> De kern van deze add-on: met eenvoudige instellingen worden offset en schaal automatisch aangepast <<**

- T : Pro begin afname [(Gedetailleerde uitleg)](#2-offset-uitleg)  
  Vier berekeningsformules: 1. Lineair / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- U : Stel beginframe in  
  Bepaalt de **starttijd** van de totale animatie voor alle objecten in de lijst.
  <br>

- V : Offset verhouding (Begin)    
  De hoeveelheid offset vermenigvuldigd met de afname (T), gebruikt om automatisch de beginpunten van alle strips in te stellen.
  <br>

- W : Pro einde afname [(Gedetailleerde uitleg)](#2-offset-uitleg)    
  Vier berekeningsformules: 1. Lineair / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- X : Stel eindframe in    
  Bepaalt de **eindtijd** van de totale animatie voor alle objecten in de lijst.
  <br>

- Y : Offset verhouding (Einde)    
  Het verschil tussen het eerste en laatste object (negatieve waarden mogelijk).
  <br>

- Z : Voer professionele NLA Stride uit (Herhaaldelijk klikken **cumuleert niet**).
  <br>


---

## ❓ Veelgestelde vragen


#### 1. ⚠️ Let op de details van "Gedeelde gegevens (Instanced Data)"

Deze add-on is primair gericht op het verschuiven en uitlijnen van NLA-strips zelf,  
en verwerkt **niet** automatisch de "Instanced Data"-relaties van Blender.

#### Wat zijn gedeelde gegevens?

Wanneer **meerdere objecten dezelfde data-blokken delen**, zijn deze "Instanced".

- Bijvoorbeeld:  
  - Twee objecten delen hetzelfde materiaal.  
  - Of ze delen dezelfde actie (animatie), mesh of andere data-blokken.  

In de NLA Editor lijken dit twee onafhankelijke strips, maar ze **verwijzen naar dezelfde onderliggende data**.
Het resultaat is dat bij gebruik van **NLA Stride voor offset**, de add-on weliswaar strips lijkt te verplaatsen, maar ze nog steeds dezelfde data beïnvloeden, waardoor de **gewenste offset niet wordt bereikt**.


#### ✅ Oplossing (Volg de onderstaande stappen)

> 💡 **Kernoplossing: Maak de data eerst onafhankelijk (Single User) voor de offset.**

Stappen (zoals getoond in de afbeelding):

1. Selecteer de objecten in de 3D viewport.  
2. Ga naar **Object → Relations**.  
3. Klik op **Make Single User**.  
4. Selecteer het type data dat onafhankelijk moet worden (bijv. Object Animation).
5. Nadat de data onafhankelijk is, gebruik je **NLA Stride** voor de offset.  



![alt text](images/img_3001.png)

> Zodra de data onafhankelijk is, heeft elk object zijn eigen "echte NLA-data".
> NLA Stride kan dan **normaal en voorspelbaar de NLA-strips verschuiven**.
---


#### 2. ⚠️ Grootschalige NLA-aanmaak

Deze add-on verwerkt NLA-strips. Animaties die nog geen NLA-strips zijn (Active Actions), worden niet beïnvloed.

#### ✅ Oplossing: Batch Conversie Tool

De add-on biedt een tool om objecten in de lijst in één keer te converteren naar NLA (zie groene pijl hieronder). Let op: dit geldt voor de **Lijst**, niet voor de selectie in de 3D viewport.

![alt text](images/img_3002.png)

---



## 📖 Overige


#### 1. Tips voor Uitlijning en Offset strategieën

- Je kunt in de 3D Viewport op **Alt A** drukken om alles te deselecteren en vervolgens de functie **Selecteer lijstobjecten** gebruiken om te controleren welke objecten precies in de lijst staan.  
<br>

- De **volgorde** is erg belangrijk omdat deze direct de animatiestatus na de offset beïnvloedt. Gebruik indien mogelijk namen om de volgorde te bepalen. Bij zeer veel objecten kun je deze in groepen verwerken.  
<br>

- Als de situatie onoverzichtelijk wordt, gebruik dan de uitlijningstools om alles weer te synchroniseren.  
<br>

- Omdat animatie-offset nu heel eenvoudig is, kun je je volledig concentreren op het maken van één **perfecte beweging**.  
<br>

- Bij bewegingsontwerp: als je de **Locatie** hebt ingesteld, let dan op bij het kopiëren. De animatie kan terugspringen naar dezelfde positie omdat de locatie-informatie in de NLA is vastgelegd. Gebruik in dat geval **Ctrl A** (Apply Transformation) om de nieuwe locatie in de delta-transformaties te schrijven.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Offset uitleg
- Lineaire stapelmodus :  
  - Eenvoudige modus :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  De eenvoudige modus berekent op basis van de oorspronkelijke staat (uiterst links in de afbeelding). Bijvoorbeeld, bij een offset van 100 en een schaal van 1.5, zullen het beginpunt en de lengte van de laatste strip altijd hetzelfde zijn. Maar de verschillende afnamemodi zorgen voor verschillende tussenliggende beginpunten, wat een ander gevoel van offset geeft.

    ---
  - Professionele modus :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  In tegenstelling tot de eenvoudige modus kan de professionele modus zowel het begin als het einde regelen, waardoor er voor beide een aparte afnamemodus kan worden ingesteld.  
  
    ---
  - **Let op** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Als de afnamemodi voor begin en einde **verschillen**, let dan op of de animatiestrips niet te kort worden of verdwijnen.
---

#### 3. Betekenis van de iconen in de lijst

![alt text](images/img_3003.gif)

Icon A : Animatiebron (Modus)
Icon B : Action staat voor algemene animatiegegevens (geen NLA)
Icon C : Beschikbare NLA-gegevens

- De betekenis van de symbolen in B en C verandert afhankelijk van de geselecteerde bron in kolom A:
  - ✔ : Bevat de **correcte** data zoals ingesteld in kolom A.
  - ・ : Bevat data, maar **niet** van het type ingesteld in kolom A.
  - ✕ : Bevat geen data.

Gegevens in het voorbeeld:
| Item | Objectanimatie | Materiaalanimatie | Shape Key animatie |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Actieve actie** | cube.027 | cube.037 | cube.038 | 

- Overig: cube.000 (Heeft alle 3 types NLA) / cube.039 (Heeft totaal geen animatiedata)

---




## 🔧 Technische referentie

  [Blender NLA Officiële Handleiding](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Blender API Officiële Handleiding](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Inhoudsopgave

1. [Snel aan de slag](#-snel-aan-de-slag) 
2. [Belangrijke updates](#-belangrijke-updates) 
3. [Functieoverzicht](#-functieoverzicht)      
4. [Veelgestelde vragen](#-veelgestelde-vragen) 
5. [Overige](#-overige) 
6. [Technische referentie](#-technische-referentie)