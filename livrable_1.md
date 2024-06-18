# Introduction

Le secteur de la santé subit une transformation rapide, guidée par le potentiel des données médicales. Pour améliorer les performances et la qualité des soins, les praticiens et les administrateurs doivent accéder à des informations exploitables issues de ces données. Les informations sur l'affluence des patients, les dossiers médicaux, et la rentabilité des établissements contiennent des perspectives précieuses encore sous-utilisées.

Pour exploiter pleinement ces données, il est essentiel de développer des systèmes informatiques évolutifs capables de charger, extraire et analyser les données médicales complexes. Cela nécessite une nouvelle architecture de stockage et de traitement, notamment des infrastructures d'entreposage de données comme les datawarehouses et datamarts, pour une analyse pertinente.

Le projet Cloud Healthcare Unit (CHU) incarne cette nécessité. Le groupe CHU vise à créer une base de données pour exploiter les vastes volumes de données générées par les systèmes de gestion de soins et FTP, répondant ainsi aux besoins croissants d'analyse et de visualisation des données pour une meilleure prise de décision.

# Modélisation des différents axes d'analyse ainsi que les mesures

Dans cette partie, nous détaillerons la modélisation conceptuelle des données pour répondre aux besoins d'analyse identifiés. La modélisation se concentrera sur :

- Axes d'analyse : Identification des dimensions principales telles que le temps, les établissements, les diagnostics, les patients, et les professionnels de santé.
- Mesures : Définition des indicateurs clés de performance (KPI) comme les taux de consultation, les taux d'hospitalisation, les taux de satisfaction, et les nombres de décès.

Cette section fournira des diagrammes et des descriptions textuelles pour expliquer comment les données seront structurées pour permettre des analyses pertinentes et multi-dimensionnelles.

# Développement des jobs d'alimentation du schéma décisionnel

## Introduction à l'ETL

Le processus ETL (Extract, Transform, Load) est une méthode essentielle pour intégrer et préparer des données provenant de diverses sources pour l'analyse et la prise de décision. L'ETL comprend trois étapes principales :

- Extraction : Collecte des données brutes depuis différentes sources.
- Transformation : Nettoyage et conversion des données dans un format adapté à l'analyse.
- Chargement : Insertion des données transformées dans une base de données.

## Sources de Données

Nous allons intégrer des données provenant de multiples sources, notamment des fichiers CSV, des fichiers Excel et des bases de données PostgreSQL. Voici un aperçu des principales sources :

- Fichiers CSV:

    - Décès
    - Activité professionnel de santé
    - Établissement de santé
    - Professionnel de santé
    - Hospitalisation

- Fichiers Excel :

    - A Compléter
    
- Base de données PostgreSQL :

    - Adher
    - Consultation
    - Diagnostic
    - Laboratoire
    - Médicaments
    - Mutuelle
    - Patient
    - Prescription
    - Professionnel de santé
    - Salle
    - Spécialités
    - Date

## Outils et Technologies

Pour réaliser l'ETL, nous utiliserons Talend. Talend est une plateforme puissante et flexible permettant de créer, déployer et gérer des workflows d'ETL. Talend facilite la connexion à différentes sources de données, l'application de transformations complexes, et le chargement des données dans la base de données.

### Développement des Jobs ETL

1. Extraction

Les données seront extraites des différentes sources en utilisant des connecteurs spécifiques de Talend :

- SCV et Excel : Utilisation de composants Talend tels que tFileInputDelimited pour lire les fichiers CSV et Excel.
- PostgreSQL : Utilisation de composants comme tPostgresqlInput pour interroger les bases de données PostgreSQL.

2. Transformation

Une fois les données extraites, elles doivent être transformées pour assurer la cohérence et la qualité des informations. Les étapes de transformation incluent :

- Nettoyage des données : Suppression des doublons, gestion des valeurs manquantes, et normalisation des formats de données.
- Consolidation : Agrégation des données provenant de différentes sources pour créer des dimensions et des faits cohérents.
- Enrichissement : Ajout de nouvelles colonnes ou calculs dérivés pour améliorer l'analyse.

3. Chargement

Les données transformées seront chargées dans le datawarehouse en utilisant des composants Talend tels que tPostgresqlOutput. Les données seront stockées dans des tables dimensionnelles et des tables de faits structurées pour optimiser les requêtes analytiques. Ces tables seront précisées par la suite.

### Architecture du Datawarehouse

Le datawarehouse est structuré pour supporter une analyse efficace et rapide des données. Voici les principales composantes de cette architecture :

- Tables Dimensionnelles : Contiennent des informations de référence utilisées pour filtrer, regrouper et segmenter les données factuelles.
- Tables de Faits : Contiennent les données transactionnelles et les mesures à analyser.

## Conclusion

En utilisant Talend pour développer les jobs ETL, nous pourrons intégrer des données provenant de sources diverses, les transformer pour assurer leur qualité et leur cohérence, et les charger dans une base de données structuré pour l'analyse. Ce processus permettra de répondre aux besoins d'analyse définis par les utilisateurs, tout en garantissant des performances optimales et une sécurité accrue des données.

# Description de l'architecture de la base de données

Cette section présentera l'architecture globale de la base de données, en mettant en avant les éléments suivants :

- Schéma de la base de données : Structure des tables, des relations entre elles, et des index utilisés pour optimiser les requêtes.
- Technologies : Outils et plateformes choisis pour le stockage, la gestion et l'analyse des données (bases de données, systèmes de gestion de flux de données, etc.).
- Sécurité et Gouvernance : Mesures mises en place pour protéger la confidentialité des données médicales et assurer la conformité avec les réglementations en vigueur.

Des diagrammes d'architecture, des descriptions techniques détaillées et des justifications des choix technologiques seront fournis pour illustrer comment la base de données est conçu pour être évolutif, sécurisé et performant.