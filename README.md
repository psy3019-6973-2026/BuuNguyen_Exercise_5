# BuuNguyen_Exercise_5

# Mon nom est Rémi Buu Nguyen. Je suis en 3ieme année de neurosciences cognitives à l'UdeM

<a href="https://github.com/TON_USERNAME">
   <img src="https://avatars.githubusercontent.com/u/180669752?v=4?s=100" width="100px;" alt=""/>
   <br /><sub><b>Remi Buu Nguyen</b></sub>
</a>

### Lien du projet = https://school-brainhack.github.io/project/chen_project_2025/

## 1. Présentation du projet initial
titre du projet initial =  Brainbeats: Classifying Music Genre with fMRI Connectivity

### Description du projet
Ce projet s'inspire de l'article de Nakai, T., Koide‑Majima, N., & Nishimoto, S. (2021). Brain and Behavior, 11(1), e01936.

Les humains ont tendance à catégoriser les stimuli auditifs en classes distinctes, comme les langues, les instruments ou les genres musicaux. Le genre musical constitue ainsi une étiquette couramment utilisée pour organiser et reconnaître la musique, mais les mécanismes cérébraux qui soutiennent cette catégorisation demeurent encore partiellement compris.

Ainsi, en s'insipirant du projet de Nakai et al., on cherche à savoir s'il est possible de prédire le genre musical écouté en se basant uniquement sur des patterns de connectivité fonctionnelles en IRMf.

### Description des données
Les données utilisé pour le projet proviennent de la banque de données OpenNeuro ds003720. Cette base de données ouverte contient des données IRMf de 5 participants écoutant des extraits musicaux appartenant à 10 genres différents. Les données ne sont pas prétraités directement dans cette banque de données, mais le sont sur Zenodo.

Chaque sujet présente:
- 12 runs d'entraînement 
- 6 runs de test. 
Chaque run contient environ 50 extraits musicaux de 10 secondes. 

La parcellation du cerveau à été effectué avec l'atlas Schaefer 100-ROI cortical atlas (98 usable ROIs after resampling) 

! NOTE IMPORTANTE !

Seul le sujet sub-005 à été utilisé dans le cadre de ce projet. Les autres sujets contenaient des fichiers corrompus ou non-correspondants, ce qui rompait l'alignement entre les extraits musicaux et les données IRMf

### Description de la Méthode
La tâche des participant impliquait l'écoute de plusieurs extraits musicaux de 10 genres différents tout en ayant leur activité cérébrale mesurée en IRMf. 

Pour chaque extrait, une matrice de corrélation a été obtenue, puis applatie en vecteur de 4950 dimensions pour l'analyse. Ces vecteurs servaient d'entrées pour les classificateurs d'apprentissage automatique.

3 types de classificateurs ont étés testés:
- 1 Multiclass Random Forest pour les 10 genres
- 2 binary classification (SVM, KNN) pour différencier Pop et Metal

### Résultats 
![image tableau resultats](images/tableau_resultats_initiaux.jfif)

![image resultats 2](images/confusion_matrix.jfif)

INTERPRETATION DES RÉSULTATS

## 2.  Pourquoi ce projet ?
Tout d'abord, j'ai choisi ce projet puisqu'il me permet de combiner deux sujets qui m'intéressent, soit la musique et l'apprentissage automatique. Étant un pianiste, j'ai longtemps été intéressé à faire un projet où je pourrais mettre en oeuvre mes connaissances acquises pendant mon bacc pour explorer les liens entre la musique et le fonctionnement du cerveau.

Ensuite, bien que j'aie déjà de l'expérience en programmation, je suis débutant spécifiquement en traitement de données d’IRM fonctionnelle et en apprentissage automatique appliqué à la neuroimagerie. Ce projet me permet donc de me familiariser avec des concepts essentiels, tels que l'extraction de séries temporelles cérébrales, la construction de matrices de corrélation ROI-to-ROI et l'entraînement de classificateurs, tout en développant mes compétences en analyse computationnelle de données cérébrales. D'ailleurs, mon projet Honor utilise une tâche experimental en IRMf, donc ce projet pourra certainement m'être utile pour compléter ma thèse.

Finalement, le fait que les données pré-traitées soient disponibles m'a également encouragé à sélectionner ce projet. En revanche, le projet initial semble présenter assez d'opportunité d'amélioration et/ou d'apprentissage

## 3. Description des tâches

Voici les 3 tâches que je compte accomplir

### TÂCHE 1 : Reproduction complète du notebook brainbeats_analysis_pca_confmat.ipynb (tâche partagée avec Diyaa)

Les détails de comment les sous-tâches vont être divisées reste à être confirmé, mais voici certaines des sous-tâches que j'aimerais accomplir:

au niveau de la lisibilité:
- ajouter des commentaires explicatifs et réorganiser les notebook pour améliorer la visibilité

au niveau des figures:
- Améliorer la figure de matrice de confusion pour améliorer la lisibilité (changer les couleurs, mettre les chiffres importants en gras, rendre les axes plus lisibles)
- Ajouter un diagramme à bande pour illustrer le niveau de précision pour chaque genre avec une Baseline (AJOUTER UN EXEMPLE)
- si jamais cela ne me prends pas 6-15h = ajouter un graphique de type T-SNE pour voir comment les genres se regroupent (HUH??)

pourquoi cette tâche?
L'intérêt principal de cette tâche est d'apprendre à collaborer avec une collègue à travers Github. Cette tâche est également pertinente car elle me permet de mieux comprendre le pipeline de traitement des données d’IRM et d’apprentissage automatique, d’améliorer mes compétences en visualisation

### TÂCHE 2 : Reproduction complète du notebook brainbeats_binary_classifier.ipynb (tâche partagée avec Diyaa)

### TÂCHE 3 : Créer un notebook pédagogique exhaustif expliquant les concepts de classification automatique









