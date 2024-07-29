# Projet : Application de Gestion des Tâches
Vous allez développer une application web de gestion des tâches (To-Do List) en utilisant Angular pour le frontend. Le backend est déjà créé en PHP et vous sera fourni. L'objectif est de créer une interface utilisateur permettant aux utilisateurs de gérer leurs tâches quotidiennes.
## Fonctionnalités Principales
1) Authentification des Utilisateurs
    - Les utilisateurs doivent pouvoir s'inscrire et se connecter.
    - Lors de la connexion, le backend retourne les informations de l'utilisateur et un token JWT (JSON Web Token) contenant l'ID de l'utilisateur.
2) Gestion des Tâches
    - Affichage de la liste des tâches de l'utilisateur connecté.
    - Ajout d'une nouvelle tâche.
    - Modification d'une tâche existante.
    - Suppression d'une tâche.
    - Marquer une tâche comme complétée ou non complétée.

    Note : Chaque requête relative aux tâches doit inclure le token JWT dans les en-têtes pour permettre au backend de vérifier l'authentification et d'obtenir l'ID de l'utilisateur.


## Détails de l'API Backend (en PHP)
Voici un résumé des endpoints de l'API:
1) Utilisateur
    - POST http://localhost/backend_api/?url=register : Inscription d'un nouvel utilisateur.
    - POST http://localhost/backend_api/?url=login : Connexion d'un utilisateur, retourne les informations de l'utilisateur et un token JWT.

2) Tâches
    - GET http://localhost/backend_api/?url=tasks : Récupérer toutes les tâches de l'utilisateur connecté. (Token requis)
    - POST http://localhost/backend_api/?url=add_task : Créer une nouvelle tâche. (Token requis)
    - POST http://localhost/backend_api/?url=update_task&id=id_de_la_tache : Mettre à jour une tâche existante.
    - GET http://localhost/backend_api/?url=remove_task&id=id_de_la_tache : Supprimer une tâche. (Token requis)
    - GET http://localhost/backend_api/?url=complete_task&id=id_de_la_tache : Marquer une tâche comme complétée ou non complétée.

## Structure du Projet Angular
Créez une nouvelle application Angular.
Utilisez Angular CLI pour générer les composants, services et modules nécessaires.

# Composants Principaux
1) LoginComponent : Formulaire de connexion.
2) RegisterComponent : Formulaire d'inscription.
3) TaskListComponent : Liste des tâches.
4) TaskComponent : Utiliser dans le composant TaskListComponent pour afficher les information d'une tâche.
5) TaskFormComponent : Formulaire pour ajouter/modifier une tâche.

## Services Angular
1) UserService : Service pour la gestion des utilisateurs.
2) TaskService : Service pour gérer les tâches.

## Routing
Configurez les routes pour accéder aux différents composants (login, register, task list, etc.).

## Validation des Formulaires
Implémentez une validation des formulaires (inscription, connexion, ajout/modification de tâche).

## Gestion des Tokens
Lors de la connexion, stockez le token JWT reçu dans le localStorage.
Incluez ce token dans les entêtes des requêtes HTTP pour les opérations nécessitant une authentification.