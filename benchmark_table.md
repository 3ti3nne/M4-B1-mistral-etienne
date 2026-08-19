# Tableau comparatif — Benchmark Mistral Assurances

> Document à remettre à **Inès Tabet** (responsable actuariat). Doit être
> lisible par un actuaire, pas par un data scientist.
> Auteur : `<prénom>` — Date : `<date>`

## Méthodologie

- **Split** : `<TimeSeriesSplit n_splits=5>` *(ou KFold n_splits=5, justifié dans le notebook)*
- **Métriques** : MAE, RMSE, R² (moyennes sur N folds)
- **Mêmes folds, mêmes features** pour tous les modèles (règle d'or *comparabilité*)
- **Hyperparamètres** : par défaut + 1 variante raisonnable par famille
- **Référence** : baseline `mistral-tarif-v1` (LinearRegression 2024)

## Tableau (à compléter)

| Modèle                          | MAE   | RMSE  | R²   | Temps train (s) | Latence inférence (ms/1k) | Explicabilité (1-3) | Mémoire (Mo) |
|---------------------------------|-------|-------|------|-----------------|---------------------------|---------------------|--------------|
| **mistral-tarif-v1** (baseline) | 114.2 | 147.8 | 0.32 | ~0.1            | ~0.8                      | 3 (très explicable) | ~0.001       |
| Ridge                           | 117.9 | 156.9 | 0.22 | 0.005           | 0.9                       | 3                   | 0.002        |
| RandomForest                    | 52.9  | 79.3  | 0.78 | 4.6             | 15.8                      | 2                   | 150.134      |
| HistGradientBoosting            | 51.8  | 76.3  | 0.79 | 0.4             | 4.7                       | 2                   | 0.368        |

## Interprétation pour Inès

Deux concurrents à la première place avec RandomForest et HistGB, on recommande HistGB car il est tout simplement plus précis, il fera moins d'erreur, il sera meilleur sur les cas extrèmes qui sont fréquents sur les données que vous nous avez envoyé, il est 10 fois plus rapide à entraîner et bien plus rapide en inférence : au moins 10 ms de gagnées par millier de prédictions, il est aussi bien plus léger que son concurrent.

## Recommandation

Voir `verdict.md` (5 lignes max).

---

*Document remis à Inès Tabet — `<date>`.*
