# test_flutter_firebase

Ceci est l'explication détaillée de la configuration à faire pour
obetnir une application Flutter fonctionnant avec Firebase.

Mis à jour en nomvembre 2022

## Firebase, création de compte

- dans un navigateur ouvrir https://firebase.google.com/
- si nécessaire, se créer un compte
- se connecter

## Firebase, création du projet et des applications

- dans un navigateur, entrez dans la console de firebase
- créer un nouveau projet Firebase, vous n'avez pas besoin de Google Analytics 
- ajouter une application IOS dans le projet créé, vous pouvez télécharger le fichier .plist mais les étapes de configuration de code ne sont pas nécessaires. Nous les ferons dans le projet Flutter à venir
- ajouter une application Android dans le projet créé, vous pouvez télécharger le fichier .plist mais les étapes de configuration de code ne sont pas nécessaires. Nous les ferons dans le projet Flutter à venir
- vous n'avez pas à suivre les étapes qui vous propose de changer le code

## Création du projet de code et repo

- créer un nouveau repo pour le projet flutter sur Github, choisir un repo privé et respecter le nom demandé dans le cours.
- cloner ce nouveau repo sur la machine local (GitKraken ou autre)
- taper : flutter upgrade
- il s'agit de vous assurer d'avoir une version à jour de flutter pour le projet
- créer un projet flutter de base dans le dossier local du repo
- lancer votre application de base pour vérifier le fonctionnement
- FAIRE UN COMMIT
- FAIRE UN PUSH

Faire des commits régulièrement va permettre de voir ce qui change dans le projet 
pour chaque étape et également de revenir à un point fonctionnel si une étape échoue.

## installation de firebase-cli

- suivre les instructions ici
- tester en exécutant dans le terminal : firebase login

## installation de flutterfire-cli

- dans un terminal (celui de IntellijIdea ou AndroidStudio par exemple)
- taper : dart pub global activate flutterfire_cli

## configuration du projet avec flutterfire

- dans un terminal (celui de IntellijIdea ou AndroidStudio par exemple)
- se placer dans le dossier du projet flutter
- taper : flutterfire configure
- vous allez être invité à choisir le projet firebase correspondant au projet
- FAIRE UN COMMIT et au passage regarder quels fichiers ont été configurés

## ajout des composants de firebase via les librairies

L'ensemble de la documentation sur les différentes composantes se trouve ici:
https://firebase.google.com/docs/flutter/setup?platform=web#available-plugins


Vous allez maintenant ajouter plusieurs composantes de Firebase:
- dans un terminal
- depuis le dossier du projet flutter
- taper : flutter pub add firebase_core
- cela ajoute la base de la librairie
- taper : flutter pub add cloud_firestore
- il s'agit de la "base de données" de firebase
- taper : flutter pub add firebase_auth
- pour gérer l'authentification
- taper : flutter pub add firebase_storage
- pour stocker des fichiers, pour nous les images
- FINALEMENT, taper flutterfire configure
- Cette dernière commande s'assure que tout est configuré ok.
- FAIRE UN COMMIT, encore une fois pour se donner un point de retour et voir ce qui s'est passé.

## test dans le code

TODO






Video d'explications:
https://www.youtube.com/watch?v=0xbKp50F1PE
