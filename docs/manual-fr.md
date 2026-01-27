<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Manuel de l'Utilisateur 

> Ce manuel présente les fonctions et techniques de l'extension NLA-Stride pour Blender, ainsi que des réponses à certains problèmes connus courants.

---

## 📘 Table des Matières

1. [Démarrage Rapide](#Quick_Start)  
2. [Mises à jour de Version](#Version_Updates)
3. [Aperçu des Fonctions](#Feature_Overview)      
4. [Foire Aux Questions (FAQ)](#FAQ) 
5. [Autres](#Others) 
6. [Référence Technique](#Technical_Reference)

---

## 🚀 Démarrage Rapide
<a id="Quick_Start"></a>

### 1. Installation de l'Extension

1. Suivez les étapes d'installation officielles de Blender ( **[Guide d'installation générale](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Après l'installation, vous trouverez le **NLA Stride Tool** dans la vue 3D de Blender, sous l'onglet **Barre Latérale → Animation**. 
<br>![alt text](images/img_1001.png)



---

### 2. Sélectionner des Objets avec Animation  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Sélectionnez un ou plusieurs objets contenant des données d'animation. S'il s'agit d'animations standard au lieu d'animations NLA, veuillez vous référer aux instructions de « Création massive de NLA ».

---

### 3. Ajouter à la Liste

![alt text](images/img_1003.png)

⚠️ Remarque : L'extension fonctionne sur la base de la liste, indépendamment de la sélection d'objets en temps réel dans la vue.

---

### 4. Opérations d'Alignement / Décalage NLA


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Ci-dessus se trouvent des démonstrations des fonctions d'alignement et de décalage NLA.

---

### 5. Profitez de la Magie de l'Animation

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

Remerciements particuliers à la marque taïwanaise [SANSUI / 山水](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) pour avoir fourni les modèles d'exemple.

---
## 🌟 Mises à jour de Version
<a id="Version_Updates"></a>
  
#### v1.0.0 Mises à jour clés
- Exporter / Importer / Ajouter à la Liste 
  ![alt text](images/v100_001.png)  
  1. Trois nouvelles fonctions ajoutées aux Opérations de Liste.
  2. L'exportation et l'importation se font via des fichiers *.json.
  3. « Ajouter » insère les éléments à la fin de la liste.
  4. En cas de noms en double, l'élément existant est prioritaire.
#### v0.9.8 Mises à jour clés  
- Version initiale publique  
---
## 🧰 Aperçu des Fonctions
<a id="Feature_Overview"></a>
 

#### 1. Source d'Animation 

![alt text](images/img_2001.png)

- A : Initialiser et ajouter la sélection    
  Efface les données de la liste actuelle et ajoute les objets sélectionnés dans la Scène.  
  <br>
- B : Vider la liste  
  Efface toutes les données à l'intérieur de la liste.  
  <br>
- C : Source d'animation  
    Actuellement, trois types sont pris en charge :  
    -  Animation d'objet  
    -  Animation de clés de forme (Shape Key)  
    -  Animation de matériau
  <br>
- D : Ajouter / Supprimer des objets dans la liste  
  L'ajout **n'efface pas** la liste ; les objets sont ajoutés à la fin **selon l'ordre de sélection**. Les objets déjà présents seront déplacés à la fin. Cela diffère de la méthode A. La suppression diffère également de 1-J.  
  <br>

- E : Opérations de liste (Menu déroulant)  
  Voir les détails dans [1-1 Opérations de liste](#List_Functions).
  <br>

- F : Déplacer l'élément sélectionné vers le Haut / Bas  
  Ajuste manuellement l'ordre. Une fois ajusté, cela est défini comme l' **« Ordre Original en Cache »**.
  <br>

- G : Pousser vers NLA (Menu déroulant)  
  Convertit uniquement les objets de la liste en bandes (strips) NLA.
  <br>  
  
-  PS. [3. Signification des icônes dans la liste](#List_Icon_Meanings)

#### 1-1. Opérations de liste
<a id="List_Functions"></a>

![alt text](images/img_2002.png)

- H : Initialiser et ajouter la sélection   
  Efface les données de la liste et ajoute les objets sélectionnés dans la Scène.
  <br>

- I : Quatre états de tri    
  Le plus important est l' **Ordre original** enregistré par l'extension ; les trois autres sont des états de tri temporaires.
  <br>

- J : Supprimer la sélection de la scène   
  Supprime de la liste les objets actuellement sélectionnés dans la scène 3D (différent de 1-D).
  <br>

#### 2. Spécifier les bandes de décalage

![alt text](images/img_2003.png)

- K : Trois modes de bande (Mode bande)  
  - Bande unique : Cible une seule bande spécifique.
  - Piste unique : Traite toutes les bandes d'une piste comme une seule unité (les positions relatives sont conservées).
  - Toutes les pistes : Toutes les pistes de l'objet changent ensemble (les positions relatives sont conservées).
  <br>

- L : Trois localisateurs  
  - Quel emplacement (Slot) : Pour le Mode Matériau uniquement, calculé de **haut en bas** dans l'interface NLA.
  - Quelle piste : Calculé de **bas en haut** dans l'interface NLA.
  - Quelle bande : Calculé de **gauche à droite** dans l'interface NLA.
  <br>

  **!! REMARQUE : Si la cible n'est pas correctement spécifiée, le décalage NLA ne pourra pas être exécuté.**

#### 3. Outils d'alignement NLA (Valeurs d'initialisation)
![alt text](images/img_2004.png)

- M : Cinq modes d'alignement (Mode alignement)  
  - Sur l'image de début max : Basé sur le **dernier** point de début des bandes de la liste.
  - Sur l'image de début min : Basé sur le **premier** point de début des bandes de la liste (Courant).
  - Sur l'image de fin max : Basé sur le **dernier** point de fin des bandes de la liste (Courant).
  - Sur l'image de fin min : Basé sur le **premier** point de fin des bandes de la liste.
  - Sur le temps actuel : Basé sur la position actuelle de la tête de lecture (Le plus utilisé).
  <br>

- N : Trois méthodes d'alignement  
  - Aligner le début : Aligne le côté gauche sur la cible (courant pour les points de début).
  - Aligner le milieu : Aligne le centre sur la cible.
  - Aligner la fin : Aligne le côté droit sur la cible (courant pour les points de fin).
  <br>

- O : Réinitialiser l'échelle  
  Remet la valeur d'échelle de toutes les bandes NLA de la liste à 1.
  <br>


#### 4. Mode Simple

![alt text](images/img_2005.png)  
- P : Atténuation en mode simple [(Description détaillée)](#Stride_Description)  
  Il existe quatre formules pour le calcul du décalage : 1. Linéaire / 2. Fondu entrant (Ease In) / 3. Fondu sortant (Ease Out) / 4. Fondu entrant/sortant (Ease In Out).
  <br>

- Q : Quantité de décalage (Unité : **Images**)  
  C'est la différence totale entre le premier et le dernier objet de la liste (accepte les valeurs négatives).
  <br>

- R : Échelle  
  C'est la différence d'échelle entre le premier et le dernier objet de la liste (0 ~ 1).
  <br>

- S : Exécuter Simple NLA Stride (Cliquer à répétition cumule le calcul).
  <br>

#### 5. Mode Professionnel
![alt text](images/img_2006.png)  
  **>> Le cœur de cette extension : avec des réglages simples, le décalage et l'échelle des bandes s'ajustent automatiquement <<**

- T : Atténuation de début Pro [(Description détaillée)](#Stride_Description)  
  Quatre formules : 1. Linéaire / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- U : Définir l'image de début  
  Définit le temps de **début** de l'animation globale pour tous les objets de la liste.
  <br>

- V : Ratio de décalage (Début)    
  La quantité de décalage multipliée par l'atténuation (T), utilisée pour configurer automatiquement les points de début de toutes les bandes.
  <br>

- W : Atténuation de fin Pro [(Description détaillée)](#Stride_Description)    
  Quatre formules : 1. Linéaire / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- X : Définir l'image de fin    
  Définit le temps de **fin** de l'animation globale pour tous les objets de la liste.
  <br>

- Y : Ratio de décalage (Fin)    
  Différence entre le premier et le dernier objet (accepte les valeurs négatives).
  <br>

- Z : Exécuter Professionnel NLA Stride (Cliquer à répétition **ne cumule pas**).
  <br>


---

## ❓ Foire Aux Questions (FAQ)
<a id="FAQ"></a>


#### 1. ⚠️ Attention aux détails des « Données Instanciées (Instanced Data) »

Cette extension se concentre principalement sur le déplacement et l'alignement des bandes NLA elles-mêmes,  
et **ne gère pas** automatiquement les relations de « Données Instanciées » de Blender.

#### Que sont les données instanciées ?

Lorsque **plusieurs objets partagent le même bloc de données**, ces données sont « Instanciées ».

- Par exemple :  
  - Deux objets partageant le même matériau.  
  - Ou partageant la même action (animation), maillage, ou d'autres blocs de données.  

Dans l'Éditeur NLA, cela ressemble à deux bandes indépendantes, mais elles **pointent vers les mêmes données sous-jacentes**.
En conséquence, en utilisant **NLA Stride pour le décalage**, l'extension semble déplacer les bandes, mais comme elles partagent les données, le **décalage souhaité ne sera pas atteint**.


#### ✅ Solution (Suivez les étapes ci-dessous)

> 💡 **Clé : Rendre les données « utilisateur unique » (Single User) avant le décalage.**

Étapes (comme illustré sur l'image) :

1. Sélectionnez les objets dans la vue 3D.  
2. Allez dans **Objet → Relations**.  
3. Cliquez sur **Rendre utilisateur unique (Make Single User)**.  
4. Sélectionnez le type de données requis (ex : Animation d'objet).
5. Une fois les données indépendantes, utilisez **NLA Stride** pour le décalage.  



![alt text](images/img_3001.png)

> Une fois indépendantes, chaque objet possède ses propres « vraies données NLA ».
> NLA Stride peut alors **décaler les bandes NLA normalement et de manière prévisible**.
---


#### 2. ⚠️ Création massive de NLA

Cette extension travaille sur les bandes NLA. Les animations qui n'ont pas été converties en bandes NLA (Actions actives) ne seront pas affectées.

#### ✅ Solution : Outil de conversion massive

L'extension propose un outil pour convertir les objets de la liste en NLA en une seule fois (flèche verte ci-dessous). Remarque : cela affecte la **Liste**, pas seulement la sélection 3D.

![alt text](images/img_3002.png)

---



## 📖 Autres
<a id="Others"></a>


#### 1. Conseils pour les stratégies d'Alignement et de Décalage

- Vous pouvez appuyer sur **Alt A** dans la vue 3D pour tout désélectionner, puis utiliser la fonction **Sélectionner les objets de la liste** pour vérifier exactement ce qui se trouve dans votre liste.  
<br>

- L' **ordre** est crucial car il affecte directement l'état de l'animation après le décalage. Si possible, utilisez des noms pour déterminer l'ordre. Pour de nombreux objets, envisagez d'utiliser la fonction [`Exporter / Importer`](#Version_Updates) ou de traiter par lots.  
<br>

- Si la situation devient confuse, utilisez les outils d'alignement pour synchroniser tout à nouveau vers un point de départ.  
<br>

- Puisque le décalage d'animation est devenu très simple, concentrez-vous sur la création d'un **mouvement parfait**.  
<br>

- Concernant la conception du mouvement : Si la **Position** est animée, notez qu'en copiant, l'animation peut sauter à la même position originale. Dans ce cas, utilisez **Ctrl A** (Appliquer transformation) pour écrire le nouvel emplacement dans les données de **Transformation Delta**.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Description de Stride
<a id="Stride_Description"></a>

- Mode d'empilement linéaire :  
  - Mode Simple :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Le mode simple calcule en fonction de l'état d'origine (image la plus à gauche). Par exemple, avec un Décalage de 100 et une Échelle de 1.5, le point de début et la longueur de la dernière bande seront toujours les mêmes ; mais les différents modes d'atténuation créeront des points de début intermédiaires différents, donnant une sensation de décalage variée.

    ---
  - Mode Professionnel :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Contrairement au mode simple, le mode professionnel permet de contrôler séparément le début et la fin, avec un mode d'atténuation distinct pour chacun.  
  
    ---
  - **Attention** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Si les modes d'atténuation pour le début et la fin sont **différents**, surveillez si les bandes d'animation ne deviennent pas trop courtes ou ne disparaissent pas.
---

#### 3. Signification des icônes dans la liste
<a id="List_Icon_Meanings"></a>

![alt text](images/img_3003.gif)

Icône A : Mode de données
Icône B : Action représente les données d'animation standard (non-NLA)
Icône C : Données NLA disponibles

- La signification des symboles dans B et C change selon le Mode de données sélectionné dans la colonne A :
  - ✔ : Contient les données **correctes** correspondant au mode en A.
  - ・ : Contiene des données, mais **pas** du type défini en A.
  - ✕ : Ne contient pas de données.

Données dans l'exemple :
| Élément | Animation objet | Animation matériau | Animation Shape Key |
|------|------|------|--------|
| **Bande NLA** | cube.049 | cube.050 | cube.051 | 
| **Action active** | cube.027 | cube.037 | cube.038 | 

- Autres : cube.000 (Possède les 3 types de NLA) / cube.039 (Aucune donnée d'animation)

---




## 🔧 Référence Technique
<a id="Technical_Reference"></a>

  [Manuel Officiel de Blender NLA](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Manuel Officiel de Blender API](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Table des Matières

1. [Démarrage Rapide](#Quick_Start) 
2. [Mises à jour de Version](#Version_Updates) 
3. [Aperçu des Fonctions](#Feature_Overview)      
4. [Foire Aux Questions (FAQ)](#FAQ) 
5. [Autres](#Others) 
6. [Référence Technique](#Technical_Reference)