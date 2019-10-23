### Amélioratons


##### Alors nous allons essayer de changer quelque petites choses dans l'application.
***
Pour commencer on va retiter la barre de débug qui se trouve en haut de l'app

```sh
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Todo List',
      home: TodoListScreen(),
      debugShowCheckedModeBanner: false,   // AJOUTER CECI
    );
  }
}
```

Ensuite nous allons changer la couler du thème

```sh
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Todo List',
      theme: ThemeData( // Ajouter CECI début
        primarySwatch: Colors.green,
      ), // Fin
      home: TodoListScreen(),
      debugShowCheckedModeBanner: false,
    );
  }
}
```

***
##### Et pour finir nous allons changer le logo du launcher de l'application:
 * aller dans le fichier:
 ```.\todo\android\app\src\main\res```
  et supprimez les fichiers qui commencent par mipmap
* puis rendez-vous sur le site: [https://appicon.co/](https://appicon.co/)
* Glisser le logo que vous souhaitez pour votre application.
* Activez uniquement pour android et téléchargez.
* Dézippé et collé l'intérieur du fichieé dans le dossier ```res```
 * Refaite un flutter run

### Voila le worshop est terminé.