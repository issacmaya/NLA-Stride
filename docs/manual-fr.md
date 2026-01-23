<a href="images/NLA-Stride_LOGO2.png"><img src="images/NLA-Stride_LOGO2.png" width="250"></a>  

# Manuel d'utilisation (Français)

> Ce manuel présente les fonctions et astuces du module complémentaire NLA-Stride pour Blender, ainsi que des réponses à certains problèmes connus courants.

---

## 📘 Sommaire

1. [Démarrage rapide](#-démarrage-rapide)  
2. [Aperçu des fonctionnalités](#-aperçu-des-fonctionnalités)      
3. [Foire aux questions](#-foire-aux-questions) 
4. [Divers](#-divers) 
5. [Référence technique](#-référence-technique)

---

## 🚀 Démarrage rapide

### 1. Installation de l'addon

1. Suivez les étapes d'installation officielles de Blender ( **[Guide d'installation général](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html)** )

2. Après l'installation, vous trouverez l'outil **NLA Stride Tool** dans la vue 3D de Blender, sous l'onglet **Barre latérale → Animation**. 
<br>![alt text](images/img_1001.png)



---

### 2. Sélectionner des objets avec animation  
<a href="images/img_1002.png">
  <img src="images/img_1002.png" width="650">
</a>  

Sélectionnez un ou plusieurs objets contenant des données d'animation. S'ils contiennent des actions standard au lieu de bandes NLA, veuillez vous référer à la section « Pousser par lot vers la NLA » plus loin.  

---

### 3. Ajouter à la liste  
![alt text](images/img_1003.png)  

⚠️ Remarque : L'addon fonctionne sur la base de la liste, quelle que soit la sélection actuelle dans la vue 3D.  

---

### 4. Alignement NLA / Opérations de décalage  
<a href="images/img_1004.png"><img src="images/img_1004.png" width="650"></a>  
<a href="images/img_1005.png"><img src="images/img_1005.png" width="650"></a>  
<a href="images/img_1006.png"><img src="images/img_1006.png" width="650"></a>  

Ci-dessus se trouvent des démonstrations des fonctions d'alignement et de décalage NLA.  

---

### 5. Profitez de la magie de l'animation  
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

Remerciements particuliers à la marque taïwanaise [SANSUI](https://www.sansuitw.com/?gad_source=1&gad_campaignid=23085773952&gbraid=0AAAAAoXC59ENhboAZDO-y0zK4yQpidtXM&gclid=CjwKCAiAybfLBhAjEiwAI0mBBscjnZOEYBBY127EypNMfnL1h_Vqm_HACczeJBOqMK-euDJFPb1iAxoC7rkQAvD_BwE) pour avoir fourni les modèles d'exemple.  

---

## 🧰 Aperçu des fonctionnalités

#### 1. Source de données 
![alt text](images/img_2001.png)  

- A : Initialiser et ajouter la sélection  
  Vide d'abord la liste, puis ajoute les objets actuellement sélectionnés dans la scène.  
<br>

- B : Vider la liste  
  Supprime toutes les données de la liste.  
<br>

- C : Source d'animation  
  Prend actuellement en charge trois types : Animation d'objet / Animation de clés de forme / Animation de matériau.  
<br>

- D : Ajouter / Supprimer des éléments de la liste  
  L'ajout **ne vide pas** la liste précédente ; les objets sont ajoutés à la fin selon l' **ordre de sélection**. Si un objet déjà présent dans la liste est sélectionné, il sera déplacé à la fin. La logique d'ajout est différente de celle de A. L'outil de suppression est également différent de 1-J.  
<br>

- E : Opérations de liste (menu déroulant)  
  Voir « 1-1 Opérations de liste » pour plus de détails.  
<br>

- F : Monter / Descendre l'élément  
  Ajuste l'ordre manuellement. Une fois ajusté, ce résultat est défini comme l' **« Ordre d'origine »**.  
<br>

- G : Pousser vers NLA (menu déroulant)  
  Convertit l'action actuelle en bandes NLA, uniquement pour les objets de la liste.  
<br>

- PS. [3. Signification des icônes de la liste](#3-signification-des-icônes-de-la-liste)  

#### 1-1. Opérations de liste
![alt text](images/img_2002.png)  

- H : Initialiser et ajouter la sélection  
  Vide d'abord la liste, puis ajoute les objets actuellement sélectionnés dans la scène.  
<br>

- I : Quatre options de tri  
  La plus importante est **Restaurer l'ordre d'origine**, car cet addon enregistre cette séquence. Les trois autres sont des tris automatiques.  
<br>

- J : Retirer la sélection de la scène  
  Supprime les objets de la liste en fonction de la sélection actuelle dans la vue 3D. C'est différent de l'outil de suppression 1-D.  

#### 2. Positionnement des données
![alt text](images/img_2003.png)  

- K : Trois modes de bande  
  - Bande unique : Cible une seule bande spécifique.  
  - Piste unique : Traite toutes les bandes d'une même piste comme un seul groupe (les positions relatives ne changent pas).  
  - Toutes les pistes : Revient à modifier toutes les pistes de l'objet simultanément (les positions relatives ne changent pas).  
<br>

- L : Trois points de positionnement  
  - Quel slot : (Mode matériau uniquement) Calculé de **haut en bas** dans l'interface.  
  - Quelle piste : Calculé de **bas en haut** dans l'éditeur NLA.  
  - Quelle bande : Calculé de **gauche à droite** dans l'éditeur NLA.  
<br>

  **!! Remarque : Si la cible n'est pas positionnée correctement, NLA Stride ne pourra pas effectuer le décalage.** #### 3. Outils d'alignement NLA (Valeurs initiales)
![alt text](images/img_2004.png)  

- M : Cinq cibles d'alignement  
  - Sur l'image de début max : S'aligne sur le point de **début** de la bande qui commence le plus **tard** dans la liste.  
  - Sur l'image de début min : S'aligne sur le point de **début** de la bande qui commence le plus **tôt** (usage courant).  
  - Sur l'image de fin max : S'aligne sur le point de **fin** de la bande qui se termine le plus **tard** (usage courant).  
  - Sur l'image de fin min : S'aligne sur le point de **fin** de la bande qui se termine le plus **tôt**.  
  - Sur le temps actuel : S'aligne sur la position actuelle de la tête de lecture (le plus fréquent).  
<br>

- N : Trois modes d'alignement  
  - Aligner au début : Le côté gauche de la bande s'aligne sur la cible. Généralement utilisé pour l'alignement de **Début**.  
  - Aligner au milieu : Le centre de la bande s'aligne sur la cible.  
  - Aligner à la fin : Le côté droit de la bande s'aligne sur la cible. Généralement utilisé pour l'alignement de **Fin**.  
<br>

- O : Réinitialiser l'échelle  
  Restaure la valeur d'échelle de toutes les bandes NLA de la liste à 1.0.  


#### 4. Mode simple
![alt text](images/img_2005.png)  

- P : Mode d'atténuation [(Description détaillée)](#2-description-du-décalage)  
  - Quatre formules de calcul : 1. Linéaire / 2. Entrée lente / 3. Sortie lente / 4. Entrée et sortie lentes.  
<br>

- Q : Valeur de décalage (Unité : **images**)  
  - Ce n'est pas l'espacement entre les bandes individuelles, mais la différence totale entre le premier et le dernier objet de la liste (valeurs négatives autorisées).  
<br>

- R : Échelle  
  - Pas une échelle incrémentielle, mais la différence d'échelle entre le premier et le dernier objet de la liste (0 ~ 1).  
<br>

- S : Exécuter le Stride NLA simple (cliquer de manière répétée accumule le calcul).  
<br>

#### 5. Mode professionnel
![alt text](images/img_2006.png)  
  **>> Le cœur de cet addon. Grâce à des réglages simples, il ajuste automatiquement le décalage et l'échelle des bandes <<** - T : Mode d'atténuation [(Description détaillée)](#2-description-du-décalage)  
  - Quatre formules de calcul : 1. Linéaire / 2. Entrée lente / 3. Sortie lente / 4. Entrée et sortie lentes.  
<br>

- U : Régler l'image de début  
  - Définit le temps de **Début** pour toute la séquence d'animation de tous les objets de la liste.  
<br>

- V : Rapport de décalage (Tête)  
  - Multiplié par le mode d'atténuation (T) pour calculer la valeur de décalage, utilisée pour positionner automatiquement tous les points de début des bandes.  
<br>

- W : Mode d'atténuation [(Description détaillée)](#2-description-du-décalage)  
  - Quatre formules de calcul : 1. Linéaire / 2. Entrée lente / 3. Sortie lente / 4. Entrée et sortie lentes.  
<br>

- X : Régler l'image de fin  
  - Définit le temps de **Fin** pour toute la séquence d'animation de tous les objets de la liste.  
<br>

- Y : Rapport de décalage (Queue)  
  - Le rapport de décalage pour les points de fin des bandes.  
<br>

- Z : Exécuter le Stride NLA professionnel (cliquer de manière répétée **n'accumule pas** le calcul).  
<br>


---

## ❓ Foire aux questions


#### 1. ⚠️ Attention aux « Données instanciées (Instanced Data) »

Cet addon traite principalement le décalage et l'alignement des bandes NLA elles-mêmes ; il **ne gère pas** automatiquement les relations de « données instanciées » au sein de Blender.  

#### Que sont les données instanciées ?

Lorsque **plusieurs objets partagent les mêmes données**, ces blocs de données sont « instanciés ».  

- Par exemple :  
  - Deux objets partageant le même matériau.  
  - Le partage de la même action (Action), du même maillage (Mesh) ou d'autres blocs de données.  

Dans l'éditeur NLA, ils peuvent sembler être deux bandes indépendantes, mais en réalité, ils **pointent vers le même bloc de données sous-jacent**.
Cela signifie qu'en utilisant **NLA Stride pour le décalage**, l'addon semble déplacer différentes bandes, mais en réalité, il modifie la même donnée, de sorte que l' **effet de décalage attendu ne se produit pas**.


#### ✅ Solution (Suivez les étapes de l'image)

> 💡 **Idée centrale : Rendre les données indépendantes avant d'effectuer le décalage.** Étapes (comme indiqué sur l'image) :  

1. Sélectionnez les objets à traiter dans la vue 3D.  
2. Allez dans **Objet (Object) → Relations (Relations)**.  
3. Cliquez sur **Rendre utilisateur unique (Make Single User)**.  
4. Sélectionnez les types de données qui doivent devenir indépendants (ex : Animation d'objet).  
5. Une fois les données indépendantes, utilisez **NLA Stride** pour effectuer le décalage.  



![alt text](images/img_3001.png)  

> Une fois les données indépendantes, chaque objet possède ses propres données NLA exclusives.
> NLA Stride peut alors **aider à décaler les bandes NLA de manière normale et prévisible**.  

---


#### 2. ⚠️ Création de NLA par lot

La cible de cet addon sont les bandes NLA. Si les données d'animation n'ont pas encore été « poussées » (push down) pour devenir des bandes NLA, elles ne seront pas affectées.  

#### ✅ Solution : Outil Pousser vers NLA

L'addon propose un outil de conversion par lot (indiqué par les flèches vertes ci-dessous). Notez qu'il cible les objets **de la liste**, et non la sélection actuelle dans la vue 3D.  

![alt text](images/img_3002.png)  

---



## 📖 Divers


#### 1. Conseils de stratégie pour l'alignement et le décalage

- Vous pouvez d'abord appuyer sur **Alt A** dans la vue 3D pour tout désélectionner, puis utiliser la fonction **Sélectionner les objets de la liste** pour confirmer exactement qui se trouve dans votre liste.  
<br>

- L' **Ordre** est crucial, car il affecte directement l'état de l'animation après le décalage. Si possible, utilisez des règles de nommage pour décider de l'ordre. Si vous avez énormément d'objets, traitez-les par lots.  
<br>

- Lorsque tout devient confus, utilisez les outils d'alignement pour tout unifier d'abord.  
<br>

- Étant donné que le décalage d'animation devient très simple, concentrez votre énergie sur la création d'un **mouvement parfait**.  
<br>

- Si la conception de votre mouvement inclut la **Position (Location)**, soyez prudent lors de la duplication ; lors de la lecture de l'animation, elle peut revenir à la même position car l'information de position est écrite dans la NLA. Dans ce cas, vous pouvez utiliser **Ctrl A** pour appliquer les transformations et écrire la nouvelle position dans les données de **Transformations delta**.  
<br>![alt text](images/img_4001.png)  

---

#### 2. Description du décalage
- Mode de superposition linéaire :  
  - Mode simple :   
  <a href="images/img_4002.png"><img src="images/img_4002.png" width="650"></a>  
  Le mode simple calcule avec le mode de superposition basé sur l'état d'origine (à l'extrême gauche de l'image). Comme illustré, avec un décalage réglé sur 100 et une échelle sur 1.5, le point de début et la longueur (point de fin) de la dernière bande seront toujours identiques ; mais on peut voir qu'en raison des différents modes d'atténuation, les points de début des autres bandes diffèrent, créant différentes sensations de décalage.  

    ---
  - Mode professionnel :    
  <a href="images/img_4003.png"><img src="images/img_4003.png" width="650"></a>  
  La seule différence avec le mode simple est que le mode professionnel permet de régler le contrôle de la tête (Head) et de la queue (Tail), offrant ainsi deux réglages de mode d'atténuation distincts.  
  
    ---
  - **Remarque** :   
  <a href="images/img_4004.png"><img src="images/img_4004.png" width="650"></a>  
  Attention : si les deux modes d'atténuation de tête et de queue sont **différents**, il faut surveiller si les bandes d'animation rencontrent des problèmes (trop courtes ou disparues).  

---

#### 3. Signification des icônes de la liste

![alt text](images/img_3003.gif)  

Icône A : Mode de données  
Icône B : Action représente des données d'animation standard (non NLA).  
Icône C : Données NLA existantes.  

- La signification des icônes B et C varie en fonction du mode de données de la colonne A :  
  - ✔ : Contient les données **correctes** correspondant au mode de la colonne A.  
  - ・ : Contient des données, mais **pas** du type configuré dans la colonne A.  
  - ✕ : Aucune donnée trouvée.  

Données dans la vue :  
| Élément | Animation d'objet | Animation de matériau | Animation de clés de forme |
|------|------|------|--------|
| **Bande NLA** | cube.049 | cube.050 | cube.051 | 
| **Action active** | cube.027 | cube.037 | cube.038 |  

- Divers : cube.000 (possède les trois types de NLA) / cube.039 (aucune donnée d'animation).  

---

## 🔧 Référence technique

  [Manuel officiel Blender NLA](https://docs.blender.org/manual/en/latest/editors/nla/index.html)  

  [Manuel officiel de l'API Blender](https://docs.blender.org/api/current/bpy.ops.nla.html)  

  


## 📘 Sommaire

1. [Démarrage rapide](#-démarrage-rapide)  
2. [Aperçu des fonctionnalités](#-aperçu-des-fonctionnalités)      
3. [Foire aux questions](#-foire-aux-questions) 
4. [Divers](#-divers) 
5. [Référence technique](#-référence-technique)
