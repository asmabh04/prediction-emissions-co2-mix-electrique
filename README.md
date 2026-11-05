# Prédiction des émissions de CO₂ du mix électrique

Projet réalisé par **Siwar DAGHAR**, **Asma BEN HMIDA** et **Lilia NEKILI**.

## Présentation

Ce projet s'appuie sur la compétition Kaggle [ARE SD 2024 – Émissions CO₂ du mix électrique](https://www.kaggle.com/competitions/are-sd-2024-emissions-co2-du-mix-electrique).

L'objectif est de prédire, à partir de données météorologiques et calendaires, le type de production du mix électrique (`MixProdElec`), qui peut prendre trois valeurs :

- `Carbonne`
- `Decarbonne`
- `Normal`

Les algorithmes de classification sont **implémentés à la main** (sans bibliothèque de machine learning comme scikit-learn), afin de bien comprendre leur fonctionnement.

## Contenu du dépôt

| Fichier | Description |
|---|---|
| `notebook-final.ipynb` | Notebook complet : analyse, implémentation des modèles, prédictions |
| `README.md` | Présentation du projet |

## Méthodologie

1. **Visualisation et préparation des données** : lecture des fichiers CSV avec `pandas`, centrage et réduction des variables (température, humidité, nébulosité, précipitations, position dans l'année, vitesse du vent).
2. **Naive Bayes** : calcul des probabilités a priori et des vraisemblances, puis des probabilités a posteriori pour prédire la classe de chaque ligne. Optimisation du temps d'exécution avec `groupby`.
3. **K plus proches voisins (KNN)** : calcul des distances avec `scipy` (`cdist`), prédiction pour différentes valeurs de `k`.
4. **Validation croisée (K-fold)** : découpage des données en plusieurs groupes et mesure de la précision de chaque modèle.
5. **Arbres de décision** : impureté de Gini et recherche de la meilleure séparation.
6. **Forêts aléatoires** : construction à partir de la méthode du bootstrap.
7. **Création du fichier de soumission** : export des prédictions au format CSV.

## Données

Les données ne sont pas incluses dans ce dépôt (taille trop importante). Elles sont disponibles sur la page Kaggle de la compétition :

- `train.csv` : données d'entraînement
- `prev.csv` : données de test à prédire

Pour exécuter le notebook en local, télécharge ces fichiers et adapte la variable `path_to_data` au début du notebook.

## Bibliothèques utilisées

- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `scipy`

Installation :

```bash
pip install numpy pandas matplotlib seaborn scipy
```

## Utilisation

1. Clone le dépôt :
   ```bash
   git clone https://github.com/TON-PSEUDO/prediction-emissions-co2-mix-electrique.git
   ```
2. Place `train.csv` et `prev.csv` dans un dossier de données et modifie `path_to_data` dans le notebook.
3. Ouvre `prediction-emissions-co2-mix-electrique.ipynb` avec Jupyter Notebook, JupyterLab ou VS Code, puis exécute les cellules dans l'ordre.

## Auteures

- Siwar DAGHAR
- Asma BEN HMIDA
- Lilia NEKILI
