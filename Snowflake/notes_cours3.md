# ​ Cours 3 – Resource Monitors dans Snowflake

> **Thématique** : Pilotage intelligent des coûts et contrôle des ressources dans Snowflake

---

##  Objectif du cours

Comprendre les mécanismes d’**observabilité et de gestion proactive des ressources** (crédits) via les *resource monitors* de Snowflake. L'enjeu ? Éviter les surconsommations imprévues et maîtriser le budget.

---

##  Ce que j’ai déjà noté

- Les **resource monitors** permettent de surveiller la consommation des entrepôts virtuels (*virtual warehouses*), d’éviter les usages excessifs via la définition de **quotas de crédit**, et de déclencher des actions – alertes ou suspensions – en cas de dépassement.
- Ils permettent de configurer différents types de déclencheurs (alertes à 80 %, suspension après requêtes en cours, suspension immédiate, etc.), par email ou interface, mais les notifications sont **désactivées par défaut**.
- Seuls les administrateurs (*ACCOUNTADMIN*) peuvent créer ou assigner des monitors. On peut en associer un à plusieurs entrepôts – les seuils sont alors répartis équitablement.

---

##  Informations complémentaires pour renforcer la compréhension

### Rôle et paramètres d’un **Resource Monitor**  
- Il **surveille** les crédits consommés tant par les entrepôts virtuels que par les services cloud (ex. Snowflake services générant du coût invisible) :contentReference[oaicite:0]{index=0}.  
- Les **quotas de crédits** sont fixés pour une période (journalier, hebdo, mensuel, annuel ou jamais) :contentReference[oaicite:1]{index=1}.  
- Un **monitor peut cibler tout le compte (1 seul autorisé)** ou des entrepôts spécifiques (*warehouse-level*, plusieurs possibles) :contentReference[oaicite:2]{index=2}.

### Planification & Actions  
- La **période de monitoring** peut être personnalisée (fréquence, démarrage différé, fin programmée).  
- Actions configurables selon seuils de consommation :  
  - `NOTIFY` (alerte)  
  - `SUSPEND` (suspension après requêtes en cours)  
  - `SUSPEND_IMMEDIATE` (suspension et interruption immédiate).  
- Chaque monitor peut inclure jusqu’à 1 action de type *suspend*, 1 *suspend_immediate* et jusqu’à 5 actions *notify*.

### Création et gestion via SQL  
Exemple de script complet via SQL :

```sql
CREATE OR REPLACE RESOURCE MONITOR my_rm
  WITH CREDIT_QUOTA = 500
       FREQUENCY = MONTHLY
       START_TIMESTAMP = IMMEDIATELY
       TRIGGERS
         ON 75 PERCENT DO NOTIFY
         ON 90 PERCENT DO SUSPEND
         ON 100 PERCENT DO SUSPEND_IMMEDIATE;

-- Assignation à un entrepôt virtuel
ALTER WAREHOUSE my_wh
  SET RESOURCE_MONITOR = my_rm;

