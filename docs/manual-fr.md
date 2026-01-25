<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Manuel d'utilisation (Français)

> Ce manuel présente les fonctions et astuces du module complémentaire NLA-Stride pour Blender, ainsi que des réponses à certains problèmes connus.

---

## 📘 Sommaire

1. [Démarrage rapide](#-démarrage-rapide)  
2. [Points forts de la version](#-points-forts-de-la-version)
3. [Aperçu des fonctionnalités](#-aperçu-des-fonctionnalités)      
4. [FAQ](#-faq) 
5. [Autres astuces](#-autres-astuces) 
6. [Référence technique](#-référence-technique)

---

## 🚀 Démarrage rapide

### 1. Installation de l'Add-on

1. Utilisez les étapes d'installation officielles de Blender ( **[Guide général d'installation](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Après l'installation, vous trouverez **NLA Stride Tool** dans la vue 3D de Blender, onglet **Barre latérale → Animation**. 
<br>![alt text](images/img_1001.png)



---

### 2. Sélectionner des objets avec animation  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Sélectionnez un ou plusieurs objets contenant des données d'animation. Si vous utilisez des animations standard au lieu de bandes NLA, veuillez vous référer aux instructions « Pousser les animations vers le NLA ».

---

### 3. Ajouter à la liste

![alt text](images/img_1003.png)

⚠️ Remarque : Le module fonctionne sur la base de la liste, quels que soient les objets actuellement sélectionnés dans la scène.

---

### 4. Opérations d'alignement / décalage NLA


<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  

<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  

<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  


Les schémas ci-dessus illustrent les fonctions d'alignement et de décalage NLA.

---

### 5. Profitez de l'animation

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

Modèle d'exemple fourni gracieusement par [SANSUI Taiwan](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE).

---
## 🌟 Points forts de la version
#### Points forts v1.0.0
- Exporter / Importer / Ajouter à la liste 
  ![alt text](images/v100_001.png)  
  1. Ajout de trois fonctions dans les opérations de liste.
  2. L'exportation et l'importation utilisent le format *.json.
  3. « Ajouter » insère les éléments à la fin de la liste.
  4. En cas de noms en double, la première occurrence rencontrée est prioritaire.
#### Points forts v0.9.8  
- Première version publique  
---
## 🧰 Aperçu des fonctionnalités

#### 1. Outil d'initialisation de liste 

![alt text](images/img_2001.png)

- A : Initialiser et ajouter la sélection    
  Efface les données de la liste puis ajoute les objets actuellement sélectionnés dans la scène.
  <br>
- B : Vider la liste  
  Efface toutes les données de la liste.
  <br>
- C : Source d'animation  
    Prend actuellement en charge trois types :
    - Animation d'objet  
    - Animation de Shape Key (Clés de forme)  
    - Animation de matériau
  <br>
- D : Ajouter / Supprimer des objets de la liste  
  L'ajout **n'efface pas** les éléments existants ; les objets sont ajoutés à la fin **dans l'ordre de sélection**. La suppression ici diffère de 1-J.
  <br>

- E : Opérations de liste (Menu déroulant)  
  Voir [1-1 Opérations de liste](#1-1-opérations-de-liste) pour plus de détails.
  <br>

- F : Monter / Descendre l'élément sélectionné  
  Ajustez manuellement le tri. Si l'ordre est modifié, le résultat est défini comme l'**« Ordre original »**.
  <br>

- G : Pousser les animations vers le NLA (Menu déroulant)  
  Convertit les animations en bandes NLA uniquement pour les objets de la liste.
  <br>  
  
-  PS. [3. Légende des icônes de liste](#3-légende-des-icônes-de-liste)

#### 1-1. Opérations de liste

![alt text](images/img_2002.png)

- H : Initialiser et ajouter la sélection   
  Efface les données de la liste et ajoute les objets actuellement sélectionnés.
  <br>

- I : Modes de tri    
  Comprend l'**Ordre original** (suivi par l'add-on) et trois autres méthodes de tri.
  <br>

- J : Supprimer la sélection de la scène   
  Supprime de la liste les objets actuellement sélectionnés dans la scène.
  <br>

#### 2. Spécifier les bandes de décalage

![alt text](images/img_2003.png)

- K : Mode de bande  
  - Bande unique : Cible une seule bande spécifique.
  - Piste unique : Traite toutes les bandes d'une piste comme une seule unité (conserve les positions relatives).
  - Toutes les pistes : Toutes les pistes de l'objet changent ensemble (conserve les positions relatives).
  <br>

- L : Positionnement Slot/Piste/Bande  
  - Slot : Mode matériau uniquement, calculé de **haut en bas** dans l'interface.
  - Piste : Calculée de **bas en haut** dans l'éditeur NLA.
  - Bande : Calculée de **gauche à droite** dans l'éditeur NLA.
  <br>

  **!! Remarque : Si la cible n'est pas correctement localisée, NLA Stride ne peut pas fonctionner.**

#### 3. Outils d'alignement NLA (Valeurs initiales)
![alt text](images/img_2004.png)

- M : Cible du mode d'alignement  
  - Par image de début max : Aligne sur le **début** de la bande commençant le plus **tard** dans la liste.
  - Par image de début min : Aligne sur le **début** de la bande commençant le plus **tôt** dans la liste (Courant).
  - Par image de fin max : Aligne sur la **fin** de la bande se terminant le plus **tard** dans la liste (Courant).
  - Par image de fin min : Aligne sur la **fin** de la bande se terminant le plus **tôt** dans la liste.
  - Par temps actuel : Aligne sur la position actuelle de la tête de lecture (Très courant).
  <br>

- N : Position d'alignement  
  - Aligner au début : Aligne le côté gauche sur la cible.
  - Aligner au milieu : Aligne le centre sur la cible.
  - Aligner à la fin : Aligne le côté droit sur la cible.
  <br>

- O : Réinitialiser l'échelle  
  Réinitialise l'échelle de toutes les bandes NLA spécifiées dans la liste à 1.
  <br>


#### 4. Mode simple

![alt text](images/img_2005.png)  
- P : Mode d'atténuation (Falloff) [(Description détaillée)](#2-description-du-décalage)  
  Quatre formules de calcul : 1. Linéaire / 2. Ease In / 3. Ease Out / 4. Ease In Out.
  <br>

- Q : Valeur de décalage (Unité : **Images**)  
  Il ne s'agit pas de l'écart équidistant entre les bandes, mais de la différence totale entre le premier et le dernier objet de la liste (autorise les valeurs négatives).
  <br>

- R : Échelle  
  Il ne s'agit pas d'une mise à l'échelle équidistante, mais de la différence d'échelle entre le premier et le dernier objet (0 ~ 1).
  <br>

- S : Exécuter le NLA Stride simple (Les valeurs s'accumulent en cas de clics répétés).
  <br>

#### 5. Mode professionnel
![alt text](images/img_2006.png)  
  **>> La fonctionnalité clé : définissez les points de début et de fin, et les bandes se décaleront et se redimensionneront automatiquement. <<**

- T : Atténuation de début Pro [(Description détaillée)](#2-description-du-décalage)  
  Formule de calcul du décalage : Linéaire, Ease In, Ease Out ou Ease In Out.
  <br>

- U : Définir l'image de début  
  Définit le temps de **Début** global pour toute la séquence d'animation de la liste.
  <br>

- V : Ratio de décalage  
  La valeur de décalage multipliée par le mode d'atténuation (T), utilisée pour automatiser le positionnement de l'image de début.
  <br>

- W : Atténuation de fin Pro [(Description détaillée)](#2-description-du-décalage)    
  Formule de calcul du décalage : Linéaire, Ease In, Ease Out ou Ease In Out.
  <br>

- X : Définir l'image de fin    
  Définit le temps de **Fin** global pour toute la séquence d'animation de la liste.
  <br>

- Y : Ratio de décalage    
  Différence entre les images de fin du premier et du dernier objet (autorise les valeurs négatives).
  <br>

- Z : Exécuter le NLA Stride professionnel (Les valeurs **ne s'accumulent pas**).
  <br>


---

## ❓ FAQ


#### 1. ⚠️ Attention aux détails des « Données instanciées (Instanced Data) »

Ce module cible les bandes NLA elles-mêmes pour le décalage et l'alignement,  
il **ne gère pas** automatiquement les relations de « Données instanciées » de Blender.

#### Que sont les données instanciées ?

Lorsque **plusieurs objets partagent le même bloc de données**, ces données sont dites « Instanciées ».

- Par exemple :  
  - Deux objets partageant le même Matériau.  
  - Partageant la même Action, le même Maillage (Mesh) ou d'autres blocs de données.  

Dans l'éditeur NLA, elles ressemblent à deux bandes indépendantes, mais elles **pointent vers les mêmes données en coulisses**.
Par conséquent, lors de l'utilisation de **NLA Stride pour décaler**, le module déplace les bandes, mais comme elles influencent les mêmes données sous-jacentes, l'**effet de décalage attendu ne sera pas obtenu**.


#### ✅ Solution (Suivez la capture d'écran ci-dessous)

> 💡 **Pratique clé : Rendre les données indépendantes avant le décalage**

Étapes :

1. Sélectionnez les objets dans la vue 3D.  
2. Allez dans **Objet → Relations**.  
3. Cliquez sur **Rendre utilisateur unique (Make Single User)**.  
4. Sélectionnez les types de données qui doivent être indépendantes.
5. Une fois les données indépendantes, utilisez **NLA Stride** pour effectuer le décalage.  



![alt text](images/img_3001.png)

> Une fois les données indépendantes, chaque objet possède ses propres « Données NLA réellement uniques ».
> NLA Stride décalera alors les bandes NLA de manière normale et prévisible.
---


#### 2. ⚠️ Poussée groupée vers le NLA

Cet add-on fonctionne spécifiquement sur les bandes NLA. Les données d'animation qui n'ont pas été « poussées » (pushed) vers le NLA ne seront pas affectées.

#### ✅ Solution : Outil de conversion groupée

Le module fournit un outil pour pousser les animations vers le NLA pour tous les objets **de la liste** (flèche verte ci-dessous). Remarque : cela cible la liste, pas seulement la sélection 3D.

![alt text](images/img_3002.png)

---



## 📖 Autres astuces


#### 1. Stratégie d'alignement et de décalage

- Vous pouvez appuyer sur **Alt A** dans la vue 3D pour tout désélectionner, puis utiliser la fonction **Sélectionner les objets de la liste** pour vérifier exactement quels objets sont dans votre liste.  
<br>

- L'**Ordre** étant crucial (il affecte directement le résultat du décalage), essayez d'utiliser les noms pour déterminer l'ordre. Si vous avez de nombreux objets, traitez-les par lots.  
<br>

- Si la situation devient confuse, utilisez l'outil d'alignement pour tout réinitialiser sur un point de départ unifié.  
<br>

- Puisque le décalage devient facile, concentrez-vous d'abord sur la création d'un **mouvement dynamique parfait**.  
<br>

- Si votre animation implique la **Position (Location)**, les copies pourraient revenir à la même position initiale. Utilisez **Ctrl A** pour appliquer les transformations aux données de **Delta Transform**.  
  <br>![alt text](images/img_4001.png)  

---

#### 2. Description du décalage
- Mode d'atténuation linéaire :  
  - Mode simple :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Le mode simple calcule en fonction de l'état d'origine (à gauche). Par exemple : Décalage 100, Échelle 1.5. Le début et la longueur de la dernière bande correspondront aux paramètres, mais les bandes intermédiaires varieront selon le mode d'atténuation.

    ---
  - Mode professionnel :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  Contrairement au mode simple, le mode professionnel contrôle à la fois le Début (Head) et la Fin (Tail), permettant des modes d'atténuation distincts pour chaque extrémité.  
  
    ---
  - **Remarque** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Si les modes d'atténuation de début et de fin sont **différents**, veillez à ce que les bandes ne deviennent pas trop courtes ou ne disparaissent pas.
---

#### 3. Légende des icônes de liste

![alt text](images/img_3003.gif)

Icône A : Mode source d'animation
Icône B : L'Action représente des données d'animation générales (Pas encore dans le NLA)
Icône C : Données NLA disponibles

- Les symboles en B et C changent selon le mode source (A) :
  - ✔ : Contient des données **Correctes** correspondant au Mode A.
  - ・ : Contient des données, mais elles ne correspondent **PAS** au Mode A.
  - ✕ : Aucune donnée trouvée.

Données dans l'exemple :
| Élément | Anim. Objet | Anim. Matériau | Anim. Shape Key |
|------|------|------|--------|
| **Bande NLA** | cube.049 | cube.050 | cube.051 | 
| **Action Active** | cube.027 | cube.037 | cube.038 | 

- Autres : cube.000 (Possède du NLA pour les 3 types) / cube.039 (Aucune donnée d'animation)

---




## 🔧 Référence technique

  [Manuel officiel Blender NLA](https://docs.blender.org/manual/en/latest/editors/nla/index.html)

  [Manuel officiel de l'API Blender](https://docs.blender.org/api/current/bpy.ops.nla.html)

  


## 📘 Sommaire

1. [Démarrage rapide](#-démarrage-rapide) 
2. [Points forts de la version](#-points-forts-de-la-version) 
3. [Aperçu des fonctionnalités](#-aperçu-des-fonctionnalités)      
4. [FAQ](#-faq) 
5. [Autres astuces](#-autres-astuces) 
6. [Référence technique](#-référence-technique)