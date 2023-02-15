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








