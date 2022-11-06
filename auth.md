# prerequis

Avoir fait le premier fichier de configuration. S'assurer d'avoir réinistaller firebase-cli et flutterfire-cli.

## installation de la librairie

- si ce n'est pas déjà fait (il faut regarder dans le pubspec pour voir s'il y a déjà la librairie auth de firebase)
- dans un terminal
- depuis le dossier du projet flutter
- taper : flutter pub add firebase_auth
- COMMIT PUSH

## code de détection du status de login

- dans votre IDE
- dans le fichier dart de votre ecran principal
- dans la fonction initState
- ajouter le code suivant (la doc de référence se trouve ici : https://firebase.google.com/docs/auth/flutter/start)

```
FirebaseAuth.instance
  .authStateChanges()
  .listen((User? user) {
    if (user == null) {
      print('User is currently signed out!');
    } else {
      print('User is signed in! ' + user.email!);
    }
  });
  ...  reste de votre initState
```

- relancer votre application
- pour l'instant vous devriez toujours voir que c'est "currently signed out!"
- COMMIT PUSH

## ajout de google sign_in

- dans un navigateur 
- aller dans la console firebase dans votre projet
- dans le volet authentication, cherche les méthodes de sign in
- activer le sign in via google
- dans un navigateur aller à https://pub.dev/packages/google_sign_in
- copier la dépendance google_sign_in avec la bonne version dans votre pubspec.yaml
- taper : flutterfire configure

```
Future<UserCredential> signInWithGoogle() async {
  // Trigger the authentication flow
  final GoogleSignInAccount? googleUser = await GoogleSignIn().signIn();

  // Obtain the auth details from the request
  final GoogleSignInAuthentication? googleAuth = await googleUser?.authentication;

  // Create a new credential
  final credential = GoogleAuthProvider.credential(
    accessToken: googleAuth?.accessToken,
    idToken: googleAuth?.idToken,
  );

  // Once signed in, return the UserCredential
  return await FirebaseAuth.instance.signInWithCredential(credential);
}

```
- ajouter un bouton pour appeler la méthode signInWithGoogle
- relancer votre application
- déclencher le bouton pour appeler la méthode
- on vous demandera de vous connecter sur Google 
- vous devriez avoir un message "PlatformException(sign_in_failed, com.google.android.gms.common.api.ApiException: 10: , null, null)"
- pour le sign in Google, il faut ajouter la signature SHA1 de l'application dans notre application Android
- avec Android Studio ouvrir le dossier android dans votre projet flutter
- view puis tool windows puis gradle
- dans la vue gradle, cliquer sur l'éléphant
- taper : gradle signinReport dans le dialogue qui apparait
- copier la valeur du SHA1 de la tache google_sign_in_android
- dans un navigateur
- dans la console firebase sélectionner l'application Android
- trouver le bouton "ajouter une empreinte"
- copier la valeur du SHA1 et valider
- relancer l'application et tenter une connexion, tout devrait fonctionner. 

## ajout d'un signout

- dans votre écran principal,
- ajouter un bouton qui déconnecte, suit un exemple
```
MaterialButton(
  onPressed: () async {
    await GoogleSignIn().signOut();
    await FirebaseAuth.instance.signOut();
  },
  child: Text("signout"),
),
```
- relancer l'application
- On devrait pouoir se connecter et se déconnecter et l'état se lit dans la console
- COMMIT PUSH
