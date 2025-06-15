🌟 Vue d'ensemble
Ce projet est une API RESTful robuste développée en J2EE, conçue pour gérer les opérations bancaires, les informations clients et la gestion des comptes. Elle expose un ensemble de services permettant à des applications clientes (front-end, applications mobiles, autres services) d'interagir avec le système bancaire.

📦 Structure du Projet
Le projet suit une structure de projet Maven standard pour les applications J2EE, en mettant l'accent sur la séparation des préoccupations et une architecture en couches pour l'API.
<img width="272" alt="image" src="https://github.com/user-attachments/assets/6b01f53b-30c9-4566-b81f-222cc3789a1d" />
<img width="299" alt="image" src="https://github.com/user-attachments/assets/7048bdb4-691d-42dc-9142-b6b6f2762dd6" />
<img width="290" alt="image" src="https://github.com/user-attachments/assets/23b8aa9e-ae38-43a1-b8b0-b0e28fee1c6f" />


🛠️ Technologies Utilisées
Ce projet back-end est développé en Java et utilise un ensemble de frameworks et de bibliothèques robustes pour garantir une architecture solide et des performances optimales.

Java Development Kit (JDK) : Version 17
Spring Boot : Version 3.4.5
Spring Boot Starter Data JPA : Pour une intégration simplifiée avec les technologies de persistance de données (JPA/Hibernate).
Spring Boot Starter Web : Pour la création d'applications web et d'API RESTful.
Spring Boot Starter Test : Pour faciliter les tests unitaires et d'intégration au sein de l'environnement Spring.
Maven : Pour l'automatisation de la construction, la gestion des dépendances et la gestion du cycle de vie du projet.
MySQL Connector/J : Version 8.3.0 - Pilote JDBC pour la connectivité avec les bases de données MySQL.
H2 Database : Base de données relationnelle en mémoire, utilisée principalement pour les tests ou le développement local rapide sans dépendance à une base de données externe.
Lombok : Version 1.18.30 - Une bibliothèque Java qui réduit le code "boilerplate" (répétitif) en générant automatiquement des méthodes comme les getters, setters, constructeurs, etc., via des annotations.
Hibernate : (Implicitement utilisé via Spring Data JPA) - Implémentation du standard JPA pour le mappage objet-relationnel.
voici une partie de pom.xml :
<img width="563" alt="image" src="https://github.com/user-attachments/assets/f6d226a7-e2b1-4cfe-85d7-0a7ff34ead3a" />


🏗️ Architecture du Projet
Le projet suit une architecture en couches (n-tiers), une approche courante et recommandée pour les applications d'entreprise. Cette architecture favorise la séparation des préoccupations (Separation of Concerns), rendant le code plus modulaire, maintenable et testable.

Voici les principales couches et composants du back-end :

1. Couche de Présentation / Web (web)
   Responsabilité : Point d'entrée des requêtes API. Reçoit les requêtes HTTP, les valide (superficiellement) et délègue le traitement à la couche de service. Elle est responsable de la sérialisation des objets métier en réponses JSON/XML pour le client.
<img width="575" alt="image" src="https://github.com/user-attachments/assets/b8d7143f-7da0-489f-92bf-fe75fc654043" />

2. Couche de Service / Logique Métier (services)
   Responsabilité : Contient la logique métier principale de l'application. Elle orchestre les opérations, effectue les validations complexes, gère les transactions et interagit avec la couche d'accès aux données. C'est le cœur de l'application où les règles spécifiques du domaine sont implémentées.
   exemple de l'interface service :
   <img width="592" alt="image" src="https://github.com/user-attachments/assets/c5487d5d-141e-4b7e-bf47-a58a8751a233" />
   Son implementation:
   <img width="548" alt="image" src="https://github.com/user-attachments/assets/526b5652-01a0-43b2-bbc2-ef5a5a6b823d" />

3. Couche d'Accès aux Données / Persistance (repositories, entities)
   Responsabilité : Gère l'interaction directe avec la base de données. Elle s'occupe des opérations CRUD (Create, Read, Update, Delete) et de la cartographie des objets Java vers les tables de la base de données.
<img width="578" alt="image" src="https://github.com/user-attachments/assets/a79d8ec2-f630-4a9d-bb95-5ba842e2562f" />
<img width="424" alt="image" src="https://github.com/user-attachments/assets/367ec69f-121a-4986-ab60-f12ce2b50791" />

4. Couche de Transfert de Données (dtos, mappers)
   Responsabilité : Assure un transfert de données efficace et découplé entre les différentes couches de l'application, et surtout entre l'API et les clients.
   <img width="452" alt="image" src="https://github.com/user-attachments/assets/c018773d-6e67-41b3-aa47-455b1978526e" />
   <img width="571" alt="image" src="https://github.com/user-attachments/assets/aa5d5dcf-d292-4bc8-904f-9a3d62a97098" />
   
5. Composants Transversaux (enums, exceptions)
   Responsabilité : Fournissent des fonctionnalités transversales utilisées dans plusieurs couches de l'application.
   <img width="286" alt="image" src="https://github.com/user-attachments/assets/18050ca8-fb13-4ea5-8944-eb110c83f789" />
   <img width="527" alt="image" src="https://github.com/user-attachments/assets/abd00c87-ba29-44dd-8fad-a0c0caa569ab" />




