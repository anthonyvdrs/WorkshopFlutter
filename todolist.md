Pour commencer on va importer le package material, qui va nous permettre d'utiliser un paquet de widgets déjà construits.

```dart
import 'package:flutter/material.dart';
``` 

Le code exécuté en Dart commence toujours par la fonction main(), nous allons donc la créer et éxecuter le component qui contient notre application.
En Flutter tous les components sont appelés "Widgets".

```dart
void main() => runApp(new MyApp());
``` 

Nous allons créer un Widget stateless qui sera le container de notre app.

```dart
class MyApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
        return Container();
    }
}
``` 
Et dedans nous allons utiliser le Widget material "MaterialApp()".
On va pouvoir y mettre le titre de notre app et créer une structure basique (un Scaffold).

```dart
class MyApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
        return new MaterialApp(
            title: 'Todo List',
            home: Scaffold(

            ),
        );
    }
}
``` 

Dans ce Scafold, on va mettre une app bar et un bouton flottant.
* L'app bar contiendra lui meme le Widget Text pour définir le titre.

```dart
appBar: AppBar(title: Text('Todo List')),
```

On va également mettre un body qui va render le Widget ToDoList() que nous allons créer nous même.

```dart
body: TodoList(),
```

Voici notre Widget stateful 
```dart
class TodoList extends StatefulWidget {
  @override
  _TodoListState createState() => _TodoListState();
}

class _TodoListState extends State<TodoList> {
  @override
  Widget build(BuildContext context) {
    return Container();
  }
}
```

Chaque tâche sera une instance de la class Todo avec un constructeur pour le titre et l'état "isDone".
* isDone est par défaut false 

```dart
class Todo {
  Todo({this.title, this.isDone = false});

  String title;
  bool isDone;
}
```

Nous allons mettre en place la liste des tâches dans le state de notre Widget TodoList

```dart
class _TodoListState extends State<TodoList> {

  List<Todo> todos = [];

  @override
  Widget build(BuildContext context) {
    return Container();
  }
}
```
Et nous allons utiliser le Widget "ListView" qui permet d'afficher tous les enfants d'un widget les uns après les autres et donne aussi la possibilité de les scroller

```dart
class _TodoListState extends State<TodoList> {

  List<Todo> todos = [];

  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      itemBuilder: _buildItem,
      itemCount: todos.length,
    );
  }
}
```

Il faut maintenant créer la fonction _buildItem() qui sera exécutée à chaque fois qui faudra render une nouvelle tâche.

* _buildItem() va retourner le widget CheckboxListTitle(), comme son nom l'indique sert à créer un élément de type checkbox.
```dart
class _TodoListState extends State<TodoList> {

  List<Todo> todos = [];

  Widget _buildItem(BuildContext context, int index) {
    final todo = todos[index];
    return CheckboxListTile(
      value: todo.isDone,
      title: Text(todo.title),
    );
  }

  @override
  Widget build(BuildContext context) {
    return ListView.builder(
      itemBuilder: _buildItem,
      itemCount: todos.length,
    );
  }
}
```

On doit maintenant gerer l'interaction avec les checkbox.

```dart
return CheckboxListTile(
  value: todo.isDone,
  title: Text(todo.title),
  onChanged: (bool isChecked) {
    _toggleTodo(todo, isChecked);
  },
);
```
Et render a chaque changement d'état

```dart
class _TodoListState extends State<TodoList> {
  List<Todo> todos = [];
  
  _toggleTodo(Todo todo, bool isChecked) {
    todo.isDone = isChecked;
  }
```



