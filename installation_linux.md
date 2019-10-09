## Prérequis

* Télécharger [les SDK de Flutter](https://storage.googleapis.com/flutter_infra/releases/stable/linux/flutter_linux_v1.9.1+hotfix.4-stable.tar.xz)
* Télécharger [Android Studio](https://dl.google.com/dl/android/studio/ide-zips/3.5.1.0/android-studio-ide-191.5900203-linux.tar.gz)
* 3 GO d'espace libre

## Installation de Flutter

1. Installer Java.

```sh
sudo apt update
sudo apt upgrade
sudo apt install openjdk-11-jre-headless
```

2. Créer un dossier pour l'installation de Flutter et Android Studio.

```sh
cd ~/Documents/
mkdir FlutterSetup
cd /FlutterSetup
tar xf ~/Téléchargements/flutter_linux_v1.9.1+hotfix.4-stable.tar.xz
tar xf ~/Téléchargements/android-studio-ide-191.5900203-linux.tar.gz
```

3. Ajouter Flutter au PATH.

```sh
sudo nano ~/.bashrc
```

 * Ajouter la ligne suivante à la FIN du fichier et ensuite **redémarrer le PC**

 ```sh
 export PATH="~/Documents/FlutterSetup/flutter/bin:$PATH"
 ```

4. Tester l'installation

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

1. Lancer l'installateur

```sh
~/Documents/FlutterSetup/android-studio/bin/studio.sh
```

2. Installer avec les parametres par défaut, une fois installé, vous pouvez quitter AS.

3. Ouvrez VsCode et installez l'extension Flutter.

4. Dans VsCode, faites F1 et flutter create project.

5. Localisez les SDK de flutter avec l'extension (sélectionner le dossier flutter dans Documents/FlutterSetup)

6. Accepter toutes les conditions d'utilisation sans les lire

```sh
flutter doctor --android-licenses
```

6. Un petit 'flutter doctor' dans le terminal pour vérifier si tout fonctionne, il devrait indiquer qu'il manque le plugin Flutter et Dart dans Android Studio mais comme on travaille dans VsCode, c'est pas très grave.

7. Pour ajouter un device, il faut activer le Déboguage USB dans votre smartphone.

8. N'oubliez pas de prendre un cable le jour du Workshop.
