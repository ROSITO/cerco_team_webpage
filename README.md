# cerco_team_webpage
page web du cerco


# Liens
## ENG
SV3M: https://cerco.cnrs.fr/en/sv3m-2/
PresAge: https://cerco.cnrs.fr/en/presage-2/
NeuroAI: https://cerco.cnrs.fr/en/neuroai-2/
DYNAMO: https://cerco.cnrs.fr/en/dynamo-2/
SLAM: https://cerco.cnrs.fr/en/slam-2/


# Problèmes résolus

## 1. Problèmes de mise en page SV3M
- **Problème initial** : Les deux photos des responsables n'avaient pas la même taille
- **Solution** : Utilisation de `height:200px` avec `min-height` et `max-height` pour garantir une taille uniforme
- **Problème d'espacement** : Photos trop proches l'une de l'autre
- **Solution** : Augmentation du `gap` de `12px` à `24px` dans `.leaders`
- **Problème d'égalité de largeur** : Les deux colonnes des responsables n'avaient pas la même largeur
- **Solution** : Passage de `display:grid` à `display:flex` avec `flex:1 1 0` et `min-width:0` pour garantir des colonnes de largeur égale

## 2. Création des versions anglaises
- **Tâche** : Création des versions anglaises de toutes les pages d'équipe (PREsage_EN, DYNAMO_EN, neuroAI_EN, SLAM_EN, SV3M_EN)
- **Source** : Traduction du contenu à partir des fichiers `.doc` et `.docx` dans le dossier `annexe`
- **Préservation** : Tous les liens (images, publications, financeurs) ont été conservés, seuls les contenus textuels ont été traduits

## 3. Problème de rendu WordPress (pages anglaises)
- **Problème** : Les pages anglaises s'affichaient en une seule colonne dans WordPress au lieu de deux colonnes
- **Cause** : WordPress transforme les sauts de ligne en balises `<p>`, ce qui casse la structure HTML. WordPress transforme également la balise `<main>` en `<p><main></p>`
- **Solution** :
  - Remplacement de `<main class="col-right">` par `<div class="col-right">`
  - Compression du HTML sur une seule ligne (suppression de tous les sauts de ligne entre les balises importantes)
  - Suppression des commentaires HTML qui peuvent être transformés en balises `<p>`
  - Application de cette solution à toutes les pages anglaises

## 4. Création de la page S!C
- **Tâche** : Création de la page pour le Service Informatique et Communication
- **Structure** : Même modèle que les autres équipes, mais sans les sections "Projects" et "Funding"
- **Versions** : Création des versions française (SIC.html) et anglaise (SIC_EN.html)
- **Photo** : Ajout de la photo de la responsable (Carmen OLMOS ARAYE)

## 5. Problème de largeur du texte (S!C)
- **Problème** : Le texte dans la colonne de droite semblait coincé dans une colonne étroite
- **Cause** : WordPress applique des styles qui limitent la largeur du contenu (via `.entry-content` et `.is-layout-constrained`)
- **Solution** : Ajout de règles CSS avec `!important` pour forcer la largeur complète :
  - `width:100%!important` et `max-width:none!important` sur `.col-right`
  - Règles spécifiques pour contrer les styles WordPress sur `.entry-content` et `.is-layout-constrained`

## 6. Problème de taille de la photo (S!C)
- **Problème** : La photo de la responsable prenait trop de place (largeur complète de la colonne)
- **Solution** :
  - Limitation de la largeur à 150px avec `max-width:150px!important`
  - Ajout de styles inline directement sur l'image pour garantir l'application
  - Centrage de la photo avec `margin:0 auto!important`
  - Modification du CSS pour utiliser `width:150px` au lieu de `width:100%`

## Notes techniques
- Toutes les pages anglaises utilisent maintenant un format ultra-compact (une seule ligne) pour éviter les transformations WordPress
- Les pages françaises fonctionnent avec le format normal (sauts de ligne), sauf SIC.html qui a nécessité la compression pour WordPress
- Utilisation de `!important` dans les CSS pour forcer l'application des styles malgré les styles WordPress
