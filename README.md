# 💳 Fintech Data Dashboard — Power BI

## 📘 Description du projet
Ce projet présente un **dashboard complet pour une fintech** visant à analyser la performance des agences, les dépenses, les fraudes et les comportements clients à travers des visualisations interactives sous **Power BI**.

Le projet inclut une approche **de modélisation de données robuste**, des **indicateurs clés de performance (KPIs)**, et une **page de storytelling** qui raconte l’évolution du chiffre d’affaires et les leviers de performance de l’entreprise.

---
![La page Overview](https://github.com/YabGui224/fintech-bi-dashboard/screenshots/overview.png)
![La page Overview](https://github.com/YabGui224/fintech-bi-dashboard/screenshots/frauds.png)


## Objectifs du projet
- Offrir une **vision globale** de la performance financière et opérationnelle.
- Identifier les **causes de la baisse du chiffre d’affaires (CA)**.
- Surveiller les **KPIs critiques** : taux de fraude, dépenses, budget, activité client.
- Évaluer la **performance des agences et des services**.
- Mettre en lumière des **insights actionnables** à travers une page de storytelling.

---

## Modèle de données

### Tables utilisées :
| Table | Description |
|-------|--------------|
| **Agents** | Contient les informations sur les agents (ID, nom, ville, agence). |
| **Budget_Departements** | Suivi des budgets par département et par période. |
| **Clients** | Détails sur les clients (date d’inscription, nombre de transactions, dépenses totales). |
| **Dépenses** | Montants dépensés par type, département et agence. |
| **Fraudes** | Historique des fraudes par client, service et agence. |
| **Transactions** | Historique des transactions (client, agent, service, montant, date). |

📐 **Schéma de données** :  
Le modèle adopte une structure en **étoile (Star Schema)** où les tables de faits (Transactions, Dépenses, Fraudes) sont reliées aux tables de dimensions (Clients, Agents, Budget_Departements).

---

## 📊 Pages du Dashboard

### 1. **Overview**
- Vue d’ensemble du chiffre d’affaires, des transactions et des clients.
- Indicateurs clés : CA total, nombre de clients actifs, volume de transactions, taux de fraude global.
- Courbes et cartes géographiques interactives.

---

### 2. **Clients**
- Analyse du portefeuille client : croissance, engagement, dépenses moyennes.
- Segmentation par ville et par ancienneté.
- Classement des meilleurs clients selon la dépense totale.

---

### 3. **Budget & Dépenses**
- Comparaison du budget prévu vs dépenses réelles.
- Visualisation par département et type de dépense.
- Suivi des écarts budgétaires et identification des zones de dépassement.

---

### 4. **Transactions**
- Suivi du volume de transactions par service, agent et agence.
- Analyse temporelle (par jour, semaine, mois).
- Distribution des montants et fréquence des opérations.

---

### 5. **Storytelling (Analyse narrative)**
> Une page dédiée à la compréhension des **tendances clés et anomalies**.

**Contenu narratif :**
- *Pourquoi la baisse du CA ?*  
  Analyse des services et agences à faible performance.  
- *KPIs à suivre de près*  
   Taux de fraude, dépenses, budget utilisé, CA par service.  
-  *Agences performantes et sous-performantes*  
   Classement des agences et visualisation comparative.  
-  *Fraudes et risques*  
   Cartographie des fraudes par service et par région.  
-  *Recommandations stratégiques*  
   Actions proposées pour améliorer la rentabilité et réduire les risques.

---

## ⚙️ Technologies & outils utilisés
| Outil | Utilisation |

| **Power BI** | Visualisation et storytelling |
| **CSV** | Préparation et nettoyage des données |
| **Power Query** | Transformation et modélisation des données |
| **DAX** | Calcul des mesures et indicateurs personnalisés |
| **GitHub** | Versionning et documentation du projet |
| **ChatGPT**| Pour le scraping des donnees

---

## 📈 Exemples d'indicateurs DAX

```DAX
-- Chiffre d'affaires total
CA_Total = SUM(Transactions[Montant])

-- Taux de fraude
Taux_Fraude = DIVIDE(SUM(Fraudes[Montant]), SUM(Transactions[Montant]))

-- Budget utilisé (%)
Taux_Utilisation_Budget = DIVIDE(SUM(Depenses[Montant]), SUM(Budget_Departements[Budget])) * 100
