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

Ainsi, eninsipirant du projet de Nakai et al., ce projet cherche à savoir s'il est possible de prédire le genre musical écouté en se basant uniquement sur des patterns de connectivité fonctionnelles en IRMf.

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
![image resultats](images/cfd05776-b6c6-4424-bd0c-5bc28a3a1228.jfif)










