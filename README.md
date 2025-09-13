.
├── ReseauxN_Partie1_GuyJuniorCalvet.ipynb   # Notebook pour l'entraînement du PMC
├── ReseauxN_Partie2_GuyJuniorCalvet.ipynb   # Notebook pour l'entraînement des CNN
├── Customer.csv                           # Jeu de données pour la Partie 1
└── README.md                              # Ce fichier```

---

##  PARTIE 1 : Perceptron Multi-Couches (PMC) pour la Vente en Ligne

### 🎯 Objectif

Analyser des données clients (`Customer.csv`) pour entraîner un Perceptron Multi-Couches capable de prédire le niveau de revenu. Deux classifieurs ont été développés :
*   Un **classifieur binaire** (revenu élevé vs. non élevé).
*   Un **classifieur multi-classes** (revenu faible, moyen, élevé).

### 🛠️ Tâches Réalisées

*   **Prétraitement des données** : Nettoyage et encodage des variables catégorielles.
*   **Recherche d'Architecture** : Détermination du nombre optimal de couches cachées et de neurones.
*   **Validation Croisée** : Entraînement et évaluation robuste du modèle (k=3).
*   **Analyse de Performance** : Mesure des métriques (précision, rappel, F1-Score) et analyse des matrices de confusion.
*   **Courbe d'Apprentissage** : Vérification du sur-ajustement et du sous-ajustement.
*   **Optimisation des Hyperparamètres** : Utilisation de `RandomizedSearchCV` pour trouver la meilleure configuration.
*   **Comparaison** : Évaluation des performances du PMC par rapport à un modèle d'Arbre de Décision du devoir précédent.

### 📊 Résultats Clés

Le **Perceptron Multi-Couches** s'est avéré largement supérieur au modèle d'Arbre de Décision du devoir #2, en particulier pour la classification multi-classes où il a réussi à équilibrer les prédictions entre les différentes classes, contrairement à l'arbre qui présentait un fort biais.

| Modèle | Exactitude (Accuracy) | F1-Score (Pondéré) | Bilan |
| :--- | :---: | :---: | :--- |
| Arbre de Décision | 51% | 0.34 | Très déséquilibré, ignore les classes minoritaires. |
| **PMC (MLPClassifier)** | **70%** | **0.70** | **Performances équilibrées et nettement supérieures.** |

---

## PARTIE 2 : Réseaux de Neurones à Convolution (CNN) pour la Classification d'Images

### 🎯 Objectif

Classifier les images du jeu de données **Fashion-MNIST** en utilisant des architectures de réseaux de neurones de plus en plus complexes et performantes.

### 🛠️ Tâches Réalisées

1.  **Modèle de Référence (PMC)** : Exécution d'un Perceptron Multi-Couches de base avec Keras pour établir une performance de référence.
2.  **CNN Personnalisé** : Implémentation d'un Réseau de Neurones à Convolution pour améliorer la précision.
3.  **CNN avec Augmentation de Données** : Utilisation de `ImageDataGenerator` pour créer de nouvelles images d'entraînement (rotations, zooms, etc.) afin de lutter contre le sur-apprentissage et d'améliorer la généralisation.
4.  **Apprentissage par Transfert** : Utilisation du modèle pré-entraîné **VGG16** pour tirer parti de ses couches de convolution déjà optimisées sur un grand volume d'images.

### 📊 Résultats Comparatifs

Une analyse comparative des quatre modèles a été menée en se basant sur la précision finale sur l'ensemble de test et le temps d'entraînement.

| Modèle | Exactitude (Accuracy) | Temps d'entraînement (secondes) | Analyse |
| :--- | :---: | :---: | :--- |
| PMC (Keras) | 88.86% | 161.22 | Rapide mais moins précis que les CNN. |
| **CNN Personnalisé** | **93.12%** | 2630.80 | **Meilleur compromis performance/temps.** |
| CNN + Augmentation | 91.37% | 2994.18 | Efficace contre le sur-apprentissage, mais légère baisse de précision. |
| VGG16 (Transfert) | 87.61% | 14458.45 | Moins performant et beaucoup plus long, probablement surdimensionné pour ce jeu de données. |

Le **CNN personnalisé (2.2.2)** s'est révélé être le modèle le plus performant pour cette tâche.

## 🚀 Comment Exécuter

### Prérequis

*   Python 3.x
*   Jupyter Notebook ou JupyterLab
*   Bibliothèques listées dans `requirements.txt`

### Installation

1.  Clonez le dépôt :
    ```bash
    git clone [URL_DU_DEPOT]
    cd [NOM_DU_DEPOT]
    ```2.  (Optionnel mais recommandé) Créez un environnement virtuel :
    ```bash
    python -m venv env
    source env/bin/activate  # Sur Windows: env\Scripts\activate
    ```
3.  Installez les dépendances :
    ```bash
    pip install -r requirements.txt
    ```
    *Note : Si vous n'avez pas de fichier `requirements.txt`, vous pouvez installer les bibliothèques manuellement :*
    ```bash
    pip install pandas numpy scikit-learn matplotlib tensorflow
    ```

### Lancement

1.  Démarrez Jupyter Notebook :
    ```bash
    jupyter notebook
    ```
2.  Ouvrez et exécutez les cellules des notebooks `Devoir3_Partie1_GuyJuniorCalvet.ipynb` et `Devoir3_Partie2_GuyJuniorCalvet.ipynb`. Assurez-vous que le fichier `Customer.csv` est dans le même répertoire que le notebook de la partie 1.
