# 📘 Cours 2 – Chargement des données dans Snowflake

> **Thématique** : Data Loading & Architecture pratique

---

## 🎯 Objectif du cours

Comprendre les différentes méthodes d’ingestion de données dans Snowflake, leur fonctionnement, et les bonnes pratiques associées.

---

## 🧩 Méthodes de chargement proposées

Snowflake permet l’intégration de données via plusieurs approches, en fonction des besoins (volume, automatisation, usage technique ou non) :

- **Snowsight** :  
  Interface graphique sans code, utile pour charger des données ponctuelles de faible volume.

- **SQL & SnowSQL** :  
  Méthode recommandée pour les chargements massifs via ligne de commande.

- **Snowpipe** :  
  Permet l’ingestion automatique et continue des données.  
  **Bonnes pratiques** :  
  - Grouper les petits fichiers en lots plus importants.  
  - Réduire les déclencheurs pour minimiser les coûts.

- **Outils ETL/ELT tiers** :  
  Intègrent extraction, transformation et chargement de manière automatisée.

---

## ⚙️ Focus sur le chargement avec SnowSQL

Le processus se déroule en **trois étapes principales** :

### 1. PUT : Téléversement local vers Snowflake

- Fichiers pris en charge :  
  `CSV`, `JSON`, `Parquet`, `Avro`, `XML`, `ORC`
- Les fichiers sont **compressés** et **cryptés** avant d’être envoyés dans le cloud.

---

### 2. Mise en staging

Zone temporaire avant insertion finale :

- **Internal Stage** :  
  - Hébergé par Snowflake  
  - Accessible uniquement par l’utilisateur uploader  
  - Fichiers non modifiables, non supprimables

- **External Stage** :  
  - Relié à des plateformes cloud externes (AWS, Azure, GCP)  
  - Requiert la définition d’un `FILE FORMAT`

```sql
CREATE FILE FORMAT my_format
TYPE = 'CSV'
DELIMITER = ','
SKIP_HEADER = 2;
```

### 3. COPY INTO : Chargement dans une table

Commandes SQL pour intégrer les données dans la table cible :

```sql
COPY INTO my_table
FROM @my_stage
FILES = ('file1.csv')
FILE_FORMAT = (FORMAT_NAME = 'my_format');
```

### 🧠 Bonnes pratiques

- **Taille optimale des fichiers :**
  Entre 100 Mo et 250 Mo pour maximiser les performances.

- **External Tables :**
  Permettent de lire les fichiers directement depuis le stage, sans les copier.

```sql
CREATE EXTERNAL TABLE flight_data
WITH LOCATION = '@s3_external_stage'
FILE_FORMAT = (TYPE = 'PARQUET');
```

- **Optimisation :**
Appliquer des filtres sélectifs et exploiter le partitionnement pour réduire les coûts lors des requêtes.

