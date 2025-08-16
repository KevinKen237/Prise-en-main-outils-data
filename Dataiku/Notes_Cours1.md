# 📚 Data Preparation (Préparation des données)

La préparation des données est une étape clé dans tout projet Data Science. Elle consiste à explorer, nettoyer, transformer et organiser les données pour qu’elles soient exploitables dans un flux analytique ou un modèle de Machine Learning.  

---

## 🔎 Explore Data (Explorer les données)

- **Compute row count and sample method**  
  Calculer le nombre de lignes et définir une méthode d’échantillonnage pour mieux comprendre la taille et la représentativité du jeu de données.  
- **Analyse column distributions**  
  Examiner la distribution des valeurs dans chaque colonne (valeurs uniques, valeurs manquantes, fréquences) afin d’identifier anomalies et tendances.

---

## 🛠️ Prepare Data (Préparer les données)

- **Create Recipe | add a new step**  
  Créer une *recipe* de préparation et ajouter des étapes de transformation.  
- **Split column | rename column**  
  Découper une colonne en plusieurs parties et/ou renommer pour plus de clarté.  
- **Simplify text for text-only columns**  
  Nettoyer ou uniformiser le texte (par exemple, mettre en minuscules, retirer les accents).  
- **Use formula**  
  Appliquer des formules personnalisées pour transformer ou enrichir les données.  
- **Duplicate a step**  
  Réutiliser une transformation déjà configurée.  
- **Run the prepare Recipe**  
  Exécuter la *recipe* pour appliquer toutes les étapes aux données.

---

## 📂 Import Data (Importer des données)

- **Upload a new dataset | change the format**  
  Charger un nouveau fichier (CSV, Excel, etc.) et, si nécessaire, adapter son format pour l’intégration dans le projet.

---

## 🔗 Join Data (Joindre des données)

- **Create a Join recipe**  
  Créer une *recipe* de jointure pour fusionner plusieurs jeux de données.  
- **Configure the join step and the condition(s)**  
  Définir les clés de jointure (par ex. ID client).  
- **Handle unmatched rows**  
  Gérer les lignes qui ne trouvent pas de correspondance.  
- **Select column for the output dataset**  
  Choisir les colonnes à conserver dans le résultat.  
- **Build the dataset from the flow**  
  Générer un nouveau dataset directement intégré dans le *flow*.

---

## 💻 Write code in your favourite language (Coder dans votre langage préféré)

- **Create a Code notebook**  
  Créer un notebook (Python, R, etc.) pour plus de flexibilité.  
- **Write code in notebook**  
  Écrire du code personnalisé pour explorer ou transformer les données.  
- **Convert a code notebook to a code recipe**  
  Transformer le notebook en *recipe* intégrée dans le *flow*.  
- **Adjust the flow if necessary**  
  Réorganiser le *flow* pour garder une logique claire et optimisée.

---
