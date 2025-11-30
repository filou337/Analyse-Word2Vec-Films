# 🎬 Analyse Word2Vec d’une base de données de films

Ce repo regroupe mon projet autour d’un dataset de films (type **The Movies Dataset – Kaggle**) où je fais deux choses en parallèle:

1. Côté **chiffres** : je construis un modèle supervisé pour expliquer/prédire le **logarithme du revenu** d’un film à partir de variables comme les votes, la note moyenne, etc.
2. Côté **texte** : j’entraîne un modèle **Word2Vec (skip-gram)** sur les synopsis des films pour voir comment le vocabulaire se structure en “univers” thématiques (famille, guerre, monde, etc.).

👤 **Auteur** : Philippe ROUMBO  
🎓 Master Big Data & Business Intelligence – Université Sorbonne Paris Nord  

---

## 🔍 Ce que je fais concrètement

L’idée générale, c’est :

- Je pars d’un dataset de films avec `revenue`, `budget`, `popularity`, `vote_average`, `vote_count`, `adult`, `video` et surtout `overview` (le synopsis).
- Je construis un premier pipeline **ML supervisé** classique (régression linéaire + RandomForest) sur une cible transformée en log : `ln_revenue`.
- Ensuite, je passe en mode **NLP** : je nettoie les synopsis, j’entraîne un Word2Vec, puis je fais **PCA, t-SNE et K-Means** pour comprendre comment les mots se regroupent.

En gros :  
> d’un côté, j’essaie de voir ce qui explique le box office,  
> de l’autre, je regarde comment le langage des synopsis s’organise dans un espace vectoriel.

---

## 📂 Organisation du projet

```text
.
├── notebooks/
│   └── NLP.ipynb                    # Notebook principal : EDA, régression, Word2Vec, PCA, t-SNE, clustering
├── data/
│   └── raw/
│       └── movies_metadata.csv      # Dataset Kaggle (The Movies Dataset)
├── docs/
│   └── Rapport_Word2Vec_Films.pdf   # Rapport complet (version LaTeX → PDF)
└── README.md
