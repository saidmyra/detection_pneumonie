Détection de la Pneumonie à partir de Radiographies Thoraciques

Projet de Deep Learning appliqué à l’imagerie médicale visant à détecter automatiquement la pneumonie à partir de radiographies thoraciques grâce à un réseau de neurones convolutifs (CNN).

Aperçu du projet

Ce projet consiste à développer un modèle de classification binaire capable de distinguer :

NORMAL → Poumons sains sans anomalies
PNEUMONIA → Présence d’une infection pulmonaire

L’objectif est d’assister les professionnels de santé en signalant automatiquement les radiographies suspectes.

Technologies utilisées
Python
PyTorch
CNN (Convolutional Neural Networks)
NumPy
Matplotlib
Scikit-learn
Prétraitement des données

Plusieurs techniques de preprocessing ont été appliquées afin d’améliorer les performances du modèle :

Redimensionnement
Conversion des images en 128x128
Optimisation des opérations de convolution
Normalisation
Conversion en tenseurs PyTorch
Standardisation des données
Data Augmentation
RandomHorizontalFlip
Amélioration de la robustesse du modèle
Gestion du déséquilibre des classes

Le dataset étant déséquilibré (plus d’images PNEUMONIA que NORMAL), une stratégie d’équilibrage a été mise en place.

Solution utilisée
WeightedRandomSampler

Cette approche permet :

d’augmenter le poids de la classe minoritaire
d’obtenir des batchs plus équilibrés
de limiter le biais du modèle
Architecture du modèle CNN

Le modèle est composé de plusieurs blocs convolutionnels suivis d’un classifieur dense.

Structure
Blocs convolutionnels
Conv2D
BatchNorm
ReLU
MaxPooling
AdaptiveAvgPool
Classifieur
Flatten
Linear
ReLU
Dropout
Linear final
Sortie
Sigmoid
Probabilité de pneumonie
Configuration de l’entraînement

Plusieurs techniques ont été utilisées pour améliorer la stabilité et les performances du modèle.

Optimisation
Optimiseur Adam
Fonction de perte
Focal Loss
Adaptée aux datasets déséquilibrés
Régularisation
Early Stopping
ReduceLROnPlateau
Résultats

Le modèle obtient une excellente capacité de discrimination avec une AUC de 0.944.

Performances
Classe NORMAL
128 images correctement classifiées
106 faux positifs
Classe PNEUMONIA
388 images correctement détectées
Seulement 2 faux négatifs
Analyse des résultats
Points forts
Très forte sensibilité (>99%)
Seulement 2 pneumonies manquées
Bonne robustesse malgré le déséquilibre des classes
Excellente capacité de discrimination (AUC élevée)
Limites

Le modèle génère encore plusieurs faux positifs sur les images normales.

Interprétation

Le modèle adopte une stratégie conservatrice :
il préfère détecter un cas suspect plutôt que manquer une pneumonie réelle.

Perspectives d’amélioration

Plusieurs pistes peuvent être explorées pour améliorer le modèle :

Tester différents seuils de décision
Augmenter le dataset de validation
Utiliser des modèles pré-entraînés :
ResNet
VGG
DenseNet
Comparer différentes tailles d’images
Important

⚠️ Ce modèle n’a pas vocation à remplacer un diagnostic médical professionnel.
Il s’agit d’un outil d’aide à la décision destiné à assister les radiologues dans la détection précoce des cas suspects.

Auteurs
Said Myra
