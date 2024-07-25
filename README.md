# Dart-Basics


# Dart Guide

## Introduction to Dart

Dart is a client-optimized programming language for apps on multiple platforms. It is developed by Google and is used to build mobile, desktop, server, and web applications.

### Why Dart?

- **Easy to Learn**: Dart's syntax is clean and intuitive, making it easy for beginners to pick up.
- **High Performance**: Dart is compiled to ARM and x64 machine code, providing high performance for your applications.
- **Versatile**: Dart can be used for both frontend and backend development, making it a versatile choice for full-stack development.

## Getting Started

### Installing Dart

1. **Windows**:
    - Download the Dart SDK from the official [Dart website](https://dart.dev/get-dart).
    - Extract the contents to a desired location.
    - Add the Dart SDK to your PATH.

2. **MacOS**:
    - Install Dart using Homebrew:
      ```bash
      brew tap dart-lang/dart
      brew install dart
      ```

3. **Linux**:
    - Install Dart using the apt package manager:
      ```bash
      sudo apt update
      sudo apt install apt-transport-https
      sudo sh -c 'wget -qO- https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -'
      sudo sh -c 'wget -qO- https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list'
      sudo apt update
      sudo apt install dart
      ```

### Your First Dart Program

Create a new file called `hello.dart` and add the following code:

```dart
void main() {
  print('Hello, Dart!');
}
```

Run the program using the Dart VM:

```bash
dart hello.dart
```

## Dart Basics

### Variables and Data Types

Dart is a statically typed language, which means you need to declare the type of a variable when you create it. However, Dart also supports type inference, so you can use the `var` keyword to let Dart infer the type.

```dart
void main() {
  // Explicitly typed variables
  int a = 10;
  double b = 10.5;
  String c = 'Hello, Dart';
  bool d = true;

  // Type inference
  var e = 20; // Dart infers that e is an int
  var f = 'Dart is great'; // Dart infers that f is a String
}
```

### Control Flow Statements

Dart supports common control flow statements like `if`, `else`, `for`, `while`, and `switch`.

```dart
void main() {
  int number = 5;

  // If-else statement
  if (number > 0) {
    print('The number is positive.');
  } else {
    print('The number is negative.');
  }

  // For loop
  for (int i = 0; i < 5; i++) {
    print(i);
  }

  // While loop
  int j = 0;
  while (j < 5) {
    print(j);
    j++;
  }

  // Switch statement
  switch (number) {
    case 0:
      print('The number is zero.');
      break;
    case 1:
      print('The number is one.');
      break;
    default:
      print('The number is neither zero nor one.');
  }
}
```

### Functions

Functions in Dart are first-class objects, which means they can be assigned to variables or passed as arguments to other functions.

```dart
void main() {
  // Simple function
  void sayHello() {
    print('Hello, Dart!');
  }

  // Function with parameters
  void printNumber(int number) {
    print('The number is $number');
  }

  // Function with return type
  int add(int a, int b) {
    return a + b;
  }

  // Calling functions
  sayHello();
  printNumber(10);
  int sum = add(5, 3);
  print('Sum: $sum');
}
```

### Classes and Objects

Dart is an object-oriented language with classes and objects.

```dart
void main() {
  var person = Person('John', 30);
  person.sayHello();
}

class Person {
  String name;
  int age;

  // Constructor
  Person(this.name, this.age);

  // Method
  void sayHello() {
    print('Hello, my name is $name and I am $age years old.');
  }
}
```

### Asynchronous Programming

Dart supports asynchronous programming using `async` and `await` keywords.

```dart
void main() async {
  print('Fetching data...');
  var data = await fetchData();
  print('Data: $data');
}

Future<String> fetchData() async {
  // Simulate a network request
  await Future.delayed(Duration(seconds: 2));
  return 'Hello from the network';
}
```

## Advanced Dart

### Generics

Generics allow you to create classes and methods that can work with any data type.

```dart
void main() {
  var list = List<int>();
  list.add(1);
  list.add(2);
  print(list);
}

class List<T> {
  List<T> _items = [];

  void add(T item) {
    _items.add(item);
  }

  T operator [](int index) => _items[index];

  int get length => _items.length;
}
```

### Mixins

Mixins are a way of reusing a class’s code in multiple class hierarchies.

```dart
void main() {
  var cat = Cat();
  cat.walk();
  cat.meow();
}

class Animal {
  void walk() {
    print('Walking...');
  }
}

mixin Meowing {
  void meow() {
    print('Meowing...');
  }
}

class Cat extends Animal with Meowing {}
```

### Futures and Streams

Futures and Streams are used for handling asynchronous programming.

```dart
void main() {
  print('Fetching data...');
  fetchData().then((data) {
    print('Data: $data');
  });

  print('Fetching stream data...');
  fetchStreamData().listen((data) {
    print('Stream Data: $data');
  });
}

Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Hello from the network';
}

Stream<int> fetchStreamData() async* {
  for (int i = 0; i < 5; i++) {
    await Future.delayed(Duration(seconds: 1));
    yield i;
  }
}
```

## Conclusion

Dart is a powerful and versatile programming language that can be used for various types of applications. With its clean syntax and robust features, it is an excellent choice for both beginners and experienced developers. Happy coding!
