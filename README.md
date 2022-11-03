# test_flutter_firebase

Ceci est l'explication détaillée de la configuration à faire pour
obetnir une application Flutter fonctionnant avec Firebase.

Mis à jour en nomvembre 2022

## Firebase, création de compte

- dans un navigateur ouvrir https://firebase.google.com/
- si nécessaire, se créer un compte
- se connecter

## Firebase, création du projet et des applications

- dans un

## Création du projet de code et repo

- créer un nouveau repo pour le projet flutter sur Github
- cloner ce nouveau repo sur la machine local
- créer un projet flutter de base dans le dossier local du repo
- faire un commit

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
