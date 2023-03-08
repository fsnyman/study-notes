# Dart Basics

## Dart Features
| Feature | Description |
|-|-|
| Object Oriented | Can structure our code and data using classes |
| Statically Typed | Variable types are known at compile time, which makes code more stable/safe |
| C Style Syntax | Similar to Java|

### DartPad
DartPad is a web-based tool that allows you to write, run, and share Dart code directly in your browser. It provides a simple and convenient way to test and compile your code without requiring any local development environment setup.
[Link to DartPad](https://dartpad.dev/)

## Dart Fundamentals
### The main method
A dart program is only valid if it contains a main method (unlike Python). This is the entry point into the program. 
``` Dart
// A basic IO program with some logic in Dart
import 'dart:io';

void main() {
  print('Enter your name');
  var usrIn = stdin.readLineSync();
  print(usrIn == 'Francois' ? 'You are hired $usrIn!' : 'Hi $usrIn');
}
```

### Variable Basics

|*Variable Type*|*Variable Name*|*Assignment*|*String literal*|*Terminator*|
|-|-|-|-|-|
|String|name|=|'Francois'|;|

#### Variable Naming Conventions and Rules
It is convention to use **camelCase** when naming variables in Dart. In other words, the first letter in the name of a variable is lowercase and each successive word is capitalised. 

##### Valid variable names can contain
- Upper and lower case letters
- Numbers (not the first character)
- Inderscore _ 

#### Built-in Types of Variables

|*Variable Type*|*Use*|*Example*|
|-|-|-|
|int|Whole numbers up to 64-bit precision|int varName = 1;
|double|64-bit floating point number, double the precision of 32-bit floating point numbers|double varName = 1.0;|
|bool|true or false value only (note the lowercase)|bool varName = true;|
|String|A string of characters|String varName = 'String Value';|

### Basic String Operations
#### String Concatenation
##### String Concatenation with '+'

Use '+' to concatenate many variables and/or Strings into one. 

``` Dart
void main() {
  String concatString1 = 'Hallo ';
  String concatString2 = 'Francois ';
  String concatString3 = 'Snyman';
  String finalVar =
  concatString1 + concatString2 + concatString3 + ', how are you?';
  print(finalVar);
  print(finalVar + ', I hope you are well');
}
``` 


##### String Interpolation with '$'
- Add variables into a string with $varName
- Use {varName}string to remove the space between the variable and the subsequent String
- Inject logic when interpolating with ${logic} 

```Dart
void main() {
  String name = 'Bob';
  int age = 70;
  bool isAwesome = true;
  double height = 1.88;
  print(
      'Hello $name, next year you will be ${age + 1} years old, you are ${height}m tall, with awesome status: $isAwesome');
}```

#### String Escaping
Use the escape character "\" in front of a special character to indicate that the special character is not so special and actually part of the String.
```Dart
void main() {
  print('Hello, I\'m Francois');
  print('Use \\n to break to a new line'); 
  // without double \ the \n will break the line
  print('I will work for \$0 per hour just to get experience');
  // without \$ the compiler will look for a variable called 0
  }
/* 
Output:
Hello, I'm Francois
Use \n to print a new line
I will work for $0 per hour just to get experience
```

Use raw strings to indicate that there are no special characters in the string. 
```Dart
void main() {
  print(r'Use \n to print a new line');
  print(r'I will work for $0 per hour just to get experience');
}
/*
Output:
Use \n to print a new line
I will work for $0 per hour just to get experience
```
Note that this technique does not work to escape the ' character. Just use double quotes instead E.g. " I'm ".

#### Multi Line Strings
Use \n to break to a new line in a string.
Use 3x` before and after the string to break the string as you write it in the code. 
```Dart
void main() {
  print('''Use \\n to print a new line, and remember,
I will work for \$0 per hour just to get experience.
See how the line breaks without the use of \\n?''');
}
/*
Output:
Use \n to print a new line, and remember,
I will work for $0 per hour just to get experience.
See how the line breaks without the use of \n?
```

#### String Case
- Use object.toUpperCase() method to output an uppercase version of the variable object.
- Use object.toLowerCase() method to output a lowercase version of the variable object.

>These methods can be used with both string variables (name.toUpperCase()) and string literals ('francois'.toUpperCase())

```Dart
void main() {
  // assign variables
  String name = 'Francois';
  String surname = 'Snyman';
  // print in upper case
  print('${name.toUpperCase()} ${surname.toUpperCase()}');
  // print in lower case
  print('${name.toLowerCase()} ${surname.toLowerCase()}');
  // print first letter of name and surname in upper case
  print('${name[0].toUpperCase()} ${surname[0].toUpperCase()}${surname.substring(1).toLowerCase()}');
}
/*
Output:
FRANCOIS SNYMAN
francois snyman
F Snyman
```

#### Find and Replacing Strings
##### The .contains method
Returns true if the String is found and false if not. 
```Dart
void main() {
  String name = 'Francois Snyman';
  print(name.contains('Snyman')); // true
  print(name.contains('Bob')); // false
}
```

##### The .replaceAll method
Used to replace a string with another string

```Dart
void main() {
  String name = 'Francois Snyman';
  String newName = name.replaceAll('Snyman', 'Smith');
  print(name); // Francois Snyman
  print(newName); // Francois Smith
}
```

##### Some more string conversion methods
1.  `length`: Returns the number of characters in a string.
2.  `isEmpty`: Returns true if the string is empty.
3.  `toLowerCase`: Converts the string to lowercase.
4.  `toUpperCase`: Converts the string to uppercase.
5.  `trim`: Removes whitespace from the beginning and end of a string.
6.  **`substring`: Extracts a substring of the original string.**
7.  `indexOf`: Returns the index of the first occurrence of a substring.
8.  `split`: Splits the string into a list of substrings based on a delimiter.
9.  `startsWith`: Returns true if the string starts with a specific substring.
10.  `endsWith`: Returns true if the string ends with a specific substring.
11. `replaceAll`: Replaces all occurrences of a substring with another string.
12. `replaceFirst`: Replaces the first occurrence of a substring with another string.
13.  `replaceRange`: Replaces a range of characters in the string with another string.
14.  `contains`: Returns true if the string contains a specified substring.
15.  `compareTo`: Compares two strings lexicographically.
16.  `codeUnits`: Returns a list of the Unicode code points in the string.
17.  `endsWith`: Returns true if the string ends with a specified suffix.
18.  `padLeft`: Pads the string with a specified character on the left until it reaches a certain length.
19.  `padRight`: Pads the string with a specified character on the right until it reaches a certain length.
20.  `substringAfter`: Returns the substring after a specified delimiter.
21. ...

### Conversions Between Types
Keep the following in mind when converting between types:
- Because Dart is a strongly-typed language, String variables and number variables can't be assigned to each other directly. Additional methods or functions are required to convert them to each other. 
- Only numerical String values can be parsed into ints or doubles. You need error handling to catch any errors when converting from Strings to ints or doubles.
- You cannot assign an int directly to a double, use the toDouble method for this.
- You can assign an integer literal (basically a number without a decimal value) to a double.
- You cannot assign a double literal (a number with a decimal value) to an integer. Which makes sense; where will the decimal value go in an integer?
- 

Some methods used to convert between types:
- toString
- toStringAsFixed
- parse 
- toDouble
- Convert double to int (and also some rounding methods for doubles)
	- **floor**
		- Returns the nearest integer value below the specified number. Please note that the results are not symmetrical for positive and negative numbers. For example: floor(2.15) returns 2, while floor(-2.15) returns -3.
	- **round**
		- Perform rounding to the specified number of decimals (and to an integer value is if this number is 0, or if the parameter is omitted). If the number is an integer type, it will be returned unchanged (as an integer), even if the number of decimals was specified and not 0. If the number is of type real, the rounding is performed to the specified decimal place. Examples: round(2.15,1) returns 2.2, round(2.15) returns 2, round(-2.15) returns -2
	- **ceil** 
		- Returns the nearest integer value above the specified number. Here there is also no symmetry for positive and negative number ranges. Example: ceil(2.15) returns 3, and ceil(-2.15) returns -2.
	- **truncate** 
		- Truncates the number to the specified number of decimal places, without rounding of any kind: trunc(2.15,1) will return 2.1, trunc(-2.15,1) returns -2.1, and trunc(2.15) returns 2.
	- toInt
		- Deletes the decimal value without any rounding and Returns an int representing the specified Number object.

```Dart
void main() {
  int age = 36;
  double hights = 1.88;

  // convert age to a string
  String ageString = age.toString();

  // convert hights to a string with only 1 decimal place
  String hightsString = hights.toStringAsFixed(1);
  print(age + 1); // 37
  print(ageString + '1'); // 361
  print(hightsString); // 1.9 Note that it was rounded up

  // convert hightString back to a double
  double hightsDouble = double.parse(hightsString);
  print(hightsDouble); // 1.9

  // convert hight to int rounding down
  int hightsIntDown = hights.toInt();
  // convert hight to int rounding
  int hightsIntRound = hights.round();
  print(hightsIntDown); // 1
  print(hightsIntRound); // 2
}
```

## Operations
### Arithmetic

| + | - | * | / | ~/ | % |
|--|--|--|--|--|--|

```Dart
void main() {
  // assign variables
  int num1 = 5;
  int num2 = 2;
  // add
  print(num1 + num2); // 7
  // subtract
  print(num1 - num2); // 3
  // multiply
  print(num1 * num2); // 10
  // divide
  print(num1 / num2); // 2.5
  // integer division
  print(num1 ~/ num2); // 2
  // modulo
  print(num1 % num2); // 1
}
```

#### Order of Operator Precedence (TBC)
1.  `()` (grouping)
2.  `[]` (list access)
3.  `.` (member access)
4.  `!`, `~`, `-` (unary operators)
5.  `*`, `/`, `%` (multiplicative operators)
6.  `+`, `-` (additive operators)
7.  `<<`, `>>` (shift operators)
8.  `>>>` (unsigned shift)
9.  `<`, `<=`, `>`, `>=` (relational operators)
10.  `==`, `!=` (equality operators)
11.  `&` (bitwise AND)
12.  `^` (bitwise XOR)
13.  `|` (bitwise OR)
14.  `&&` (logical AND)
15.  `||` (logical OR)
16.  `??` (null-aware operators)
17.  `=` (assignment operators)

### Augmented Assignment
| += | -= | \*= | \/= | ~= | %= |
|--|--|--|--|--|--|

```Dart
void main() {
  double x = 7;
  int y = 7;
  print(x += 2); // x = x + 2, x = 9.0
  print(x -= 2); // x = x - 2, x = 7.0
  print(x *= 2); // x = x * 2, x = 14.0
  print(x /= 2); // x = x / 2, x = 7.0 x must be double to use /= operator
  print(x %= 2); // y = y % 2, y = 1.0, 
  //This must not be confused with the decimal value, it is the remainder
  print(y ~/= 2); // y = y ~/ 2, y = 3, y must be int to use ~/= operator
}
```

### Increment and Decrement
| x++ | x-- | ++x | --x |
|--|--|--|--|
```Dart
void main() {
  int x = 1;
  int y = x++; //assigns y the value of x, then increments x by 1

  print('y=$y, x=$x'); // y=1, x=2
  y = ++x; //increments x by 1, then assigns y the value of x
  print('y=$y, x=$x'); // y=3, x=3

  x = 1;
  y = x--; //assigns y the value of x, then decrements x by 1
  print('y=$y, x=$x'); // y=1, x=0
  y = --x; //decrements x by 1, then assigns y the value of x
  print('y=$y, x=$x'); // y=-1, x=-1
}
```

### Relational
| == | != | >= | <= | < | > |
|--|--|--|--|--|--|

Relational operators compare two expressions and return a boolean result
```Dart
void main() {
  // assign variables
  int num1 = 5;
  int num2 = 2;
  // greater than
  print(num1 > num2); // true
  // greater than or equal to
  print(num1 >= num2); // true
  // less than
  print(num1 < num2); // false
  // less than or equal to
  print(num1 <= num2); // false
  // equal to
  print(num1 == num2); // false
  // not equal to
  print(num1 != num2); // true
}
```

Relational operators cannot compare Strings with numbers,

### Logical

| && | expr1 \|\| expr2 | !expr3 | expr1 ? expr2 : expr3 |
|--|--|--|--|
| And | Or | Not | Ternary Operator |

Logical operators can be used to combine multiple relational arguments
```Dart
void main() {
  // and
  print(5 > 2 && true); // true
  // or
  print(5 > 2 || 5 < 2); // true
  // not
  print(!(5 == 5)); // false
  // ternary operator
  print((5 > 1) ? 'Bigger than 1' : 'Smaller than 1'); // Bigger than 1
}
```


### Bitwise

| \| | & | ^ | \|= | &= | ^= | ~= |
|--|--|--|--|--|--|--|

### Shifting

| >> | << | >>= | <<= |
|--|--|--|--|

```Dart
void main() {
  // assign variables
  int num1 = 0xf0; // binary 11110000
  int num2 = 0x0f;
  // bitwise OR
  print(num1 | num2); // binary 11111111, decimal 255
  // bitwise AND
  print(num1 & num2); // binary 00000000, decimal 0
  // bitwise XOR
  print(num1 ^ num2); // binary 11111111, decimal 255
  // bitwise NOT
  print(~num1); // binary 00001111, decimal 15
  // bitwise left shift
  print(num1 << 2); // binary 1111000000, decimal 240
  // bitwise right shift
  print(num1 >> 2); // binary 00111100, decimal 60
  // bitwise right shift with zero fill
  print(num1 >>> 2); // binary 00111100, decimal 60
  // bitwise AND with NOT
  print(num1 & ~num2); // binary 11110000, decimal 240
  // bitwise OR with NOT
  print(num1 | ~num2); // binary 11111111, decimal 255
  // bitwise XOR with NOT
  print(num1 ^ ~num2); // binary 00001111, decimal 15
  // >>= operator
  num1 >>= 2;
  print(num1); // binary 00111100, decimal 60
  // <<= operator
  num1 <<= 2;
  print(num1); // binary 1111000000, decimal 240
  print(num1.toRadixString(2)); // 1111000000
  print(num1.toRadixString(16)); // f0
}
```

## Comments
// Single line comment
/// Same as single line comment
/* */ Multi line comments

## Expressions and Statements
In some languages statements and expressions are the same, but not in dart.  

In the following code:

```Dart
int x = (10 + 3) % 4;
print(x);
```

### Expressions
- Hold a value at runtime (can be assigned to a variable)
- 10, 3, 4 and the entire "(10 + 3) % 4" are all expressions that can be assigned to a variable.

#### Statements
- Do not hold a value (and cannot be assigned to a variable)
- The entire line "int x = (10 + 3) % 4;" and "print(x);" are e


# Dart Type System 

### Static vs Dynamically Typed Languages

**Static**: Each variable and expression is explicitly declared with a specific data type and checked at compile time. Better for catching type related errors improve program reliability.

**Dynamic**: Variable or expression types are not required to be declared explicitly. The type of a variable or expression is determined at runtime, resulting in more concise and flexible code.


| Static Typing	| Dynamic Typing |
|--|--|
| C	| Python|
| Java	 | Ruby |
| Swift |	JavaScript |
| Dart	| |


### Type Inference

Variable types do not need to be declared explicitly in dart, but once a variable is inferred or declared it cannot be changed to another type of variable (like int to String).

### var, final, const, dynamic keywords
Always use const over final over var. 

#### var 
Used to infer the variable type automatically.
```Dart
void main() {
  var name = 'Francois';
  var age = 42;

  print(name.runtimeType); // Output: String
  print(age.runtimeType); // Output: int
}
```


#### final
Used to declare or infer a variable with a value that cannot be changed. Using final instead of var where possible is best practice and could increase program stability.
```Dart
void main() {
  String name = 'Francois';
  final nameUpper = name.toUpperCase();
  /*Note that this still works even though name.toUpperCase()
  will only be known at runtime*/
  final int age = 42;

  print(name.runtimeType); // Output: String
  print(name.runtimeType); // Output: String
  print(age.runtimeType); // Output: int
}
```



#### const
- Used to declare a compile-time constants. 
- Even more restrictive than final. 
	- It is only possible to declare a const with a value that is known at compile time and not a value that will only be known at runtime. 
	- In this example name.toUpperCase() will only be known at runtime and not at compile-time, so you will not be allowed to declare it as the value of a const
```Dart
void main() {
  var name = 'Francois';
  const upperName = name.toUpperCase();
```
- Very good for performance as it allows the compiler to better optimise the generated code. 



#### dynamic
- Used to opt-out of type safety
- Useful in cases where variables need to change type like when working with JSON data. 
- Should be used as a last resort. Type safety is there to make code safer and should be used. 
```Dart
void main() {
  dynamic name = 'Francois';
  
  name = 42;
  print(name.runtimeType); // Output: int
  
  name = true;
  print(name.runtimeType); // Output: bool
}
```


# Control Flow
## if / else if / else

```Dart
void main() {
  const age = 25;
  if (age < 18) {
    print('You are a minor.');
  } else if (age < 21) {
    print('You are a young adult.');
  } else {
    print('You are an adult.');
  }
}
```

## while loops
while (boolean) {}

```Dart
var i = 0;
  while (i < 5) {
    print('i = $i');
    i++;

i = 0;
  do {
    print('i = $i');
    i++;
  } while (i < 5);
  }```

## for loops
for (initialise variable; exit condition, increment/decrement statement) {}

```Dart
for (var i = 0; i < 5; i++) {
    print('i = $i');
  }```
  *you can also loop through collections with a for loop, but more on that under the collections section*

## break and continue
**break**: breaks out of the current loop without executing the rest of the code in the loop.
**continue**: does not break out of the loop, but continues to the next iteration of the loop skipping the remaining code in the loop.

```Dart
//--------------------- break example ---------------------
import 'dart:math';
import 'dart:io';

void main() {
  //generate a random number between 1 and 10
  String randomNumber = (Random().nextInt(9) + 1).toString();
  //loop indefinitely
  while (true) {
    print('Guess a number from 1 to 10:');
    String input = (stdin.readLineSync()).toString();
  //if the guess is correct, use break to escape the loop  
    if (input == randomNumber) {
      print('You win! It is $randomNumber!!');
      break;
  //if the guess was wrong, taunt the user
    } else {
      print('You lose! You will never escape! Try again.');
    }
  }
}
```

```Dart
//--------------------- continue example ---------------------
import 'dart:math';

void main() {
  int blackSheep = (Random().nextInt(14) + 1);
  print('The black sheep is number $blackSheep');
  for (int kidsInClass = 1; kidsInClass <= 15; kidsInClass++) {
    if (kidsInClass == blackSheep) {
      continue;
      //now the black sheep in the class does not get a sweety
    }
    print('Here\'s a sweety for you kid number $kidsInClass');
  }
}
```

## The switch statement

Useful for known cases, even if it ends up as more code than if/else statements
*Remember to break out of each case*

```Dart
 switch (age) {
    case 18:
      print('You are 18.');
      break;
    case 21:
      print('You are 21.');
      break;
    default:
      print('You are neither 18 nor 21.');
      break;
  }```

## Enumerations

With enumerations you define a type with multiple values. It is advised to use enums if you have a set of predefined values. This will result in clearer code. Think days of the week or cards in a deck. 

```Dart
enum Medal { gold, silver, bronse, noMedal } //note no '' or ;
// if you add a , after the last value dart will 
void main() {
  const medalWon = Medal.gold;
  print(Medal.values); 
      // Output: [Medal.gold, Medal.silver, Medal.bronse, Medal.noMedal]
  print(medalWon); // Output: Medal.gold
  print(medalWon.name); // Output: gold

  switch (medalWon) {
    case Medal.gold:
      print('You won gold!');
      break;
    case Medal.silver:
      print('You won silver!');
      break;
    case Medal.bronse:
      print('You won bronse!');
      break;
    case Medal.noMedal:
      print('You won no medal!');
      break;
  }
}
```

# Collections

| | Ordered	| Unique|	Key-Value |	 Use | Iterable |
|--|--|--|--|--|--|
| List |	Yes	| No	| No	| 'list' constructor or [] | Yes |
| Set |	No TBC |	Yes|	No |  'set' constructor or {} | Yes |
| Map |	No |	Yes for keys |	Yes | 'map' constructor or {:} | 


## Lists 
**List**: A list is an ordered collection of objects in which duplicates are allowed. It is represented by the List class in Dart, and can contain objects of any type. Lists can be created using the square bracket notation, or by calling the List constructor.

 ```Dart
void main() {
  List numbers = [1, 3, 5, 7, 9];
  var answer = 0;
  for (var value in numbers) {
    answer = value + answer;
  } //for loop
  print(answer); // 25
} // main 
```

### List Methods
#### Note!:
- Some methods are not compatible with empty lists. When they are used on an empty list they will result in an error at runtime.
	- These include: .first .last

```Dart
void main() {
  List cities = ['London', 'Paris', 'New York', 'Cape Town'];
  print(
      'Cities list: $cities'); 
      //Cities list: [London, Paris, New York, Cape Town]
  print(
      'There are ${cities.length} Cities in the list'); 
      //There are 4 Cities in the list
  print(
      '\'.isNotEmpty\' output on the cities list is: ${cities.isNotEmpty}'); 
      //'.isNotEmpty' output on the cities list is: true
  print(
      '\'.isEmpty\' output on an empty list is: ${[].isEmpty}'); 
      //'.isEmpty' output on an empty list is: true
  print(
      'The first city in thelist is ${cities.first}'); 
      //The first city in thelist is London
  print(
      'The last city in the list is ${cities.last}'); 
      //The last city in the list is Cape Town
  print(
      'The second city in the list is ${cities[1]}'); 
      //The second city in the list is Paris
  
  // remove New York and add Lisbon in its place
  cities.removeAt(2);
  print(cities); //[London, Paris, Cape Town]
  cities.insert(2, 'Lisbon');
  print(cities); //[London, Paris, Lisbon, Cape Town]
  cities.clear();
  print('Cities list empty: ${cities.isEmpty}'); 
  //Cities list empty: true
  cities = ['London', 'Paris', 'New York', 'Cape Town'];
  print(
      'Is Lisbon in the list?: ${cities.contains('Lisbon')}'); 
      //Is Lisbon in the list?: false
  print(
      'Paris is in position ${cities.indexOf('Paris') + 1} in the city list'); 
      //Paris is in position 2 in the city list
  print(
      'Something that is not in the list show up as ${cities.indexOf('bleh')}'); 
      //Something that is not in the list show up as -1
}
```

### Type Annotations with Lists
Used to restrict the type of variable that can be used in the list to make code safer. 

``` Dart
void main() {
  List<String> cities = ['London', 'Paris', 'Cape Town'];
  print('Cities list: $cities'); //Cities list: [London, Paris, Cape Town, 5]
  List<int> numbers = [1, 3, 5, 7];
  print('Numbers list: $numbers'); //Numbers list: [1, 3, 5, 7, 9]
  //!!!!! But it is better to user var, const or final to declare a list
  //To declare a list using var, but still casting it as a list of strings:
  var names = <String>['Bob', 'Jack', 'Zoe'];
  print(names); //[Bob, Jack, Zoe]
}
```

### Using var, final and const in Lists

|  | **Reassign variable to new list** | **Changes values in list** |
|--|--|--|
| **var** | Yes | Yes |
| **final** | No, compile time error | Yes |
| **const** | No, compile time error | No, **RUNTIME ERROR** | 

## Sets
**Set**: A set is an unordered collection of **unique** objects. It is represented by the Set class in Dart, and can also contain objects of any type. Sets can be created using the curly brace notation, or by calling the Set constructor.

### Note!
- The subscript operator (for example set[1] to return the 2nd entry) does not work with Sets. Instead use set.elementAt(1). 
- Use the other methods that work with lists like set.add('thing'), set.remove('thing')... 

### Sets are unordered, sort of
[Docs on Sets on dart.dev](https://api.dart.dev/stable/2.19.2/dart-core/Set-class.html)
Iterating over elements of a set may be either unordered or ordered in some way. Examples:

- A [HashSet](https://api.dart.dev/stable/2.19.2/dart-collection/HashSet-class.html) is unordered, which means that its iteration order is unspecified,
- [LinkedHashSet](https://api.dart.dev/stable/2.19.2/dart-collection/LinkedHashSet-class.html) iterates in the insertion order of its elements, and
- a sorted set like [SplayTreeSet](https://api.dart.dev/stable/2.19.2/dart-collection/SplayTreeSet-class.html) iterates the elements in sorted order.
- Constant set literals promise source ordering (first occurrence if the same value occurs more than once). They're like immutable LinkedHashSets.
```Dart
void main() {
  final countries = <String>{'London', 'London', 'London', 'London'};
  print(countries); //{London};
  countries.add('Cape Town');
  countries.addAll({'Amsterdam', 'Paris', 'Paris', 'Paris'});
  print(countries); //{London, Cape Town, Amsterdam, Paris}
  print('First Country: ${countries.first}'); //First Country: London
  print('Is Cape Town in the set: ${countries.contains('Cape Town')}');
  //Is Cape Town in the set: true
  print('Last Country: ${countries.last}'); //Last Country: Paris
  print('Set lenght: ${countries.length}'); //Set lenght: 4
  int i = 0;
  for (String country in countries) {
    if (country == 'Cape Town') {
      print(
          'Cape Town is at position ${i + 1} in the set. Not ordered my ass!');
      // Cape Town is at position 2 in the set. Not ordered my ass!
      break;
    } //if
    i++;
  } //for loop
} //main
```

### Methods  unique to Sets (Union, Intersection, Difference, Subset, Superset)

```Dart
void main() {
  var africanCountries = {'South Africa', 'Kenya', 'Zimbabwe'};
  var europeanCountries = {'France', 'Germany', 'Italy', 'South Africa'};
  print(africanCountries.union(europeanCountries));
  // {South Africa, Kenya, Zimbabwe, France, Germany, Italy}
  // Note South Africa is only printed once
  print(africanCountries.intersection(europeanCountries)); // {South Africa}
  print(africanCountries.difference(europeanCountries)); // {Kenya, Zimbabwe}
  // Note that only 'different' countries in the first set are printed
  // subset  
}
```


## Maps
**Map**: A map is an unordered collection of key-value pairs, in which each key is unique. It is represented by the Map class in Dart, and can also contain objects of any type. Maps can be created using the curly brace notation, with a colon separating the keys and values, or by calling the Map constructor.

```Dart
void main() {
  Map England = {
    'Capital': 'London',
    'Population': 60000000,
    'Currency': 'Pound Sterling',
    'Language': 'English'
  }; // Map England
  Map<String, dynamic> SouthAfrica = {
    'Capital': 'Pretoria',
    'Population': 60000000,
    'Currency': 'Rand',
    'Language': 'English'
  }; // Map SouthAfrica
  Map<int, int> numbers = {1: 1, 2: 4, 3: 9, 4: 16, 5: 25};
  const bob = <String, dynamic>{
    // can be declared with var final or const
    'name': 'Bob',
    'age': 25,
    'height': 1.75,
    'weight': 75,
    'isMarried': false
  };

  print(England['Capital']); //London
  print(SouthAfrica['Language']); //null
  print(numbers[5]); //25
  print("${bob['name']}'s age is ${bob['age']}"); //25
} //main
```

### Manipulating data in Maps
#### Change data
```Dart
void main() {
  Map England = {
    'Capital': 'London',
    'Population': 60000000,
    'Currency': 'Pound Sterling',
    'Language': 'English'
  }; // Map England

// -- Change data --
  print(England['Population']); //60000000
  England['Population'] = 65000000;
  print(England['Population']); //65000000

// -- Add key value pair --
  print(England); //60000000
  //{Capital: London, Population: 65000000, Currency: Pound Sterling, Language: English}
  England['New'] = 'Yeh Baby!';
  print(England);
  //{Capital: London, Population: 65000000, Currency: Pound Sterling, Language: English, New: Yeh Baby!}
}
```

#### Reassigning dynamic map variables (the as operator)
Dart will not automatically assign an obviously String value as a String when assigning it from a dynamic map to a normal variable. to fix this, use the as operator to specify the variable type. 

```Dart
void main() {
  Map England = {
    'Capital': 'London',
    'Population': 60000000,
    'Currency': 'Pound Sterling',
    'Language': 'English'
  }; // Map England
  // -- the as operator --
  var englandPopulation = England['Population'] as int;
  print(England['Population'].runtimeType);
  print(englandPopulation + 1); //London
} //main
```

#### Null value if key does not exist
When calling a map value with a key that does not exit, a null is returned.

```Dart
void main() {
  var map = {'key1': 'value1', 'key2': 'value2'};
  print(map['key3']); //null
// check if key exists
  if (map.containsKey('key3')) {
    print(map['key3']);
  } else {
    print('Key does not exist');
  } //if else
} //main
```

#### Iterating on Maps
An iterable is a collection of items that can be accessed in sequence. Maps are not iterable, but it is possible to iterate through the keys of a map with the .keys operator. 

```Dart
void main() {
  var map = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'};
  for (var key in map.keys) {
    print(key);
  } //for loop
}
```

It is also possible to use the .entries operator.

```Dart
void main() {
  var mymap = {'key1': 'value1', 'key2': 'value2', 'key3': 'value3'};
  for (var myEntry in mymap.entries) {
    print('${myEntry.key} : ${myEntry.value}');
  } //for loop
} //main
```

## Nested Collections
##### Restaurant rating exercise 
Task calculate the average of a list that is nested in a map that is nested in a list.
(Calculate the average rating of multiple restaurants)
```Dart
final restaurants = [
  {
    'name': 'Pizza Place',
    'cuisine': 'Italian',
    'avgRating': 0.0,
    'ratings': <double>[1.5, 3.5, 1.0, 2.0, 2.5],
  },
  {
    'name': 'Thai Express',
    'cuisine': 'Thai',
    'avgRating': 0.0,
    'ratings': <double>[4.0, 4.5, 4.5, 3.5, 3.5],
  },
  {
    'name': 'Coffee Club',
    'cuisine': 'Coffee',
    'avgRating': 0.0,
    'ratings': <double>[4.5, 4.0],
  },
  {
    'name': 'Burger Town',
    'cuisine': 'American',
    'avgRating': 0.0,
    'ratings': <double>[4.0, 3.5, 4.0],
  },
];
void main() {
  for (var restuarant in restaurants) {                    //given by instructor
    final ratings = restuarant['ratings'] as List<double>; //given by instructor
    //TODO: calculate the average rating and assign it to the 'avgRating' key
    restuarant['avgRating'] = ratings.average; //answer
  }
}
```

##  Functions and Operators relevant to Collections

It is possible to use collection-if, collection-for and ... together. These operators also work with literals instead of collections, in other words, it is possible to say ...[1,2,3] instead of ...countOneToThreeList.

This functionality is very important when we start using flutter where the UI is defined declaratively. 

### Collection-if

It is possible to provide conditional logic to determine the values that should be assigned when declaring a list using the collection-if. 

##### Note! 
Even though this is an "if", it is not a regular if statement. Regular if statements cannot be used when declaring collections. 
```Dart
void main() {
  bool likeBiltong = true;
  bool likeMilkTart = false;

  var saFoodForYou = [
    'Bobotie',
    'Bunny Chow',
    'Braai',
    if (likeBiltong) 'Biltong',
    if (likeMilkTart) 'Milk Tart',
  ];
  print(saFoodForYou); // [Bobotie, Bunny Chow, Braai, Biltong]
}
```

### Collection-for

It is also possible to iterate though another collection when declaring a collection with the collection-for.
```Dart
void main() {
  bool likeBiltong = true;
  bool likeMilkTart = false;
  var moreSAFood = [
    'Bobotie',
    'Bunny Chow',
    'Braai',
  ];
  var saFoodForYou = [
    for (var food in moreSAFood) food + '!',
    if (likeBiltong) 'Biltong',
    if (likeMilkTart) 'Milk Tart',
  ];
// notes that this can also be don with:
// saFoodForYou.addAll(moreSAFood);
  print(saFoodForYou); // [Bobotie, Bunny Chow, Braai, Biltong]
}
```
### Spreads
**Spread**: Spread is an operator in Dart that allows you to insert the contents of an iterable (such as a list, set, or map) into another iterable or function call. It is represented by the spread operator (...) followed by the iterable. The spread operator can be used to combine multiple lists or sets, or to add key-value pairs to a map.

##### Note! 
- Just adding the name of the other collection into a collection will nest the values, not spread them, see the example code.
- The is also possible to spread a values into an iterable without declaring a list/map... beforehand. ...['one', 'two'] instead of ...countToTwo

```Dart
void main() {
  bool likeBiltong = true;
  bool likeMilkTart = false;
  var moreSAFood = [
    'Bobotie',
    'Bunny Chow',
    'Braai',
  ];
  var saFoodForYou = [
    moreSAFood, //this will nest the list
    ...moreSAFood, //this will spread the list
    if (likeBiltong) 'Biltong',
    if (likeMilkTart) 'Milk Tart',
  ];
// notes that this can also be don with:
// saFoodForYou.addAll(moreSAFood);
  print(saFoodForYou); //[[Bobotie, Bunny Chow, Braai], Bobotie, Bunny Chow, Braai, Biltong]
}
```

## Composable use of if, for and Spread

As noted earlier, you can combine if, for and ...
```Dart
void main() {
  var wantMore = true;
  var babyNames = ['Jack', 'Jill', 'Bob', 'Alice'];
  var moreBabyNames = ['John', 'Jane', 'Jack', 'Joe'];

  var finalBabyNamesList = [
    ...babyNames,
    if (wantMore)
      for (var name in moreBabyNames)
        if (name.length < 4) name + ' Snyman'
  ];
  print(finalBabyNamesList);
} 
```

### Shopping list exercise 

```Dart
void main() {
  const bananas = 5;
  const apples = 6;
  const grains = {
    'pasta': '500g',
    'rice': '1kg',
  };
  const addGrains = true;
  var shoppingList = {
    if (bananas > 0) 'bananas': '$bananas',
    if (apples > 0) 'apples': '$apples',
    if (addGrains) ...grains,
  };
  print(shoppingList); // {bananas: 5, apples: 6, pasta: 500g, rice: 1kg}
}//mainain
```

## Copying Collections
When assigning one collection the value of the other, both collections point to the same bit of memory, so if you change a value in one of these lists, the change will be applied to both.

To copy the values into unique memory space use: 
```Dart
copyOfList = [...originalList]
```

```Dart
void main() {
  var originalList = [1, 2, 3];
  var copiedList = originalList;
  print(
      'Simple assignment, before change. Original: $originalList, Copied: $copiedList');
  print('Adding 4 to original list, not the copied list...');
  originalList.add(4);
  print(
      'Simple assignment, after change. Original: $originalList, Copied: $copiedList \n');
  var copiedList2 = [...originalList];
  print(
      'Spread operator, before change. Original: $originalList, Copied: $copiedList2');
  print('Adding 5 to original list, not the copied list...');
  originalList.add(5);
  print(
      'Spread operator, after change. Original: $originalList, Copied: $copiedList2');
}
```

#  Data Processing from CSV File Exercise

## Excepting Command Line Parameters

```Dart
import 'dart:io';

void main(List<String> arguments) {
  if (arguments.isEmpty) {
    print('Usage: dart basic_data_processing.dart <input_file.csv>');
    exit(1); 
// hard exit out of the program, convention: error code 0 for all is well, non-zero for error
  }
  print(arguments.first); // print the first argument
}
```

## Reading Files Line by Line

```Dart
import 'dart:io';

void main(List<String> arguments) {
  if (arguments.isEmpty) {
    print('Usage: dart basic_data_processing.dart <input_file.csv>');
    exit(1); 
  }
  final filename = arguments.first; //just a variable
  final file = File(filename); //using the File() function to create a list
  for (var line in file.readAsLinesSync()) { // iterating over the file list
    print(line); // printing each line in the file list
  }
}
```

This code will fall over badly when the file does not exist, but to catch that error we need more knowledge of asynchronous programming in dart, which will be covered later on.

## Final Code
```Dart
// This program reads a csv file and prints out the total time spent on each activity
// Run: dart basic_data_processing.dart assets/CSVExport-Code_With_Andrea-2019.csv

import 'dart:io';

void main(List<String> arguments) {
  //verify that the user has provided a filename
  if (arguments.isEmpty) {
    print('Usage: dart basic_data_processing.dart <input_file.csv>');
    exit(
        1); // hard exit out of the program, convention: error code 0 for all is well, non-zero for error
  }

  //read the file (first argument as the filename)
  final filename = arguments.first;
  final file = File(filename).readAsLinesSync();

  //remove the header line
  file.removeAt(0);

  //read the activities into a set (set will remove duplicates)
  final activities = <String>{};
  double time = 0.0;
  for (var line in file) {
    var element = line.split(',')[5];
    activities.add(element);
  }
  //loop through the file and add up the time by activity type
  for (var activity in activities) {
    time = 0.0;
    //skip the empty activity
    if (activity == '""') {
      continue;
    }
    //loop through the file and add up the time
    for (var line in file) {
      if (line.split(',')[5] == activity) {
        time = time + double.parse((line.split(',')[3]).replaceAll('"', ''));
      }
    }
    //calculate the space needed for allignment on the floating point
    String space =
        ' ' * (30 - (activity.length + time.toStringAsFixed(1).length));
    //print the activity and time
    print('${activity.replaceAll('"', '')}: $space ${time.toStringAsFixed(1)}');
  }
}
```


# Null Safety