# 📚 Data Preparation and Visualization (Préparation et Visualisation des Données)

La préparation et la visualisation des données dans Dataiku permettent de transformer des données brutes en informations exploitables.  
L’objectif est de nettoyer, combiner et explorer les datasets, puis de les représenter sous forme de graphiques ou de tableaux de bord afin d’en faciliter l’analyse.  

---

## 🔎 Explore Data (Explorer les données)

- **Compute row count and sample method**  
  Vérifier le nombre de lignes et appliquer une méthode d’échantillonnage pour analyser un sous-ensemble représentatif du dataset.  

- **Analyse column distributions**  
  Examiner la distribution des colonnes pour détecter les valeurs manquantes, atypiques ou déséquilibrées.  

---

## 🧹 Clean Data (Nettoyer les données)

- **Pivot Data**  
  Créer une recette de pivot pour réorganiser les données en définissant les identifiants de ligne et en ajoutant de nouvelles colonnes.  

- **Prepare Recipe**  
  Ajouter des étapes de préparation comme le *parsing* des dates grâce à la fonction *smart date*.  

- **Remove outliers**  
  Détecter et supprimer les valeurs extrêmes dans les colonnes numériques en utilisant la règle des **5 IQR**.  
  Cette opération est répétée pour toutes les variables numériques.  

---

## 📂 Import Data (Importer les données)

- **Upload a new dataset**  
  Charger un nouveau jeu de données dans Dataiku et modifier son format si nécessaire (CSV, Excel, etc.).  

---

## 🔗 Join Data (Joindre les données)

- **Create a Join recipe**  
  Fusionner plusieurs datasets grâce à une recette de jointure.  

- **Configure the join step**  
  Définir les conditions de jointure (ex. clé unique, identifiant commun).  

- **Handle unmatched rows**  
  Décider de conserver uniquement les correspondances ou d’intégrer aussi les lignes non appariées.  

- **Select output columns**  
  Choisir les colonnes à inclure dans le jeu de données final.  

- **Build dataset from flow**  
  Générer automatiquement le dataset issu de la jointure depuis le *flow*.  

---

## 📊 Create Visualizations and Dashboard (Créer des visualisations et un tableau de bord)

- **Dataset | Chart**  
  Construire des graphiques variés (KPI, barres empilées, etc.) directement à partir d’un dataset.  

- **Make multiple charts**  
  Créer plusieurs visualisations pour explorer différentes dimensions des données.  

- **Publish Dashboard**  
  Regrouper toutes les visualisations dans un **dashboard interactif** avec titre, filtres et options de personnalisation.  

---

👉 Cette formation illustre comment, avec Dataiku, on peut :  
1. Explorer et nettoyer efficacement les données.  
2. Fusionner des sources multiples.  
3. Créer des visualisations pertinentes.  
4. Partager des résultats clairs via un Dashboard.  
