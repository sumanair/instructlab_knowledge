
# Introducing Rockstar
Rockstar is a computer programming language designed for creating programs that are also hair metal power ballads.

## Inception
Dylan Beattie is the creator of the Rockstar programming language and has written several articles and given talks about the language: 
* How I built Rockstar: Parsing esoteric languages with .NET: A YouTube video where Beattie explains how to build a parser and interpreter for Rockstar using C# and .NET. 
* The Art of Code: A YouTube video where Beattie discusses the origins of programming as an art form, including esoteric languages, quines, and live coding. 
* Repos, Riffs, and the Rockstar Programming Language: A talk Beattie gave at the 2021 GitKon Git conference. 

Beattie created Rockstar as a joke, combining features from other programming languages with lyrics from classic rock artists. The language has since become an open source project with multiple implementations, including Rocky, a Java implementation, and rockstar-js, a Rockstar-to-JavaScript transpiler. Rockstar has been featured in articles on BoingBoing and in Classic Rock magazine.

## The Rockstar Language Specification
Rockstar is intended to give the programmer an unprecedented degree of poetic license when it comes to the composition and structure of their programs.

## File format
Rockstar programs are UTF-8 files with the `.rock` file extension. (Given that for everything included in the current Rockstar specification, UTF-8 is indistinguishable from 7-bit ASCII, that’s a fancy way of saying they’re plain text files.)

## Comments
The use of comments in Rockstar programs is strongly discouraged. This is rock’n’roll; it’s up to the audience to find their own meaning. If you absolutely insist on commenting your Rockstar programs, comments should be contained in parentheses `()`. Yes, this means you can’t use brackets in arithmetic expressions and may need to decompose complex expressions into multiple evaluations and assignments.

There is, however, a good use for comments - to mark up your code so people know how to play it! Comment delimiters `{}` and `[]` are now available, as well. These are used by the ChordPro musical notation system.

```rockstar
(Initialise Tommy = 1337)
Tommy was a big bad brother.
```

## Variables
Rockstar supports three kinds of variable names:

### 1. Simple variables
Simple variables are valid identifiers that are not language keywords. A simple variable name must contain only letters and cannot contain spaces. Note that Rockstar does not allow numbers or underscores in variable names - remember the golden rule of Rockstar syntax: if you can’t sing it, you can’t have it. Simple variables are case-insensitive.

```rockstar
Variable is 1
Tommy is a rockstar
X is 2
Y is 3
Put x plus y into result
```

### 2. Common variables
Common variables consist of one of the keywords `a`, `an`, `the`, `my`, `your`, or `our` followed by whitespace and a unique variable name, which must contain only lowercase ASCII letters a-z. The keyword is part of the variable name, so `a boy` is a different variable from `the boy`. Common variables are case-insensitive.

```rockstar
My variable is 5
Your variable is 4
Put my variable plus your variable into the total
Shout the total
```

### 3. Proper variables
Proper variables are multi-word proper nouns - words that aren’t language keywords, each starting with an uppercase letter, separated by spaces. (Single-word variables are always simple variables.) Idiomatic variable names like `Doctor Feelgood` or `Tom Sawyer` are encouraged.

```rockstar
Eleanor Rigby, Peggy Sue, Black Betty, and Johnny B Goode
```

### Scope of Variables
- If a variable is defined outside of a function, it is in global scope.
- If a variable is defined inside of a function, it is in local scope.
- Variables in Rockstar are dynamically typed.

### Case Sensitivity
Rockstar keywords and variable names are case-insensitive, with the exception of proper variables where the first letter of each word must be capitalized.

```rockstar
TIME, time, tIMe, TIMe are all equivalent
Tom Sawyer, TOM SAWYER, TOm SAWyer are all equivalent
```

## Pronouns
The keywords `it`, `he`, `she`, `him`, `her`, `they`, `them`, `ze`, `hir`, `zie`, `zir`, `xe`, `xem`, `ve`, and `ver` refer to the variable which was most recently assigned a value.

## Types
Rockstar uses a similar type system to that defined by the ECMAScript type system.

- **Mysterious**: the value of any variable that hasn’t been assigned a value (`mysterious`).
- **Null**: the null type (`nothing`, `nowhere`, `nobody`, `gone`).
- **Boolean**: logical entities true and false (`right`, `yes`, `ok` are aliases for true; `wrong`, `no`, `lies` are aliases for false).
- **Number**: Double-precision floating-point numbers (stored according to the IEEE 754 standard).
- **String**: Sequences of 16-bit unsigned integer values representing UTF-16 code units.

## Arrays
Rockstar supports JavaScript-style arrays. Arrays are zero-based and dynamically allocated when values are assigned using numeric indexes.

```rockstar
Let the array at 0 be "zero"
Let the array at 1 be "one"
Let the array at 255 be "big"
Shout the array at 0
Shout the array at 255
```

Returning an array in a scalar context will return the current length of the array.

```rockstar
Shout my array (will print 256)
```

### Queue Operations
Rockstar arrays can also be created and manipulated by the queue operations `rock` and `roll`.

```rockstar
Rock the array with 1, 2, 3
Roll the array (returns 1; array is now [2, 3])
```

## Splitting Strings
To split a string, use the `cut` mutation (aliases: `split`, `shatter`).

```rockstar
Split "a,b,c" into the array with ","
Shout the array (prints ["a", "b", "c"])
```

## Joining Arrays
To join an array, use the `join` mutation (alias: `unite`).

```rockstar
Join tokens with ";"
```

## Truthiness
The concept of "truthiness" is key to Rockstar comparisons:
- **Falsy**: mysterious, null, false, 0.
- **Truthy**: Everything else.

## Constants vs Keywords
Words used to construct literals are **constants**; words used to construct syntax are **keywords**.

| Constant  | Aliases                           |
|-----------|-----------------------------------|
| mysterious| -                                 |
| null      | nothing, nowhere, nobody, gone    |
| true      | right, yes, ok                    |
| false     | wrong, no, lies                   |
| empty     | silent, silence                   |

## Literals and Assignment
String literals in Rockstar use double quotes.

```rockstar
"Hello San Francisco"
```

Assignment is done using either `put <expression> into <variable>` or `let <variable> be <expression>`.

```rockstar
Put 123 into X
Let my balance be 1000000
```

## Poetic Literals
A poetic literal is a unique Rockstar feature that allows the programmer to initialize variables poetically.

```rockstar
My dreams were ice. A life unfulfilled; wakin' everybody up, taking booze and pills
```

This initializes `my dreams` with the value `3.1415926535`.

## Increment and Decrement
Use `Build {variable} up` and `Knock {variable} down` to increment and decrement variables.

```rockstar
Build my world up
Knock the walls down
```

## Operators
Rockstar supports the following arithmetic operators:

| Operator   | Aliases         |
|------------|-----------------|
| + (add)    | plus, with      |
| - (subtract)| minus, without |
| * (multiply)| times, of      |
| / (divide) | over, between   |

## Compound Assignment Operators
Rockstar also supports compound assignment operators.

```rockstar
Let X be with 10
```

## Function Declarations
Functions are declared using the `takes` (alias: `wants`) keyword.

```rockstar
Multiply takes X and Y
Give back X times Y
```

## Conditionals
Conditional expressions use the `If` keyword. An `Else` block can also be used.

```rockstar
If Tommy is nobody
```

## Loops
Use the `While` or `Until` keywords for loops.

```rockstar
While Tommy ain't nothing
Knock Tommy down
```

## Examples
Here is an example of the FizzBuzz implementation in Rockstar:

```rockstar
Limit is 100
Counter is 0
Fizz is 3
Buzz is 5
Until Counter is Limit
Build Counter up
If Counter is FizzBuzz
Say "FizzBuzz!"
Continue
If Counter is Fizz
Say "Fizz!"
Continue
If Counter is Buzz
Say "Buzz!"
Continue
Say Counter
```
