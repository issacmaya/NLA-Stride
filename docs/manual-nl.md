<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Gebruikershandleiding (Nederlands)

> Deze handleiding introduceert de functies en tips voor de NLA-Stride Blender addon, inclusief antwoorden op enkele veelvoorkomende bekende problemen.

---

## 📘 Inhoudsopgave

1. [Snel aan de slag](#-snel-aan-de-slag)  
2. [Functieoverzicht](#-functieoverzicht)      
3. [Veelgestelde vragen](#-veelgestelde-vragen) 
4. [Overige](#-overige) 
5. [Technische referentie](#-technische-referentie)

---

## 🚀 Snel aan de slag

### 1. Addon installatie

1. Volg de officiële Blender installatiestappen ( **[Algemene installatiegids](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Na de installatie vindt u de **NLA Stride Tool** in de Blender 3D Viewport onder het tabblad **Zijbalk → Animatie**. 
<br>![alt text](images/img_1001.png)



---

### 2. Selecteer objecten met animatie  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Selecteer een of meer objecten die animatiegegevens bevatten. Als ze standaard acties bevatten in plaats van NLA-strips, raadpleeg dan de sectie "Batchgewijs naar NLA pushen" verderop.  

---

### 3. Toevoegen aan lijst  
![alt text](images/img_1003.png)  

⚠️ Let op: De addon werkt op basis van de lijst, ongeacht de huidige selectie in de viewport.  

---

### 4. NLA uitlijnen / Offset bewerkingen  
<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  
<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  
<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  

Hierboven ziet u demonstraties van de NLA-uitlijnings- en offsetfuncties.  

---

### 5. Geniet van de animatiemagie  
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

Met speciale dank aan het Taiwanese merk [SANSUI](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) voor het leveren van de voorbeeldmodellen.  

---

## 🧰 Functieoverzicht

#### 1. Animatiebron 
![alt text](images/img_2001.png)  

- A : Initialiseer en voeg geselecteerde toe  
  Wist eerst de lijst en voegt vervolgens de momenteel geselecteerde objecten uit de scène toe.  
<br>

- B : Lijst leegmaken  
  Verwijdert alle gegevens uit de lijst.  
<br>

- C : Animatiebron  
  Ondersteunt momenteel drie typen: Objectanimatie / Shape Key-animatie / Materiaalanimatie.  
<br>

- D : Lijstitems toevoegen / verwijderen  
  Toevoegen wist de lijst **niet**; objecten worden aan het einde toegevoegd in de **volgorde van selectie**. Als een object al in de lijst staat, wordt het naar het einde verplaatst. De toevoeglogica verschilt van A. De verwijderknop verschilt ook van 1-J.  
<br>

- E : Lijstbewerkingen (dropdownmenu)  
  Zie "1-1 Lijstbewerkingen" voor details.  
<br>

- F : Item omhoog / omlaag verplaatsen  
  Pas de volgorde handmatig aan. Eenmaal aangepast, wordt dit resultaat gedefinieerd als de **"Oorspronkelijke volgorde"**.  
<br>

- G : Push naar NLA (dropdownmenu)  
  Zet de actieve actie om naar NLA-strips, alleen voor objecten in de lijst.  
<br>

- PS. [3. Betekenis lijstpictogrammen](#3-betekenis-lijstpictogrammen)  

#### 1-1. Lijstbewerkingen
![alt text](images/img_2002.png)  

- H : Initialiseer en voeg geselecteerde toe  
  Wist eerst de lijst en voegt vervolgens de momenteel geselecteerde objecten uit de scène toe.  
<br>

- I : Vier sorteeropties  
  De belangrijkste is **Herstel oorspronkelijke volgorde**, aangezien deze addon die volgorde onthoudt. De andere drie zijn automatische sorteringen.  
<br>

- J : Verwijder scène selectie  
  Verwijdert objecten uit de lijst op basis van de huidige selectie in de viewport. Dit verschilt van de 1-D verwijderknop.  

#### 2. Gegevenspositionering
![alt text](images/img_2003.png)  

- K : Drie stripmodi  
  - Enkele strip : Richt zich op slechts één specifieke strip.  
  - Enkel spoor : Behandelt alle strips op één spoor als één groep (relatieve posities blijven ongewijzigd).  
  - Alle sporen : Gelijk aan het gelijktijdig wijzigen van alle sporen van het object (relatieve posities blijven ongewijzigd).  
<br>

- L : Drie positioneringspunten  
  - Welk slot : (Alleen materiaalmodus) Berekend van **boven naar beneden** in de UI.  
  - Welk spoor : Berekend van **beneden naar boven** in de NLA-editor.  
  - Welke strip : Berekend van **links naar rechts** in de NLA-editor.  
<br>

  **!! Let op: Als het doel niet correct gepositioneerd is, kan NLA Stride geen offsets uitvoeren.** #### 3. NLA uitlijningstools (Initialisatiewaarden)
![alt text](images/img_2004.png)  

- M : Vijf uitlijningsdoelen  
  - Op Max Start Frame : Lijnt uit op het **begin** van de **laatst** startende strip in de lijst.  
  - Op Min Start Frame : Lijnt uit op het **begin** van de **eerst** startende strip (Veelgebruikt).  
  - Op Max Eind Frame : Lijnt uit op het **einde** van de **laatst** eindigende strip (Veelgebruikt).  
  - Op Min Eind Frame : Lijnt uit op het **einde** van de **eerst** eindigende strip.  
  - Op Huidige Tijd : Lijnt uit op de huidige positie van de afspeelkop (Meest algemeen).  
<br>

- N : Drie uitlijningsmodi  
  - Uitlijnen op begin : De linkerkant van de strip wordt uitgelijnd met het doel. Meestal gebruikt voor uitlijning op het **Begin**.  
  - Uitlijnen op midden : Het midden van de strip wordt uitgelijnd met het doel.  
  - Uitlijnen op einde : De rechterkant van de strip wordt uitgelijnd met het doel. Meestal gebruikt voor uitlijning op het **Einde**.  
<br>

- O : Schaal resetten  
  Herstelt de schaalwaarde van alle NLA-strips in de lijst naar 1.0.  


#### 4. Eenvoudige modus
![alt text](images/img_2005.png)  

- P : Falloff-modus [(Gedetailleerde beschrijving)](#2-beschrijving-offset)  
  - Vier rekenformules: 1. Lineair / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- Q : Offset bedrag (Eenheid: **frames**)  
  - Dit is niet de tussenruimte tussen individuele strips, maar het totale verschil tussen het eerste en laatste object in de lijst (negatieve waarden toegestaan).  
<br>

- R : Schaal  
  - Geen incrementele schaal, maar het schaalverschil tussen het eerste en laatste object in de lijst (0 ~ 1).  
<br>

- S : Voer Eenvoudige NLA Stride uit (herhaaldelijk klikken zal berekeningen cumuleren).  
<br>

#### 5. Professionele modus
![alt text](images/img_2006.png)  
  **>> De kern van deze addon. Met eenvoudige instellingen worden strip-offsets en schaal automatisch aangepast <<** - T : Falloff-modus [(Gedetailleerde beschrijving)](#2-beschrijving-offset)  
  - Vier rekenformules: 1. Lineair / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- U : Stel startframe in  
  - Stelt de **Starttijd** in voor de gehele animatiereeks van alle objecten in de lijst.  
<br>

- V : Offsetverhouding (Kop)  
  - Vermenigvuldigd met de Falloff-modus (T) om de offsetwaarde te berekenen, gebruikt voor automatische positionering van alle strip-startpunten.  
<br>

- W : Falloff-modus [(Gedetailleerde beschrijving)](#2-beschrijving-offset)  
  - Vier rekenformules: 1. Lineair / 2. Ease In / 3. Ease Out / 4. Ease In Out.  
<br>

- X : Stel eindframe in  
  - Stelt de **Eindtijd** in voor de gehele animatiereeks van alle objecten in de lijst.  
<br>

- Y : Offsetverhouding (Staart)  
  - De offsetverhouding voor de eindpunten van de strips.  
<br>

- Z : Voer Professionele NLA Stride uit (herhaaldelijk klikken zal berekeningen **niet** cumuleren).  
<br>


---

## ❓ Veelgestelde vragen


#### 1. ⚠️ Let op "Geïnstantieerde gegevens (Instanced Data)"

Deze addon verwerkt voornamelijk de offset en uitlijning van NLA-strips zelf; het verwerkt **niet** automatisch "geïnstantieerde gegevens" relaties binnen Blender.  

#### Wat zijn geïnstantieerde gegevens?

Wanneer **meerdere objecten dezelfde gegevens delen**, zijn die gegevensblokken "geïnstantieerd".  

- Bijvoorbeeld:  
  - Twee objecten die hetzelfde materiaal delen.  
  - Het delen van dezelfde actie (Action), mesh of andere gegevensblokken.  

In de NLA-editor kunnen dit twee onafhankelijke strips lijken, maar in werkelijkheid **verwijzen ze naar hetzelfde onderliggende gegevensblok**.
Hierdoor lijkt de addon bij het gebruiken van **NLA Stride voor offset** verschillende strips te verplaatsen, maar in werkelijkheid wijzigt het hetzelfde gegeven, waardoor het **verwachte offset-effect niet wordt bereikt**.


#### ✅ Oplossing (Volg de stappen in de afbeelding)

> 💡 **Kernidee: Maak gegevens onafhankelijk voordat u de offset uitvoert.** Stappen (zoals getoond in de afbeelding):  

1. Selecteer de te verwerken objecten in de 3D Viewport.  
2. Ga naar **Object → Relations**.  
3. Klik op **Make Single User**.  
4. Selecteer de gegevenstypen die onafhankelijk moeten worden (bijv. Objectanimatie).  
5. Zodra de gegevens onafhankelijk zijn, gebruikt u **NLA Stride** voor de offset.  



![alt text](images/img_3001.png)  

> Wanneer gegevens onafhankelijk zijn, heeft elk object zijn eigen unieke NLA-gegevens.
> NLA Stride kan dan **helpen om de NLA-strips normaal en voorspelbaar te verspringen**.  

---


#### 2. ⚠️ Batchgewijs NLA aanmaken

Deze addon richt zich op NLA-strips. Als animatiegegevens nog niet zijn "gepusht" naar NLA-strips, worden ze niet beïnvloed.  

#### ✅ Oplossing: Push naar NLA tool

De addon biedt een batchgewijze conversietool (aangegeven met groene pijlen hieronder). Let op: dit geldt voor objecten **in de lijst**, niet voor de selectie in de viewport.  

![alt text](images/img_3002.png)  

---



## 📖 Overige


#### 1. Tips voor uitlijnings- en offsetstrategie

- U kunt eerst op **Alt A** drukken in de 3D Viewport om alles te deselecteren, en vervolgens de functie **Selecteer lijstobjecten** gebruiken om precies te bevestigen wie er in uw lijst staan.  
<br>

- De **Volgorde** is cruciaal, omdat deze direct van invloed is op de animatietoestand na de offset. Gebruik indien mogelijk naamgevingsregels om de volgorde te bepalen. Verwerk grote hoeveelheden objecten in batches.  
<br>

- Als het een puinhoop wordt, gebruik dan de uitlijningstools om eerst alles te uniformeren.  
<br>

- Omdat animatie-offsetting erg eenvoudig wordt, kunt u uw energie richten op het maken van één **perfecte beweging**.  
<br>

- Als uw bewegingsontwerp **Locatie** bevat, wees dan voorzichtig bij het dupliceren; bij het afspelen kan de animatie terugspringen naar dezelfde positie omdat de locatie-informatie in de NLA is geschreven. In dit geval kunt u **Ctrl A** gebruiken om transformaties toe te passen en de nieuwe positie in de **Delta Transforms** gegevens te schrijven.  
<br>![alt text](images/img_4001.png)  

---

#### 2. Beschrijving offset
- Lineaire stapelmodus :  
  - Eenvoudige modus :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  De eenvoudige modus berekent op basis van de oorspronkelijke staat (uiterst links in de afbeelding). Zoals getoond, met Offset op 100 en Schaal op 1.5, zullen het startpunt en de lengte (eindpunt) van de laatste strip altijd hetzelfde zijn; maar door de verschillende falloff-modi verschilt het startpunt van de andere strips, wat een ander offset-gevoel geeft.  

    ---
  - Professionele modus :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Het enige verschil met de eenvoudige modus is dat de professionele modus controle biedt over zowel het begin (Kop) als het einde (Staart), waardoor er twee afzonderlijk instelbare falloff-modi zijn.  
  
    ---
  - **Let op** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Let op dat als de twee falloff-modi voor begin en einde **verschillend** zijn, u moet controleren of er problemen ontstaan met de animatiestrips (te kort worden of verdwijnen).  

---

#### 3. Betekenis lijstpictogrammen

![alt text](images/img_3003.gif)  

Pictogram A : Gegevensmodus  
Pictogram B : Action staat voor standaard animatiegegevens (niet-NLA).  
Pictogram C : Bestaande NLA-gegevens.  

- De betekenis van de pictogrammen in B en C verandert op basis van de gegevensmodus in kolom A:  
  - ✔ : Bevat de **juiste** gegevens die overeenkomen met de modus in kolom A.  
  - ・ : Bevat gegevens, maar **niet** van het type dat in kolom A is ingesteld.  
  - ✕ : Geen gegevens gevonden.  

Gegevens in viewport:  
| Item | Objectanimatie | Materiaalanimatie | Shape Key-animatie |
|------|------|------|--------|
| **NLA Strip** | cube.049 | cube.050 | cube.051 | 
| **Actieve Actie** | cube.027 | cube.037 | cube.038 |  

- Overige : cube.000 (heeft alle drie de NLA-typen) / cube.039 (geen enkele animatiegegeven).  

---

## 🔧 Technische referentie

  [Blender NLA Officiële Handleiding](https://docs.blender.org/manual/en/latest/editors/nla/index.html)  

  [Blender API Officiële Handleiding](https://docs.blender.org/api/current/bpy.ops.nla.html)  

  


## 📘 Inhoudsopgave

1. [Snel aan de slag](#-snel-aan-de-slag)  
2. [Functieoverzicht](#-functieoverzicht)      
3. [Veelgestelde vragen](#-veelgestelde-vragen) 
4. [Overige](#-overige) 
5. [Technische referentie](#-technische-referentie)
