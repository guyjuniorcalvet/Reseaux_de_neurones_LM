# Projets de Réseaux de Neurones : Applications PMC et CNN

Ce dépôt présente deux projets distincts d'apprentissage automatique démontrant l'application et l'optimisation de réseaux de neurones pour des tâches de classification sur des données tabulaires et des images.

**Technologies et Bibliothèques :**
*   **Langage :** Python
*   **Analyse de Données :** Pandas, NumPy
*   **Machine Learning :** Scikit-Learn
*   **Deep Learning :** TensorFlow, Keras
*   **Visualisation :** Matplotlib

---

## 📂 Structure du Dépôt


---

## 📈 Projet 1 : Prédiction de Revenu Client avec un Perceptron Multi-Couches (PMC)

### Objectif du Projet
L'objectif de ce projet était de construire un modèle prédictif capable de classifier les clients en différentes catégories de revenus (faible, moyen, élevé) à partir de leurs données comportementales. Ce type de modèle est essentiel pour des applications commerciales comme le ciblage marketing ou la segmentation client.

### Démarche et Techniques Mises en Œuvre

1.  **Prétraitement des Données :** Nettoyage, gestion des valeurs manquantes et encodage des variables catégorielles (ex: `gender`, `country`) pour préparer les données pour le modèle.
2.  **Ingénierie des Caractéristiques :** Création de variables cibles pour des problèmes de **classification binaire** (revenu supérieur à la moyenne ou non) et **multi-classes** (revenu faible, moyen, élevé basé sur les quartiles).
3.  **Entraînement du Modèle :** Utilisation de la classe `MLPClassifier` de Scikit-Learn pour entraîner les deux types de classifieurs.
4.  **Optimisation des Hyperparamètres :** Recherche de la meilleure architecture de réseau de neurones (nombre de couches, nombre de neurones) et des meilleurs paramètres d'entraînement (fonction d'activation, solveur) à l'aide de `RandomizedSearchCV` pour une optimisation efficace.
5.  **Évaluation et Analyse :**
    *   Utilisation de la **validation croisée** pour garantir la robustesse du modèle.
    *   Analyse des performances via des métriques clés (**précision, rappel, F1-score**) et des **matrices de confusion**.
    *   Génération de **courbes d'apprentissage** pour diagnostiquer le sur-ajustement et s'assurer que le modèle généralise bien.

### Résultats
Le PMC optimisé a montré des performances nettement supérieures à un modèle de base (Arbre de Décision), avec une précision de **70%** et un F1-score pondéré de **0.70** dans la tâche multi-classes. Contrairement à l'arbre, le PMC a réussi à prédire de manière équilibrée toutes les classes de revenus, y compris les minoritaires.

---

## 🖼️ Projet 2 : Classification d'Images avec des Réseaux de Neurones à Convolution (CNN)

### Objectif du Projet
Ce projet explore la construction et la comparaison de plusieurs architectures de deep learning pour la classification d'images sur le jeu de données **Fashion-MNIST**. L'objectif était de comparer l'efficacité de différentes approches, de la plus simple à la plus avancée.

### Modèles Développés et Techniques Explorées

1.  **Modèle de Référence (PMC) :** Un Perceptron Multi-Couches de base a été implémenté avec Keras pour établir une performance de référence.
2.  **CNN Personnalisé :** Conception et entraînement d'un Réseau de Neurones à Convolution (CNN) incluant des couches de convolution, de pooling, de normalisation par lots (`BatchNormalization`) et de régularisation (`Dropout`).
3.  **CNN avec Augmentation de Données :** Pour améliorer la généralisation et réduire le sur-apprentissage, la technique d'augmentation de données a été appliquée en utilisant `ImageDataGenerator` de Keras, créant ainsi des variations synthétiques des images d'entraînement (rotations, zooms, décalages).
4.  **Apprentissage par Transfert (Transfer Learning) :** Utilisation du modèle pré-entraîné **VGG16** comme extracteur de caractéristiques fixes, en y ajoutant des couches denses personnalisées pour la classification finale.

### Analyse Comparative des Performances

| Modèle | Exactitude (Test) | Temps d'entraînement (sec) | Analyse |
| :--- | :---: | :---: | :--- |
| PMC (Keras) | 88.86% | 161 | Rapide mais moins performant que les architectures CNN. |
| **CNN Personnalisé** | **93.12%** | 2631 | **Excellent équilibre entre une haute précision et un temps d'entraînement raisonnable.** |
| CNN + Augmentation | 91.37% | 2994 | A réduit le sur-apprentissage mais a légèrement diminué la précision finale. |
| VGG16 (Transfert) | 87.61% | 14458 | Le modèle le plus long à entraîner, probablement surdimensionné pour la complexité de Fashion-MNIST. |

### Conclusion du Projet
Le **CNN personnalisé** s'est révélé être l'approche la plus efficace pour ce problème, offrant la meilleure précision tout en restant efficient en termes de temps de calcul.

---

## 🚀 Comment Exécuter

### Prérequis
*   Python 3.8+
*   Jupyter Notebook ou un IDE compatible (ex: VS Code)

### Installation
1.  Clonez le dépôt sur votre machine locale :
    ```bash
    git clone [URL_DU_DEPOT]
    cd [NOM_DU_DEPOT]
    ```
2.  Il est recommandé de créer un environnement virtuel :
    ```bash
    python -m venv env
    source env/bin/activate  # Sur Windows: env\Scripts\activate
    ```
3.  Installez les bibliothèques nécessaires :
    ```bash
    pip install pandas numpy scikit-learn matplotlib tensorflow
    ```

### Lancement
1.  Démarrez le serveur Jupyter :
    ```bash
    jupyter notebook
    ```
2.  Ouvrez et exécutez les notebooks situés dans leurs dossiers respectifs :
    *   `Projet_1_PMC_Prediction_Revenu/ReseauxN_Partie1_PMC.ipynb`
    *   `Projet_2_CNN_Classification_Image/ReseauxN_Partie2_CNN.ipynb`
