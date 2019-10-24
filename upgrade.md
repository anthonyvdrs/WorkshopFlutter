### Amélioratons


##### Alors nous allons essayer de changer quelque petites choses dans l'application.
***
Pour commencer on va retiter la barre de débug qui se trouve en haut de l'app

```dart
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

```dart
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
Maintenant nous allons centrer le titre.

```dart
 @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Todo List'),
      centerTitle: true, // AJOUTER CECI
      ),
      body: TodoList(
        todos: todos,
        onTodoToggle: _toggleTodo,
      ),
      floatingActionButton: FloatingActionButton(
        child: Icon(Icons.add),
        onPressed: _addTodo,
      ),
    );
  }
}

```

Nous allons rajouter une sidebar où il y aura les informations de connexions, liens vers autre page, etc...

```dart
@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Todo List'),
      ),
      drawer: new Drawer( // AJOUTER CECI Début
        child: ListView(
          children: <Widget>[
            new UserAccountsDrawerHeader(
              accountName: new Text('nom'),
              accountEmail: new Text('mail@becode.com'),
              currentAccountPicture: new CircleAvatar(
                backgroundImage: new NetworkImage('https://i.pravatar.cc/300'),
              ),
            )
          ],
        ),
      ), // Fin
      body: TodoList(
        todos: todos,
        onTodoToggle: _toggleTodo,
      ),
      floatingActionButton: FloatingActionButton(
        child: Icon(Icons.add),
        onPressed: _addTodo,
      ),
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

### Voila le workshop est terminé.

#### [Idées d'apps](./example.md)