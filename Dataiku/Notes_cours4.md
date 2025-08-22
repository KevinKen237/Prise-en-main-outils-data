# 📚 MLOps with Dataiku (MLOps avec Dataiku)

La formation **MLOps** dans Dataiku permet de transformer un modèle en un service opérationnel : construire un flow complet, exposer une API, la déployer en production et automatiser le processus avec contrôle qualité des données.  
Voici le résumé détaillé des étapes suivies.

---

## 🔧 Build the flow (Construire le flux)

- **Complete the flow for prediction**  
  Compléter le *flow* afin d’aller jusqu’à la prédiction.  
- **Build all the flow**  
  Construire l’ensemble du flux (préparation, entraînement, scoring).

---

## 🌐 Create an API endpoint (Créer un point d’accès API)

- **Select the chosen model**  
  Choisir le modèle que l’on souhaite exposer.  
- **Action → Create API**  
  Créer une API à partir du modèle.  
- **API service ID & Endpoint ID**  
  - API service ID : nom du dataset ou du projet (ex : `fake_jobs_service`)  
  - Endpoint ID : identifiant de l’endpoint (ex : `predict_fake_job`)  
- **Test queries (5 minimum)**  
  - Ajouter des requêtes depuis le dataset de test  
  - Lancer les requêtes de test  
- **Inspect details**  
  Vérifier :  
  - Les features envoyées à l’endpoint  
  - La prédiction retournée  
  - Les détails additionnels associés

---

## 🚀 Deploy an API endpoint (Déployer un point d’accès API)

- **Publish → Déployer**  
  Publier le service API créé.  
- **Open API Deployer**  
  - Sélectionner *API Services*  
  - Rechercher l’API service ID  
  - Cliquer sur *Deploy*  
  - Choisir une infrastructure disponible (ou en sélectionner une autre en cas d’erreur)  
- **Warnings & Errors**  
  - Si *warning* : ignorer (lié à la *Govern Policy*)  
  - Si *error* : changer d’infrastructure et relancer  
- **API endpoint in production**  
  À ce stade, l’API est disponible dans un environnement de production.  
- **Run test queries**  
  - Depuis l’Endpoint dans l’API Deployer  
  - Naviguer vers *Run and Test Panel*  
  - Lancer toutes les requêtes (*Run all*)  

---

## 🔄 Automate the Flow (Automatiser le flux)

- **Create a scenario**  
  - Onglet `|>` → *Scenarios* → sélectionner *score data*  
  - Paramètres par défaut : exécution hebdomadaire (*weekly*)  
- **Configure build step**  
  - Naviguer dans *Steps*  
  - Cliquer sur *Build step* (cocher la case)  

---

## ✅ Check Data Quality (Vérifier la qualité des données)

### Définir une règle qualité
- Dans la zone *Data Preparation Flow*, ouvrir le dataset préparé  
- Onglet *Data Quality* → *Edit Rules*  
- Ajouter la règle *Record count in range*  
- Configurer et tester la règle

### Intégrer la règle dans un scénario
- Ouvrir `|>` → *Scenarios* → sélectionner *score data*  
- Aller dans *Steps* → *Add step* → *Verify rules or run checks*  
- Cliquer sur *+ Add item* → *Dataset* → sélectionner `prepared_dataset` → *Add*  
- Glisser cette étape tout en haut (drag avec `::`)  
- Lancer le scénario (*Run*) pour tester l’exécution  

### Inspecter le résultat
- Onglet *Last runs* du scénario → consulter le dernier run  
- Ouvrir le *Build step* → constater que rien n’est exécuté si la règle n’est pas satisfaite  

---

👉 Avec ce workflow complet, Dataiku permet de :  
1. Créer un modèle prédictif prêt pour la production  
2. L’exposer en tant qu’API et le déployer  
3. Automatiser les exécutions via scénarios  
4. Garantir la qualité des données avant toute tâche  

Un véritable processus **MLOps intégré et opérationnel**.
e, Dataiku rend le **MLOps accessible et opérationnel** : déployer un modèle, l’exposer en API, automatiser les mises à jour et garantir la qualité des données deviennent des étapes intégrées et simples à suivre.
