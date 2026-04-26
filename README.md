# BuuNguyen_Exercise_5

# Mon nom est Rémi Buu Nguyen. Je suis en 3ieme année de neurosciences cognitives à l'UdeM

<a href="https://github.com/TON_USERNAME">
   <img src="https://avatars.githubusercontent.com/u/180669752?v=4?s=100" width="100px;" alt=""/>
   <br /><sub><b>Remi Buu Nguyen</b></sub>
</a>  


**Repo du projet original :** https://github.com/AlexPeng517/BHS2023_Project_SAM_MRI *(voir lien BrainHack)*

**URL BrainHack :** https://school-brainhack.github.io/project/chen_project_2025/

**Article de référence :** https://pubmed.ncbi.nlm.nih.gov/33164348/

---

## 1. Présentation du projet initial
titre du projet initial =  Brainbeats: Classifying Music Genre with fMRI Connectivity

### 1.1 Description du projet
Ce projet s'inspire de l'article de Nakai, T., Koide‑Majima, N., & Nishimoto, S. (2021). Brain and Behavior, 11(1), e01936.

Les humains ont tendance à catégoriser les différents stimuli auditifs en classes distinctes, comme les langues ou même les intonations émotionnelles dans la voix (Wildgruber et al., 2004). Du côté de la musique, Le genre musical constitue aussi une étiquette couramment utilisée pour organiser et reconnaître la musique. En revanche, les mécanismes cérébraux qui soutiennent cette catégorisation demeurent encore mal compris.

Ainsi, en s'insipirant du projet de Nakai et al., le projet initial cherchait à savoir s'il est possible de prédire le genre musical écouté en se basant uniquement sur des patterns de connectivité fonctionnelles en IRMf.

### 1.2 Description des données
Les données utilisé pour le projet proviennent de la banque de données OpenNeuro ds003720. Cette base de données ouverte contient des données IRMf de 5 participants écoutant des extraits musicaux qui appartiennent à 10 genres différents. Les données ne sont pas prétraités directement dans cette banque de données, mais une version du jeu de données avec des données pré-traité l'est sur Zenodo.

Les 10 genres musicaux:
- blues, classical, country, disco, hiphop, jazz, metal, pop, reggae, rock

Chaque sujet présente:
- 12 runs d'entraînement 
- 6 runs de test. 
Chaque sujet a écouté 540 extraits musicaux de 10 secondes.

La parcellation du cerveau à été effectué avec l'atlas Schaefer 100-ROI cortical atlas, dont 98 régions utilisables après rééchantillonnage.

!NOTE IMPORTANTE!

Seul le sujet sub-005 à été utilisé dans le projet initial. Les autres sujets contenaient des fichiers corrompus ou non-correspondants, ce qui rompait l'alignement entre les extraits musicaux et les données IRMf.

### 1.3 Description de la Méthode
La tâche des participant impliquait l'écoute de plusieurs extraits musicaux de 10 genres différents tout en ayant leur activité cérébrale mesurée en IRMf. 

L'atlas utilisé à permis de segmenter le cerveau en 98 régions corticales.

Pour chaque extrait, une matrice de corrélation a été obtenue, puis applatie en vecteur de 4950 dimensions pour l'analyse. Ces vecteurs ont serviss d'entrées pour les classificateurs d'apprentissage automatique.

3 types de classificateurs ont étés testés:
- 1 Multiclass Random Forest pour les 10 genres
- 2 binary classification (SVM, KNN) pour différencier Pop et Metal

### 1.4 Résultats 
![image tableau resultats](images/tableau_resultats_initiaux.jfif)

La précision du classificateur multiclasse était faible (environ 13%), mais meilleur que la chance avec 10 classes possibles (10%). Du côté des classificateur binaires, le modèle SVM a atteint une précision de 68%, tandis que le KNN a tout simplement échoué. 

![image resultats 2](images/confusion_matrix.jfif)

Le genre musical le mieux classé était le le reggae. 

## 2.  Pourquoi ce projet ?
Tout d'abord, j'ai choisi ce projet puisqu'il me permet de combiner deux sujets qui m'intéressent, soit la musique et l'apprentissage automatique. Étant un pianiste, j'ai longtemps été intéressé à faire un projet où je pourrais mettre en oeuvre mes connaissances acquises pendant mon bacc pour explorer les liens entre la musique et le fonctionnement du cerveau.

Ensuite, bien que j'aie déjà de l'expérience en programmation, je suis débutant spécifiquement en traitement de données d’IRM fonctionnelle et en apprentissage automatique appliqué à la neuroimagerie. Ce projet me permet donc de me familiariser avec des concepts essentiels, tels que l'extraction de séries temporelles cérébrales, la construction de matrices de corrélation ROI-to-ROI et l'entraînement de classificateurs, tout en développant mes compétences en analyse computationnelle de données cérébrales. D'ailleurs, mon projet Honor utilise une tâche experimental en IRMf, donc ce projet pourra certainement m'être utile pour compléter ma thèse.

Finalement, le fait que les données pré-traitées soient disponibles m'a également encouragé à sélectionner ce projet. En revanche, le projet initial semble présenter assez d'opportunité d'amélioration et/ou d'apprentissage

## 3. Initialisation du projet

### 3.1 Structure du dépot

```
BuuNguyen_Exercise_5/
├── task_1.ipynb                  # Tâche 1 : XXX
├── task_2.ipynb                  # Tâche 2 : XXX
├── task_3/
│   ├── 01_theorie.ipynb          # Tâche 3 — Partie 1 : Théorie de la classification automatique
│   └── 02_classificateurs.ipynb  # Tâche 3 — Partie 2 : Algorithmes KNN, SVM et Random Forest
├── images/
│   ├── tableau_resultats_initiaux.jfif
│   └── confusion_matrix.jfif
├── environment.yml
├── LICENSE
└── README.md
```

### 3.2 Reproductibilité
Pour reproduire l'ensemble des notebook, il faudra initialiser l'environnement virtuel. Le téléchargement de données se fera directement à partir des notebooks.

### Initialiser l'environnement virtuel

```bash
conda env create -f environment.yml
conda activate <nom_de_l_environnement>
```

### Les données

Les données sont téléchargées automatiquement depuis Zenodo au début des notebooks de la tâche 1 et 2. Aucun téléchargement manuel n'est nécessaire. Les notebooks de la tâche 3 n'utilisent aucune donnée externe.

### Exécution des notebook

Les notebooks peuvent être exécutés dans l'ordre suivant :

1. `task_1.ipynb` — Pipeline multiclasse et visualisations
2. `task_2.ipynb` — Classificateur binaire
3. `task_3/01_theorie.ipynb` — Théorie (aucune donnée externe requise)
4. `task_3/02_classificateurs.ipynb` — Algorithmes (aucune donnée externe requise)

En revanche, les notebook task_1.ipynb et task_2.ipynb permettent tout les deux de télecharger les données. Ainsi, l'ordre proposé n'est pas obligatoire pour que les notebooks fonctionnent. Ils peuvent être exécutés indépendamment dans n'importe quel ordre.

## 4. Description des tâches

Pour voir les tâches telles que présentées à la mi-session, voir [Presentation_initiale.md](Presentation_initiale.md).  
Pour voir les plus grandes difficultés rencontré pour les 3 tâches, voir XXXX.  
Pour voir un journal de bord incomplet et brouillon, voir XXXX.   

### 1. Tâche 1 : Reproduction et amélioration du notebook `brainbeats_analysis_pca_confmat.ipynb`

**Objectif principal :** Reproduire le notebook d'analyse multiclasse du projet original et l'améliorer au niveau de la lisibilité et des figures.

**Ce qui a été réalisé :**  

En premier lieu, le notebook original n'était pas structuré de façon claire. Je l'ai réorganisé en 4 sections distinctes avec des commentaires explicatifs à chaque étape : chargement des données, construction des labels, pipeline d'analyse, et visualisation.

Pour le pipeline d'analyse, j'ai implémenté une chaîne complète en trois étapes : standardisation (StandardScaler), réduction de dimensions par PCA à 50 composantes, puis classification par SVM linéaire (LinearSVC). 

Au niveau des visualisations, plusieurs figures ont été produites. Étant donné qu'un des objectifs de la tâche était de m'améliorer dans la production de figures, j'ai décidé de produire plusieurs types de visualisations complémentaires plutôt que de me limiter à celles du projet original.

**Figures produites :**
*Matrice de confusion :* Deux versions ont été produites. La première est la version de base. La deuxième est une version améliorée où chaque case de la diagonale est encadrée en rouge pour faciliter la lecture des bonnes prédictions.

<img src="https://avatars.githubusercontent.com/u/180669752?v=4?s=100" width="50px;" alt=""/>


*Diagramme en barres de l'accuracy par genre :* Montre la précision du modèle pour chacun des 10 genres, avec une ligne rouge pointillée au niveau du chance level (10%). Permet de voir rapidement quels genres sont mieux classés que d'autres.

> 📷 *Insérer ici : diagramme en barres de l'accuracy par genre avec chance level (cellule 20)*

*t-SNE et UMAP :* Deux techniques de réduction de dimension ont été utilisées et comparées côte à côte pour visualiser si les genres forment des groupes distincts dans l'espace des features. Le t-SNE préserve bien la structure locale (les voisins proches restent proches), tandis que l'UMAP préserve aussi une partie de la structure globale et est généralement plus stable et rapide. L'UMAP est appliqué directement sur les 50 composantes PCA déjà extraites par le pipeline, ce qui accélère considérablement le calcul.

> 📷 *Insérer ici : t-SNE avec centroïdes annotés (cellule 19)*

> 📷 *Insérer ici : comparaison côte à côte t-SNE vs UMAP (cellule 21)*

*Scree plot de la PCA :* Montre la variance cumulée expliquée en fonction du nombre de composantes, avec une ligne rouge à 50 composantes pour justifier ce choix dans le pipeline.

> 📷 *Insérer ici : scree plot de la PCA (cellule 24)*



---

## RÉFÉRENCES
Nakai, T., Koide‐Majima, N., & Nishimoto, S. (2020). Correspondence of categorical and feature‐based representations of music in the human brain. Brain and Behavior, 11(1), e01936. https://doi.org/10.1002/brb3.1936

Wildgruber, D., Riecker, A., Hertrich, I., Erb, M., Grodd, W., Ethofer, T., & Ackermann, H. (2004). Identification of emotional intonation evaluated by fMRI. NeuroImage, 24(4), 1233–1241. https://doi.org/10.1016/j.neuroimage.2004.10.034






