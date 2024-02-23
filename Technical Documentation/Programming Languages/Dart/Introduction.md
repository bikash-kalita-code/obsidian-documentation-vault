Every app requires the top-level `main()` function, where execution starts. Functions that don’t explicitly return a value have the `void` return type.

### Variables
Even in [type-safe](https://dart.dev/language/type-system) Dart code, you can declare most variables without explicitly specifying their type using `var`. Thanks to type inference, these variables’ types are determined by their initial values:
```
var name = 'Voyager I';
var year = 1977;
var antennaDiameter = 3.7;
var flybyObjects = ['Jupiter', 'Saturn', 'Uranus', 'Neptune'];
var image = {
  'tags': ['saturn'],
  'url': '//path/to/saturn.jpg'
};
```

### Functions
```
int fibonacci(int n) {
  if (n == 0 || n == 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

var result = fibonacci(20);
```
A shorthand `=>` (_arrow_) syntax is handy for functions that contain a single statement. This syntax is especially useful when passing anonymous functions as arguments:
```
flybyObjects.where((name) => name.contains('turn')).forEach(print);
```

### Comments
```
  // This is a single line comment
  
  /*
   * 
   * This is a,
   *  multi-line comment
   * 
   */
```

### Imports
To access APIs defined in other libraries, use `import`.

```
// Importing core libraries
import 'dart:math';

// Importing libraries from external packages
import 'package:test/test.dart';

// Importing files
import 'path/to/my_other_file.dart';
```

### Classes
```
class Spacecraft {
  String name;
  DateTime? launchDate;
  
  // Read-only non-final property
  int? get launchYear => launchDate?.year;
  
  // Constructor with syntactic sugar for assignment of numbers
  Spacecraft(this.name, this.launchDate) {
    // Initialization code goes here
  }
  
  // Named constructor that forwards to the default one
  Spacecraft.unlaunched(String name) : this(name, null);
  
  // Method
  void describe() {
    print('Spacecraft : $name');
    // Type promotion doesn't work on getters
    var launchDate = this.launchDate;
    if(launchDate != null) {
      int years = DateTime.now().difference(launchDate).inDays ~/ 365;
      print('Launched: $launchYear ($years years ago)');
    } else {
      print('Unlaunched');
    }
  }
}

void main() {
  var voyager = Spacecraft('Voyager I', DateTime(1977, 9, 5));
  voyager.describe();

  var voyager3 = Spacecraft.unlaunched('Voyager III');
  voyager3.describe();
}
```
