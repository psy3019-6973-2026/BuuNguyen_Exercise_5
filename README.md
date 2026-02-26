# BuuNguyen_Exercise_5

# Mon nom est Rémi Buu Nguyen. Je suis en 3ieme année de neurosciences cognitives à l'UdeM

<a href="https://github.com/TON_USERNAME">
   <img src="https://avatars.githubusercontent.com/u/180669752?v=4?s=100" width="100px;" alt=""/>
   <br /><sub><b>Remi Buu Nguyen</b></sub>
</a>

### Lien du projet = https://school-brainhack.github.io/project/chen_project_2025/

### Lien de l'article = https://pubmed.ncbi.nlm.nih.gov/33164348/ 

## 1. Présentation du projet initial
titre du projet initial =  Brainbeats: Classifying Music Genre with fMRI Connectivity

### Description du projet
Ce projet s'inspire de l'article de Nakai, T., Koide‑Majima, N., & Nishimoto, S. (2021). Brain and Behavior, 11(1), e01936.

Les humains ont tendance à catégoriser les différents stimuli auditifs en classes distinctes, comme les langues ou même les intonations émotionnelles dans la voix (Wildgruber et al., 2004). Du côté de la musique, Le genre musical constitue aussi une étiquette couramment utilisée pour organiser et reconnaître la musique. En revanche, les mécanismes cérébraux qui soutiennent cette catégorisation demeurent encore mal compris.

Ainsi, en s'insipirant du projet de Nakai et al., le projet initial cherchait à savoir s'il est possible de prédire le genre musical écouté en se basant uniquement sur des patterns de connectivité fonctionnelles en IRMf.

### Description des données
Les données utilisé pour le projet proviennent de la banque de données OpenNeuro ds003720. Cette base de données ouverte contient des données IRMf de 5 participants écoutant des extraits musicaux qui appartiennent à 10 genres différents. Les données ne sont pas prétraités directement dans cette banque de données, mais une version du jeu de données avec des données pré-traité l'est sur Zenodo.

Les genres musicaux:
- blues, classical, country, disco, hiphop, jazz, metal, pop, reggae, rock

Chaque sujet présente:
- 12 runs d'entraînement 
- 6 runs de test. 
Chaque sujet a écouté 540 extraits musicaux de 10 secondes.

La parcellation du cerveau à été effectué avec l'atlas Schaefer 100-ROI cortical atlas, dont 98 régions utilisables après rééchantillonnage.

! NOTE IMPORTANTE !

Seul le sujet sub-005 à été utilisé dans le projet initial. Les autres sujets contenaient des fichiers corrompus ou non-correspondants, ce qui rompait l'alignement entre les extraits musicaux et les données IRMf.

### Description de la Méthode
La tâche des participant impliquait l'écoute de plusieurs extraits musicaux de 10 genres différents tout en ayant leur activité cérébrale mesurée en IRMf. 

L'atlas utilisé à permis de segmenter le cerveau en 98 régions corticales.

Pour chaque extrait, une matrice de corrélation a été obtenue, puis applatie en vecteur de 4950 dimensions pour l'analyse. Ces vecteurs ont serviss d'entrées pour les classificateurs d'apprentissage automatique.

3 types de classificateurs ont étés testés:
- 1 Multiclass Random Forest pour les 10 genres
- 2 binary classification (SVM, KNN) pour différencier Pop et Metal

### Résultats 
![image tableau resultats](images/tableau_resultats_initiaux.jfif)

La précision du classificateur multiclasse était faible (environ 13%), mais meilleur que la chance avec 10 classes possibles (10%). Du côté des classificateur binaires, le modèle SVM a atteint une précision de 68%, tandis que le KNN a tout simplement échoué. 

![image resultats 2](images/confusion_matrix.jfif)

Le genre musical le mieux classé était le le reggae. 

## 2.  Pourquoi ce projet ?
Tout d'abord, j'ai choisi ce projet puisqu'il me permet de combiner deux sujets qui m'intéressent, soit la musique et l'apprentissage automatique. Étant un pianiste, j'ai longtemps été intéressé à faire un projet où je pourrais mettre en oeuvre mes connaissances acquises pendant mon bacc pour explorer les liens entre la musique et le fonctionnement du cerveau.

Ensuite, bien que j'aie déjà de l'expérience en programmation, je suis débutant spécifiquement en traitement de données d’IRM fonctionnelle et en apprentissage automatique appliqué à la neuroimagerie. Ce projet me permet donc de me familiariser avec des concepts essentiels, tels que l'extraction de séries temporelles cérébrales, la construction de matrices de corrélation ROI-to-ROI et l'entraînement de classificateurs, tout en développant mes compétences en analyse computationnelle de données cérébrales. D'ailleurs, mon projet Honor utilise une tâche experimental en IRMf, donc ce projet pourra certainement m'être utile pour compléter ma thèse.

Finalement, le fait que les données pré-traitées soient disponibles m'a également encouragé à sélectionner ce projet. En revanche, le projet initial semble présenter assez d'opportunité d'amélioration et/ou d'apprentissage

## 3. Description des tâches

Voici les 3 tâches que je compte accomplir.

### TÂCHE 1 : Reproduction du notebook brainbeats_analysis_pca_confmat.ipynb (tâche partagée avec Diyaa)

Ma première sera partagée avec Diyaa. Nous voulons reproduire le notebook brainbeats_analysis_pca_confmat.ipynb. 
Les détails de la division des sous-tâches vont être divisées reste à être confirmé, mais en voici certaines que j'aimerais accomplir:

Au niveau de la lisibilité:
- ajouter des commentaires explicatifs et réorganiser les notebook pour améliorer la lisibilité

Au niveau des figures:
- Améliorer la figure de matrice de confusion pour améliorer la lisibilité et l'interprétation (changer les couleurs, mettre les chiffres importants en gras, rendre les axes plus lisibles)
- Ajouter un diagramme à bande pour illustrer le niveau de précision pour chaque genre avec une Baseline

Sous-tâches supplémentaires : 
- Ajouter un graphique de type T-SNE pour visualiser comment les différents genres se regroupent
- Ajouts de graphiques diagnostiques (À DÉTERMINER)

Pourquoi cette tâche?
L'intérêt principal de cette tâche est de me permettre de développer mes connaissances sur le pipeline de traitement des données d’IRM et d’apprentissage automatique ainsi que d’améliorer mes compétences en visualisation de données. 
Cette tâche est également très pertinente, car elle me permettra d'apprendre à collaborer avec une collègue à travers Github.

### TÂCHE 2 :  Production et adaptation du notebook brainbeats_binary_classifier.ipynb
Ma deuxième tâche serait de produire le notebook du classificateur binaire brainbeats_binary_classifier en utilisant les données pré-traités trouvées sur Zenodo.

Voici les sous-tâches nécessaires:
- Création et exécution complète d'un notebook original
- Création d'un environnement virtuel
- Adaptation du notebook au jeu de données pré-traités
- Ajout de commentaires explicatifs

Sous-tâche si j'ai les capacité computationnelles:
- Entrainer et tester le classificateur binaire sur plus d'un participant

Sous-tâches supplémetaires:
- Créer un script de validation de la structure du jeu de données
- Trouver et tester un autre type de classificateur binaire
- Création de visualisation pour comparer les différents classificateurs utilisés

Pourquoi cette tâche?
J'ai très peu de connaissances en classification automatique, donc je pense que cette tâche constitue un bon défi. Présentement, seule la dernière cellule du notebook est disponible en ligne. Cela me permettrait donc de développer mon propre pipeline d'analyse. De plus, l'ajout potentiel d'un deuxième participant pourrait certainement améliorer la capacité de classification et donner de meilleurs résultats.
Finalement, 


### TÂCHE 3 : Créer un notebook pédagogique exhaustif expliquant les concepts de classification automatique
Ma troisième tâche serait de créer un notebook pédagogique sur le thème de la classification automatique. Le notebook serait destiné à un public débutant, comme moi, dans le but de rendre ce genre de projet plus accessible.

Voici les sous-tâches nécessaires:
- Recherches exhaustives sur la classification (explication des bases mathématiques de la classification automatique, types de classification, explication du fonctionnement, exemples d'application, explications des métriques d'évaluations des algorithmes de classifications, etc.)
- Création d'un nouveau notebook structuré de manière progressive ( théorie, exemples simples, application concrète)
- implémentation d'un classificateur simple
- Visualisation graphique de concepts clés

Sous-tâches supplémentaires:
- Ajouts d'exerices pratiques pour favoriser l'apprentissage automatique
- Création d'un jeu de donnée simple pour permettre aux lecteurs de faire leur propre tests.

Pourquoi cette tâche?
Cette tâche me permettrait de concrétiser mes apprentissages faits au long du projet. Le fait d'expliquer la matière à un public débutant m'obligerait à bien comprendre les fondements théoriques, les étapes méthodologiques et les choix techniques derrière les algorithmes de classification.

De plus, la création de ce notebook constituerait une ressource utile et réutilisable, autant pour moi que pour d'autres étudiants. 

## RÉFÉRENCES
Nakai, T., Koide‐Majima, N., & Nishimoto, S. (2020). Correspondence of categorical and feature‐based representations of music in the human brain. Brain and Behavior, 11(1), e01936. https://doi.org/10.1002/brb3.1936

Wildgruber, D., Riecker, A., Hertrich, I., Erb, M., Grodd, W., Ethofer, T., & Ackermann, H. (2004). Identification of emotional intonation evaluated by fMRI. NeuroImage, 24(4), 1233–1241. https://doi.org/10.1016/j.neuroimage.2004.10.034






