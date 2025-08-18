# 📚 Machine Learning (Apprentissage automatique)

L’apprentissage automatique permet de créer des modèles prédictifs capables de générer de la valeur à partir des données. Dans Dataiku, cette démarche est intégrée au *flow* et simplifiée grâce à des outils visuels et de l’AutoML.  

---

## 🔧 Build the flow (Construire le flux)

- **Analyse the data**  
  Explorer les données pour identifier les variables pertinentes et comprendre leur qualité.  
- **Build all the flow**  
  Mettre en place l’ensemble du *flow* (import, préparation, jointures, transformations).

---

## 📊 Split training and testing dataset (Séparer données d’entraînement et de test)

- **Create recipe of split data**  
  Créer une *recipe* pour diviser le dataset.  
- **Define a split method**  
  Définir la méthode de séparation (par ex. 70% entraînement / 30% test).  
- **Create a separate flow zone**  
  Organiser les datasets d’entraînement et de test dans une zone dédiée pour plus de clarté.

---

## 🤖 Train ML models (Entraîner des modèles ML)

- **Create an AutoML prediction task**  
  Lancer une tâche AutoML pour générer automatiquement des modèles candidats.  
- **Define design and train model**  
  Configurer les paramètres et entraîner le modèle.  
- **Adjust design to get the best performance**  
  Ajuster les hyperparamètres et choix de variables pour optimiser la performance.

---

## 🔍 Inspect a model's results (Analyser les résultats)

- **Check model explainability**  
  Étudier quelles variables influencent le plus les prédictions.  
- **Check model performance**  
  Évaluer les métriques (accuracy, F1-score, AUC, etc.).

---

## 🔁 Iterate on design (Itérer sur le design)

- **Adjust the design of training model**  
  Améliorer progressivement le modèle en ajustant ses paramètres ou en modifiant les données d’entrée.

---

## 🚀 Apply a model to generate predictions (Appliquer un modèle)

- **Choose a model to deploy**  
  Sélectionner le meilleur modèle pour la mise en production.  
- **Score data in the test dataset**  
  Produire des prédictions sur le dataset de test.  
- **Inspect the scored data**  
  Vérifier la cohérence et la pertinence des résultats.

---
