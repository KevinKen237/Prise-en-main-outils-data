# 📚 Cours 5 : La hiérarchie d'objets Snowflake

La hiérarchie d'objets Snowflake constitue la base de l'organisation et de la gestion des données dans Snowflake. Cette hiérarchie définit la façon dont les données sont structurées, accessibles et contrôlées au sein de votre compte. Comprendre ce système (des organisations aux comptes, en passant par les bases de données, les schémas et les objets tels que les tables et les vues) permet de gérer efficacement les données et de garantir des pratiques sécurisées, évolutives et optimisées.

---

## 🌐 Importance de la hiérarchie

Lorsqu’on travaille avec de grandes quantités de données, il est crucial de les organiser de manière significative. Sans structure, l’environnement devient rapidement chaotique. La hiérarchie des objets de Snowflake permet de garder les données organisées, sécurisées et faciles à trouver.

Snowflake structure les données à l’aide de **conteneurs** et **d’objets**, ce qui facilite le contrôle d’accès et l’efficacité de gestion.

---

## 📊 Structure hiérarchique

- **Organisation**  
  Niveau le plus élevé, composé d’un ou plusieurs comptes Snowflake.

- **Compte**  
  Représente un déploiement unique de Snowflake incluant données, utilisateurs, rôles et paramètres.

- **Base de données**  
  Conteneur logique pour organiser les données par sujet, département ou fonction. Peut contenir plusieurs schémas.

- **Schéma**  
  Contient des tables, vues, étapes, formats de fichiers, séquences, procédures stockées, fonctions, etc.

- **Table**  
  Objet de stockage pour données structurées ou semi-structurées.

- **Vue**  
  Représentation d’une requête.  
  - **Vue matérialisée** : stocke les résultats.  
  - **Vue sécurisée** : protège la confidentialité des données.

- **Étape**  
  Espace de stockage pour charger ou décharger des fichiers.  
  - **Interne** : au sein de Snowflake.  
  - **Externe** : sur AWS S3, Azure Blob Storage, GCS.

---

## 🧩 Notions clés

- **Conteneur**  
  Regroupe logiquement des objets (ex : une base de données contenant plusieurs schémas).

- **Objet**  
  Toute entité individuelle stockant ou manipulant des données (tables, vues, schémas, etc.).

- **Hiérarchie**  
  Structure imbriquée : un compte contient des bases de données → des schémas → des objets.

---

## 💡 Exemple concret

Une entreprise internationale utilise Snowflake :  
- Un **compte** par entreprise.  
- Plusieurs **bases de données** (ventes, RH, finances).  
- Dans chaque base, des **schémas** par région (Amérique du Nord, Europe, etc.).  
- Chaque schéma contient **tables** et **vues** (ex : dossiers employés, transactions de vente).

---

## 🔍 Détails par niveau

### 1. Bases de données : fondation
- **Rôle** : contiennent des schémas.  
- **Contrôle d'accès** : autorisations au niveau base, schéma ou objet.

### 2. Schémas : organisation interne
- **Rôle** : regroupent tables, vues, étapes, etc.  
- **Utilité** : séparer logiquement les données (ex : ventes NA vs Europe).  
- **Contrôle d'accès** : autorisations spécifiques possibles.

### 3. Objets : lieu de vie des données
- **Tables** :  
  - Permanentes (stockage long terme)  
  - Transitoires (courte durée)  
  - Temporaires (session uniquement)
- **Vues** :  
  - Non matérialisées (résultat calculé à la volée)  
  - Matérialisées (résultats stockés)  
  - Sécurisées (protection données sensibles)
- **Flux** : suivis des modifications sur tables.  
- **Étapes** :  
  - Internes  
  - Externes  
  - Utilisateur (automatique par Snowflake)  
  - Table (automatique par Snowflake)

---

## ⚠️ Erreurs courantes
- Créer trop de bases ou schémas (complexité inutile).  
- Oublier les contrôles de sécurité (risques de fuite).  
- Utiliser des tables permanentes pour des données non critiques (coût élevé).

---

## ✅ Bonnes pratiques
- Garder la hiérarchie **simple** et **logique**.  
- Auditer régulièrement les **autorisations**.  
- Optimiser les performances via **partitionnement** des schémas/tables.

---
