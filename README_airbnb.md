# Airbnb Price Prediction 🏠

Prédiction du prix des logements Airbnb à partir de données réelles (22 234 annonces, 6 villes américaines).

## Résultats

| Modèle | RMSE Train | RMSE Val | R² Train | R² Val |
|---|---|---|---|---|
| Baseline | 0.7186 | 0.7192 | 0.0000 | -0.0001 |
| Ridge | 0.4744 | 0.4794 | 0.5643 | 0.5556 |
| Lasso | 0.4744 | 0.4794 | 0.5642 | 0.5557 |
| RandomForest | 0.3942 | 0.4390 | 0.6990 | 0.6273 |
| **GradientBoosting** | **0.3910** | **0.4063** | **0.7040** | **0.6808** |

✅ Meilleur modèle : **GradientBoosting** — RMSE Val 0.4063 / R² Val 0.6808

## Stack technique

- **Python** — pandas, numpy, sklearn
- **Modèles** — GradientBoostingRegressor, RandomForest, Ridge, Lasso
- **Optimisation** — GridSearchCV (recherche des meilleurs hyperparamètres)
- **Visualisation** — matplotlib, seaborn

## Approche

1. **Exploration** — distribution des prix, corrélations, analyse par ville et type de logement
2. **Feature Engineering** — extraction des amenities, encodage ordinal, gestion des valeurs manquantes
3. **Anti Data Leakage** — `train_stats` pour appliquer les mêmes transformations train/test
4. **Modélisation** — comparaison de 5 modèles, optimisation par GridSearchCV

## Features clés

- `accommodates`, `room_type`, `city`, `bedrooms` — variables les plus prédictives
- Variable cible : `log_price` (transformation log pour normaliser la distribution)

## Données

Dataset non inclus (fichiers trop volumineux).
Source : `airbnb_train.csv` et `airbnb_test.csv` fournis dans le cadre du cours ESILV.

## Auteurs

Akihito Raffin & Henri Portier — ESILV, Spécialisation Data & IA
