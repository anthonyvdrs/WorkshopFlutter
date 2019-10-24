## Installation de Flutter

1. Télécharger [les SDK de Flutter](https://storage.googleapis.com/flutter_infra/releases/stable/windows/flutter_windows_v1.9.1+hotfix.4-stable.zip)
2. Extrayez le fichier zip et placez le fichier contenu dans l'emplacement d'installation souhaité pour le kit de développement Flutter SDK (par exemple, C: \ src \ flutter; n'installez pas Flutter dans un répertoire tel que C: \ Program Files \ qui requiert des privilèges élevés).
3. Allez dans :
   ```sh
   MODIFIER LES VARIABLES D'ENVIRONNEMENT SYSTEME
   ```
4. Cliquez sur :
   ```sh
   VARIABLE D'ENVIRONNEMENT
   ```
5. Cliquez sur :
   ```sh
    PATH
    ```
6. Ajoute le chemin de ton SDK example: 
   ```sh
   C:\Users\Anthony\Desktop\Flutter\flutter\bin
   ```
7. Redémarez le pc.
8.  Ouvrez Powershell
9.  Fait un :
    ```sh
    flutter doctor
    ```
  * Il devrait afficher quelques chose comme ça:

``` 
Doctor summary (to see all details, run flutter doctor -v):
[✓] Flutter (Channel stable, v1.9.1+hotfix.4, on Linux, locale fr_BE.UTF-8)
[✗] Android toolchain - develop for Android devices
    ✗ Unable to locate Android SDK.
      Install Android Studio from:
      https://developer.android.com/studio/index.html
      On first launch it will assist you in installing the Android SDK
      components.
      (or visit https://flutter.dev/setup/#android-setup for detailed
      instructions).
      If the Android SDK has been installed to a custom location, set
      ANDROID_HOME to that location.
      You may also want to add it to your PATH environment variable.

[!] Android Studio (version 3.5)
    ✗ Flutter plugin not installed; this adds Flutter specific functionality.
    ✗ Dart plugin not installed; this adds Dart specific functionality.
[✓] VS Code (version 1.38.1)
[!] Connected device
    ! No devices available

! Doctor found issues in 3 categories.
```
## Installation de Android Studio

1. * Télécharger [Android Studio](https://developer.android.com/studio).

2. Installer avec les parametres par défaut, une fois installé, vous pouvez quitter AS.

3. Ouvrez VsCode et installez l'extension Flutter.

4. Dans VsCode, faites F1 et Flutter: New Project.

5. Localisez les SDK de flutter avec l'extension (sélectionner le dossier flutter dans Documents/FlutterSetup)

6. Accepter toutes les conditions d'utilisation sans les lire

```sh
flutter doctor --android-licenses
```

6. Un petit 'flutter doctor' dans le terminal pour vérifier si tout fonctionne, il devrait indiquer qu'il manque le plugin Flutter et Dart dans Android Studio mais comme on travaille dans VsCode, c'est pas très grave.

7. Pour ajouter un device, il faut activer le Déboguage USB dans votre smartphone.

8. N'oubliez pas de prendre un cable le jour du Workshop.

***
#### Suite

##### [Créer un nouveau projet dans VS Code](nouveau_projet.md)