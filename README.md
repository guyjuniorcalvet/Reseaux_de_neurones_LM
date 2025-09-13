Projets de Réseaux de Neurones : Applications PMC et CNN
Ce dépôt contient deux projets d'apprentissage automatique démontrant l'entraînement, l'optimisation et la comparaison de réseaux de neurones pour des tâches de classification sur des données tabulaires et des images.
Technologies et Bibliothèques :
Langage : Python
Analyse de Données : Pandas, NumPy
Machine Learning : Scikit-Learn
Deep Learning : TensorFlow, Keras
Visualisation : Matplotlib
📂 Structure du Dépôt
code
Code
.
├── Projet_1_PMC_Prediction_Revenu/
│   ├── ReseauxN_Partie1_PMC.ipynb          # Notebook pour l'entraînement du PMC
│   └── Customer.csv                      # Jeu de données
│
├── Projet_2_CNN_Classification_Image/
│   └── ReseauxN_Partie2_CNN.ipynb          # Notebook pour l'entraînement des CNN
│
└── README.md                                 # Ce fichier
📈 Projet 1 : Prédiction de Revenu Client avec un Perceptron Multi-Couches (PMC)
Objectif du Projet
Développer un modèle capable de classifier les clients en différentes catégories de revenus à partir de leurs données comportementales (âge, genre, pays, activité sur le site). Ce projet explore la mise en œuvre d'un classifieur pour des applications commerciales comme le ciblage marketing ou la segmentation client.
Démarche et Techniques Mises en Œuvre
Prétraitement des Données : Nettoyage, gestion des valeurs manquantes et encodage des variables catégorielles avec LabelEncoder.
Ingénierie des Caractéristiques : Création de variables cibles pour deux scénarios :
Classification Binaire : Revenu supérieur ou inférieur à la moyenne.
Classification Multi-Classes : Revenu faible, moyen ou élevé, basé sur les quartiles.
Entraînement et Optimisation : Utilisation de MLPClassifier de Scikit-Learn pour entraîner les modèles. La meilleure architecture a été identifiée grâce à RandomizedSearchCV pour optimiser les hyperparamètres (nombre de couches, neurones, fonction d'activation, etc.).
Évaluation Rigoureuse :
Application de la validation croisée pour assurer la robustesse du modèle.
Analyse des performances via des métriques clés (précision, rappel, F1-score) et des matrices de confusion.
Analyse des courbes d'apprentissage pour diagnostiquer le sur-apprentissage.
Résultats
Le PMC optimisé a atteint une précision de 70% sur la tâche de classification multi-classes, démontrant une capacité à prédire de manière équilibrée toutes les catégories de revenus, y compris les classes minoritaires.
🖼️ Projet 2 : Classification d'Images avec des Réseaux de Neurones à Convolution (CNN)
Objectif du Projet
Ce projet explore et compare plusieurs architectures de deep learning pour la classification d'images sur le jeu de données Fashion-MNIST. L'objectif était de démontrer l'efficacité croissante des modèles, depuis un réseau de neurones dense simple jusqu'à des techniques avancées comme l'apprentissage par transfert.
Modèles Développés et Techniques Explorées
Modèle de Référence (PMC) : Un Perceptron Multi-Couches de base a été implémenté avec Keras pour établir une performance de référence.
CNN Personnalisé : Conception et entraînement d'un Réseau de Neurones à Convolution (CNN) incluant des couches de convolution, de pooling, de normalisation par lots (BatchNormalization) et de régularisation (Dropout).
CNN avec Augmentation de Données : Pour améliorer la généralisation et réduire le sur-apprentissage, la technique d'augmentation de données a été appliquée en utilisant ImageDataGenerator de Keras, créant ainsi des variations synthétiques des images d'entraînement (rotations, zooms, décalages).
Apprentissage par Transfert (Transfer Learning) : Utilisation du modèle pré-entraîné VGG16 comme extracteur de caractéristiques fixes, en y ajoutant des couches denses personnalisées pour la classification finale.
Analyse Comparative des Performances
Modèle	Exactitude (Test)	Temps d'entraînement (sec)	Analyse
PMC (Keras)	88.86%	161	Rapide mais moins performant que les architectures CNN.
CNN Personnalisé	93.12%	2631	Meilleur équilibre entre une haute précision et un temps d'entraînement raisonnable.
CNN + Augmentation	91.37%	2994	A réduit le sur-apprentissage mais a légèrement diminué la précision finale.
VGG16 (Transfert)	87.61%	14458	Le modèle le plus long à entraîner, probablement surdimensionné pour la complexité de Fashion-MNIST.
Conclusion
Le CNN personnalisé s'est révélé être l'approche la plus efficace pour ce problème, offrant la meilleure précision tout en restant efficient en termes de temps de calcul.
🚀 Comment Exécuter
Prérequis
Python 3.8+
Jupyter Notebook ou un IDE compatible (ex: VS Code)
Installation
Clonez le dépôt sur votre machine locale :
code
Bash
git clone [URL_DU_DEPOT]
cd [NOM_DU_DEPOT]
Il est recommandé de créer un environnement virtuel :
code
Bash
python -m venv env
source env/bin/activate  # Sur Windows: env\Scripts\activate
Installez les bibliothèques nécessaires :
code
Bash
pip install pandas numpy scikit-learn matplotlib tensorflow
Lancement
Démarrez le serveur Jupyter :
code
Bash
jupyter notebook
Ouvrez et exécutez les notebooks situés dans leurs dossiers respectifs :
Projet_1_PMC_Prediction_Revenu/ReseauxN_Partie1_PMC.ipynb
Projet_2_CNN_Classification_Image/ReseauxN_Partie2_CNN.ipynb
