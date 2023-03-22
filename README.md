#pythonGeneral    
> update: 22/03

**ALL THE WAY INTO PYTHON**

- I KNOW MASTERING PYTHON REQUIRES A LOT OF TIME, TEARS, FRUSTRATIONS
  - mastering python requires a lot of dedication
  - mastering python requires at least 1h daily on learning theory
  - mastering python requires everyday reading others code
  - mastering python requires everyday writing code
  - mastering python requires learning from the best, like Andy, like Jose
  - mastering python requires reverse engineering our VxRail Scripts and being able to improve them
  - I am pragmatic programmer
  - I think like computer:
    -  https://www.rogerperkin.co.uk/programming/what-is-computational-thinking/
    - https://www.cs.cmu.edu/afs/cs/usr/wing/www/publications/Wing06.pdf





# bases 

The __bases__ property is a special attribute in Python that is used to access the tuple of base classes of a class. When you create a new class in Python, you can specify one or more base classes from which your new class inherits attributes and methods. The __bases__ attribute provides a way to access the tuple of base classes that your class inherits from.

Here's an example to illustrate how the __bases__ attribute works:

```python 
class Animal:
    def speak(self):
        print("I am an animal")

class Dog(Animal):
    def bark(self):
        print("Woof!")

d = Dog()
d.speak()  # Output: "I am an animal"
d.bark()   # Output: "Woof!"

print(Dog.__bases__)  # Output: (<class '__main__.Animal'>,)
``` 
In this example, we define two classes, Animal and Dog. The Dog class inherits from the Animal class, which means that it automatically inherits the speak method from Animal. We then create an instance of Dog called d, and we can call both the speak and bark methods on it.

Finally, we use the __bases__ attribute to access the tuple of base classes of the Dog class, which in this case is (<class '__main__.Animal'>,). This tuple contains a single element, which is the Animal class, indicating that Dog inherits from Animal.







In Python, yield is used in a function to create a generator object. A generator is a special type of iterator that allows you to iterate over a sequence of values without generating the entire sequence at once. Instead, the values are generated on-the-fly as you iterate over the generator.

When you use yield in a function, the function becomes a generator function. When the generator function is called, it returns a generator object that you can iterate over using a for loop or other iteration methods.

Here's an example to demonstrate how yield works in a generator function:

python
Copy code
def count_up_to(n):
    i = 1
    while i <= n:
        yield i
        i += 1

for num in count_up_to(5):
    print(num)
Output:

Copy code
1
2
3
4
5
In this example, the count_up_to() function is a generator function that generates a sequence of integers from 1 to n. The yield keyword is used to return each integer one at a time, as the generator is iterated over. The for loop at the bottom of the code block iterates over the generator, printing each integer in the sequence as it is generated.

The main advantage of using a generator instead of a list is that generators are more memory-efficient. Because they generate the sequence on-the-fly, they don't need to store the entire sequence in memory at once. This makes them ideal for iterating over very large or infinite sequences of values.



```bash
hasattr() is a built-in Python function, not a method. It is used to check whether an object has an attribute with a given name.

The syntax of hasattr() is as follows:

python
Copy code
hasattr(object, attribute_name)
Here, object is the object you want to check for the presence of the attribute, and attribute_name is a string representing the name of the attribute you want to check for.

The function returns True if the object has the specified attribute, and False otherwise.

Here's an example of how to use hasattr():

python
Copy code
class MyClass:
    x = 5

obj = MyClass()

if hasattr(obj, 'x'):
    print("obj has attribute 'x'")
else:
    print("obj does not have attribute 'x'")
Output:

python
Copy code
obj has attribute 'x'
In this example, hasattr() is used to check whether the object obj has an attribute named x. Since the attribute exists in the MyClass class, which obj is an instance of, the function returns True, and the message "obj has attribute 'x'" is printed to the console.




```

The first parameter of each method:
A. holds a reference to the currently processed object
B. is always set to None
C. is set to a unique random value
D. is set by the first argument's value

The answer is A. holds a reference to the currently processed object. In Python, the first parameter of an instance method refers to the instance of the class that is calling the method. This parameter is usually called "self" by convention. It is used to access instance variables and other instance methods of the same object.



The lexicon or "lexis" of a programming language refers to its vocabulary, i.e., the set of keywords, identifiers, literals, and symbols that are used to write programs in that language.

In Python, the lexicon includes keywords such as if, else, while, for, def, class, import, from, and as, as well as built-in functions such as print(), input(), and len(). Python also has several built-in data types, including numbers, strings, lists, tuples, dictionaries, and sets.

In addition to the built-in vocabulary, Python also allows users to define their own identifiers, such as variable names, function names, and class names. These user-defined identifiers become part of the lexicon of any program that uses them.

Overall, Python's lexicon is designed to be relatively simple and easy to learn, making it a popular choice for beginners and experienced programmers alike.



--- 

A. chr(ord(x)) == x: This equation takes a character x, gets its Unicode code point using ord(), and then converts it back to a character using chr(). If x is a valid character, then this equation will always be true.

D. ord(chr(x)) == x: This equation takes a Unicode code point x, converts it to a character using chr(), and then gets its Unicode code point using ord(). If x is a valid Unicode code point, then this equation will always be true.



chr() and ord() are two built-in Python functions that are used for working with characters and their corresponding Unicode code points.

chr() takes an integer representing a Unicode code point and returns the corresponding character. For example, chr(65) returns the character 'A', since the Unicode code point for 'A' is 65. chr() can also take a string representing an integer in the range 0-1114111 (which is the maximum Unicode code point) and returns the corresponding character.

ord() takes a character and returns its corresponding Unicode code point as an integer. For example, ord('A') returns 65, which is the Unicode code point for 'A'. ord() can also take a string containing a single character and returns the corresponding Unicode code point.

These functions are often used together to convert characters to their corresponding code points and vice versa. For example, ord(chr(65)) returns 65, which is the Unicode code point for 'A', and chr(ord('A') + 1) returns 'B', which is the character corresponding to the Unicode code point 66.












In Python, __main__ is the name of the default module that is executed when a Python script is run from the command line. It is also the name of the top-level script environment that Python creates when a module is run as the main program.

When a Python script is run, the interpreter first initializes the environment and sets up some special variables, including __name__. If the script is being run as the main program, __name__ is set to the string "__main__". If the script is being imported as a module into another script, __name__ is set to the name of the module.

This distinction is useful for writing scripts that can be used both as stand-alone programs and as modules in larger programs. By checking the value of __name__, a script can determine whether it is being run as the main program or imported as a module, and can take different actions in each case.

For example, a script might define a function or class that can be imported and used by other scripts, but also include some code at the bottom of the script that runs a test of the function or class if the script is being run as the main program. In this case, the test code would be enclosed in an if __name__ == "__main__": block, so that it is only executed if the script is being run directly and not when it is imported as a module.








The correct way to declare a two-parameter lambda function raising its first parameter to the power of the second parameter is:

D. lambda x, y: x ** y

This lambda function takes two parameters x and y, and returns the result of raising x to the power of y using the ** operator.

Option A is incorrect because lambda is not defined with an assignment operator.

Option B is close but is missing the colon : that separates the argument list from the expression.

Option C is incorrect because it uses the def keyword which is used for defining a regular function, not a lambda function.

Option D is the correct syntax for defining a two-parameter lambda function that raises the first parameter to the power of the second parameter.







def f(n):
if n==1:
return 1 
return n + f(n-1)
print(f(2))
The expected output of the given code is 3.

The function f takes an integer n as input and returns the sum of all integers from 1 to n.

If n equals 1, the function returns 1 (the base case). Otherwise, it adds n to the result of calling f(n-1) recursively.

In this case, we call the function with n = 2.

The first condition n == 1 is not met, so the function adds n (which is 2) to the result of calling f(n-1) with n-1 = 1.

Since n is now 1, the function returns 1 (the base case).

Therefore, the final result of f(2) is 2 + 1 = 3, which is what is printed by the print statement.




A function called issubclass (c1, c2) is able to check if:
A. c1 and c2 are both subclasses of the same superclass
B. c2 is a subclass of c1
C. c1 is a subclass of c2
D. c1 and c2 are not subclasses of the same superclass





# subclasses # superclasses 

a subclass is a class that inherits properties and methods from a superclass. A superclass is a class that is being inherited from. The subclass can add new properties or methods or override the inherited ones.

Here is an example of a superclass and a subclass in Python:

```python 
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def speak(self):
        print("I am an animal")

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, species="Dog")
        self.breed = breed

    def speak(self):
        print("Woof!")

dog1 = Dog("Fido", "Labrador")
print(dog1.name)      # Fido
print(dog1.species)   # Dog
print(dog1.breed)     # Labrador
dog1.speak()          # Woof!
```

In this example, we have a superclass Animal that has an __init__ method to initialize the name and species attributes and a speak method that prints "I am an animal".

The subclass Dog inherits from the Animal class using the syntax class Dog(Animal):. It has its own __init__ method that calls the super().__init__ method to initialize the name attribute and set the species attribute to "Dog". It also has a breed attribute. The speak method is overridden to print "Woof!".


We then create an instance of Dog called dog1 with the name "Fido" and the breed "Labrador". We can access its attributes using the dot notation and call its methods. When we call dog1.speak(), it prints "Woof!" because the speak method was overridden in the Dog subclass.

In summary, a subclass inherits attributes and methods from a superclass and can add its own attributes and methods or override the inherited ones. The super() function is used to call methods from the superclass.









---

# PYTHON

**python has dynamic typing**

- meaning I can reassign variable to different data type later in code
  - ```dogs = 2 <more code> dogs = ["franki", "jessie"]```
  - its easy for programmer because dont have to declare data type each time you declare something
  - it double edge sword because you can hit bugs for unexpected data types
  - you can use build in type function **type()** to quickly check the type of any object
- *IN C++* if you declare *dogs* as integer + value you can not change that later in code


---

# PyPi

- is a repository for open-source third-party python packages
- with PIP you install from PyPi
- so for example if we want to use **colorama** we install it with pip
- ```pip install colorama``` and now we can use it in our scripts

**so withy PyPI we can install external modules and packages** now we will learn how to write our own.

### module is just a .py script used in another script
- packages are collection of moduels
- module is really just .py script..its fancy way of saying here Im using another .py script
- and this is how you actualy write nice scripts / programs: that there are multiple files and you importing stuff from them

```python
# file_one with function my_func

# file_two (same directory) and we want to import my_func this is how:
# - from file_one import my_func
# BUT both files are in same directory
```


# IMPORT: 

In Python, a module is simply a file containing Python definitions and statements. To use the functions, classes, and variables defined in a module, you need to import it into your current Python script.

There are two styles of import statements in Python:

1) **import module_name**: 
- This style of import statement imports the entire module and makes it available under the module's name in your current script. 
- You can access the functions, classes, and variables defined in the module using dot notation.
- For example, if you have a module called my_module that contains a function called my_function, you can import the module using the following statement:
```python
# import: 
import my_module
# access the function using dot notation: 
my_module.my_function()
```

2) **from module_name import name** 
- This style of import statement allows you to import specific functions, classes, or variables from a module and make them available directly in your current script. 
- You do not need to use dot notation to access them.
- For example, if you only need to use the my_function function from the my_module module, you can import it using the following statement:
```python 
from my_module import my_function
# Then, you can use the function directly in your script without using the module name or dot notation:
my_function()
```

**The main difference between the two styles of import statements is the namespace they create.** 
When you use import module_name, you create a new namespace for the entire module, and you need to use the module name and dot notation to access its contents. When you use from module_name import name, you import only the specific function, class, or variable you need and add it directly to your current namespace.

For example, if you use import my_module, you need to use the module name and dot notation to access its contents: ```my_module.my_function()``` 

But if you use from my_module import my_function, you can use the function directly without the module name or dot notation:```my_function()```





--- 

# UNDERSCORES: 

Underscores are used in Python to indicate various naming conventions and to give special meanings to certain variables and methods.


1) **Single leading underscore:** 
- This convention is used to indicate that a variable or method is intended to be used as a private member of a class or module. 
- For example, ```_my_private_variable``` or ```_my_private_method()```. 
- However, this is just a convention and doesn't actually prevent other code from accessing the variable or method.

2) **Single trailing underscore:**
- This convention is used to avoid naming conflicts with Python keywords or built-in functions. 
- For example, ```class_``` or ```print_```.

3) **Double leading underscore:**
- This convention is used to implement *name mangling in Python*
- Name mangling is a technique used to make a variable or method private by adding the class name to its name to avoid naming conflicts. 
-  For example, ```__my_private_variable``` will be converted to ```_classname__my_private_variable``` when accessed outside the class.
- This makes it harder to accidentally modify or access the variable or method from outside the class. 

4) **Double leading and trailing underscore** 
- 


--- 

# __init__.py

- key .py file is __init__.py
- this file marks directory and lets python know that all .py scripts should be threated as a package of modules to import
- so if we want to have more, multiple directories we need this file to be in every of them
- example above where all files in same dir but what if we have subdirectories ?
  - in each subdirectory we need __inint__ file

Python defines two types of packages, regular packages and namespace packages.

Regular packages are traditional packages as they existed in Python 3.2 and earlier.
A regular package is typically implemented as a directory containing an __init__.py file.

When a regular package is imported, this __init__.py file is implicitly executed, and the objects it defines are bound to names in the package’s namespace.

The __init__.py file can contain the same Python code that any other module can contain, and Python will add some additional attributes to the module when it is imported.

![](./pngs/modules01.png)

- same like directory structure in linux:   
  - ```directory/file BUT here MODULE.PACKAGE```

![](./pngs/modules02.png)


---

# __name__ __main__

- sometimes when you import from module you would like to know wheter a module function is being used as import
- or if you are using the oryginal .py file of that module
- ```if __name__ == __main__``` is usualy at the end of larger script files
  - it is a check if we are running the script
  - it means you run the file, the file that has not been imported
  - if __name__ == "__main__" means we runnign whole script, if python can find the name of the file lol

![](./pngs/modules03.png)


---

# __pycache__

A cache is something that keeps a copy of stuff in case you need it again, to save you having to go back to the original  

When you run a program in Python, the interpreter compiles it to bytecode first (this is an oversimplification) and stores it in the __pycache__ folder.

If you look in there you will find a bunch of files sharing the names of the .py files in your project's folder, only their extensions will be either .pyc or .pyo. These are bytecode-compiled and optimized bytecode-compiled versions of your program's files, respectively.

As a programmer, you can largely just ignore it... All it does is make your program start a little faster. When your scripts change, they will be recompiled, and if you delete the files or the whole folder and run your program again, they will reappear (unless you specifically suppress that behavior).

---






---

# ASCII vs UTF-8

```yaml
UTF-8 is an abbreviation for Unicode Transformation Format — 8 bits.

The “8” here means 8-bit blocks are used to represent a character.
UTF-8 is the most commonly used encoding format for Unicode characters.
So, simply speaking, Unicode is a character set and UTF-8 is an encoding format.
With a character set, a character is translated to a decimal number.


ASCII is an abbreviation for American Standard Code for Information Interchange
It is the first character set and character encoding standard for electronic communication.
ASCII contains 128 characters which contain the lower and upper case English letters (a-zA-Z),
the numbers from 0–9, and some special characters.
ASCII is subset of UTF-8

Unidecode is a library that can be used to translate Unicode characters to “approximate” ASCII counterparts. For example, Ä => , Å=> A and Ö=> O.
```


---
# errors | error handling

AttributeError can be defined as an error that is raised when an attribute reference or assignment fails.

One handy way of deciding between value error and type error is by understanding that
value error occurs when there is a problem with the content of the object you tried to assign the value to
for example the statement int("a") produces a ValueError because the value being provided to int is of the wrong type
(Don't associate with TypeError).
Now the 'type' of the 'func' function in the question is such that it REQUIRES a value. It is the TYPE (read nature) of this function that it must need a value to work and if we call it simply like func() it violates its nature. Hence a TypeError occurs.

## try except else

```python
# try:
#   code that might break your program
#   important about incantentions
# except:
#   here what to do if we run into error..
#   print("hey you doing sth wrong here...")
# else:
#   this block of code is what program sopousd to do if run with no errors

try:
  for i in ['a','b','c']:
    print(i**2)
except:
  print("watch out error here")
finally:
  print("all done")

```
## try except finally

```python
# try:
#   your code here, example opening file:
#   f = open("testfile","w")
#   f.write("write a test line")
# except TypeError:
#   #this line excepts only TypeErrors
# except:
#   thsi will except all other errors
#   but you want to have code doign sth with this exception
# finally:
#   this will always run, no matter if errors in code or not, it always runs
try:
  for i in ['a','b','c']:
    print(i**2)
except:
  print("watch out error here")
finally:
  print("all done")
```
![](./pngs/error_handling01.png)

---

# testing tools
- when working with other ppl you have to test your new code to make sure the old code didnt break

### pylint
- library that looks at your code and reports back possible issues
- it also gives you score of your code up to 10/10 :D

```python
pip install pylint
pylint filename.py

```

### unittest
- buil-in library will allow you to test your own programs and check you are getting desired outputs
- so you have to:
1) inside your Testing Script import unittest
2) import all other modules / scripts you have been working on
3) create a class for testing (unittest.testcase)
4) and than you have methods to test any situation you can think of, basicaly it checks your code
5)
























---

# decompile:

```bash
#install uncompile if not installed
pip install uncompyle6

uncompyle6 <what_they_dont_wants_U2c>   #std output
uncompyle6 -o . <what_they_dont_wants_U2c>
```





---
# PYTHON CRASH COURSE:
---

## DATA TYPES:

**every object in python has associated data type** and data types determine what you can (and can not) do with the object...

**data type** is basic building block when constructing larger piece of code


### Fundamental data types:

  - int   
    - integers: whole numbers
  - float
    - floating point: numbers with decimal point, even when .0 its still an integer ex: 100.0
  - str
    - strings: ordered sequence of characeters, strings has double or single quotes so number 200 put in doublequotes *"200" is a string*

### data structures:

https://docs.python.org/3/tutorial/datastructures.html#

**data structure** a bit more specialized than basic data types, because they can hold data types in sequence or mapping,

- list:
  - *ordered sequence of objects*   
- dic:
  - can store another data types in *unordered KEY:Value* pairs
- tuples:
  - tup, is *ordered, immutable sequence of objects*
  - they look a lot like lists but are immutable, meaning - you can not change object that is already in that sequence
- bool:
  - booleans, are *logical value of True or False*
- set:
  - sets are *unordered collection of unique objects*
  - None (NoneType - represents absence of value)

**How to check the type of object in python?**

```python
#
# simply use build in type() function
#
type(2)
<class 'int'>
andre = ["handsome","lowing","fit","inteligent"]
>>> andre
['handsome', 'lowing', 'fit', 'inteligent']
type(andre)
<class 'list'>
```



---

## VARIABLES
[comment]: _variables

- pointers to place in memory that stores a value
- and they have a name (identifier)
- variable andre from above stores values, which are my characteristics
- so the values are binded to the name
- variable names should be descriptive (logical right)
- variables are case sensitive
- variables should be lowercase, (maybe only global, all global variables to be in CAPS)
- lower_case_words_separated_by_underscores (snake cases thats how they are called)
- just dont use python keywords: https://runestone.academy/runestone/books/published/py4e-int/variables/variable-names-keywords.html
- can not start with number
- can not have symbols (:!"(){@:"£$%^^&||"}")


```python
#
# ASSIGN VALUES TO VARIABLE andre
#
andre = ["handsome","lowing","fit","inteligent"]
#
# MULTIPLE VARIABLE ASSIGNMENT
#
# we can also assign values to multiple variables in one go:
#
# three  variables: me, you, us
me, you, us = "andre", "anita", "zareczeni i szczesliwi"

# and can perform logic with variable names:
#
print(me, "and", you)
andre and anita

# or example of using variables (english like names):
#
In [20]: my_income = 100
In [21]: tax_rate = 0.4
In [23]: my_taxes = my_income * tax_rate

In [24]: my_taxes
Out[24]: 40.0
```






---

## STRINGS
[comment]: _strings

- ordered sequence of characters
- with indexing that starts at  0 and reverse indexing starting with -1
- you can also slice strings
  - [start:stop:step]
    - start - numerical index of start
    - stop - is the index you go up to but not including
    - step is just the size of jump
- have to print() to call them
- strings are wrapped inside '' or ""


### strings comparison

- Python String comparison can be performed using equality (==) and comparison (<, >, !=, <=, >=) operators.
- characters in both strings are compared one by one
- when different characters are found thn their Unicode value is compared

![](./pngs/unicode01.png)


### string indexing

- with slicing you can reverse the string simply by
  - mystring[::-1] what is does is from all they way from begginigng first : to the end, second : with step of engative one -1 czyli from end lol
- indexing can be done on strings as they are in variable
  and on strings themselves:
  - "hello"[3] gives l  
- starting at index 5 and going all the way to end:
  - "hallo my friend"[5:]


### string properties and methds

- IMMUTABLE:
  - means string object doesnt support item assignment
    - you can not change/reassing one/many letters/items in any of the strings:
    ```python
    # change S to P in Sam
    name = "Sam"
    name[0] = "P"
      TypeError: 'str' object does not support item assignment
    # achieve than creating new variable:
    "P" + name[1:]
      'Pam'
    ```


- CONCATENATION:
  - adding strings together (like P+slicing to end in above example)
  - or multiplying:
    - ```python
        "yes" * 10
          yesyesyesyesyesyesyesyesyesyes
        ```

- **STRING**. the dot brings up a list of methods you can use on strings
  - string**.upper()** and now we are screaming


### string formatting

**.format() method**

```python
In [35]: a = "andre"

In [36]: b = "best"

In [37]: c = "pro"

In [38]:

In [38]: print("who is the best hacker? A: {} ! And who is {} ? {}".format(a,b,a
    ...: ))
who is the best hacker? A: andre ! And who is best ? andre
#
# PLACING ONE THING:
#
logerror = "nvme disk is corrupt"

print("The error we received was: ", colored(logerror,"red").format(logerror))

The error we received was:  nvme disk is corrupt
```


### string split()
- split() is very handy if we want to split whole sentence into individual words

![](./pngs/string_functions01.png)

### string join()
- join on anything you want, white space ?

![](./pngs/string_functions02.png)





### string colors

- prerecs:

```python
# termcolor installed in ubuntu packages
sudo apt install python3-termcolor
pip3 install termcolor

# and imported in script / ipython
from termcolor import colored
```

![pic](./pngs/format_color.png)


### strings lower() function

![pic](./pngs/string_formating01.png)







---
## ARITHMETICS

```python
# aughmented assignment in two ways can be done:
#
# -
counter = 0
counter = counter + 1
# albo to samo ale szybciej
counter +=  1

# same with multiplier or other arithmetics:
counter -= 1
counter *= 2

# there is operator precedence (czyli co jest liczone pierwsze ) called PEMDAS
#
# P   - parantesis
# E   - exponentiansions (rising to the power of)
# M   -  multiplications
# D   - division
# A   - additions
# S   - substractions  

```





## FLOATS & INTEGERS
- FLOATs take more space in memory
- you can change objects to FLOATs with float() function
- same with intigers, change FLOAT to INTEGER with int() function,
- when changing to INT you NOT rounding you just ignore the part that is fractional so 3.9999 will be just 3
- FLOATs are aproximations, because they have to be stored as binary fractions and python sometimes have issues with this, (some nubers  can not be represented in binary), more on subject read this: https://de.wikipedia.org/wiki/IEEE_754
-





## BOOLEANS
- True/False with case sensitive



## OPERATORS
- = assignment operator   
- == comparison operator   
- != not equal
- >= grater than or equla to
- '' string
- "" multi sting
- ALTERNATIVE QUOTATION:
  - use \ before special character:
    - 'Let\'s code "pandorably"'
  - use tripple quotes:
    - '''within tripple codes I'm able to use anythig "i" want'''
- % operator is the modulus operator, which returns the remainder of a division operation between two numbers. For example:
```python 
a = 17
b = 5

c = a % b

print(c) # Output: 2
```

- / operator is the division operator, which performs a regular division operation between two numbers. 



| Operator | Description | Example |
| --- | --- | --- |
| `+` | Addition | `3 + 2` evaluates to `5` |
| `-` | Subtraction | `3 - 2` evaluates to `1` |
| `*` | Multiplication | `3 * 2` evaluates to `6` |
| `/` | Division | `3 / 2` evaluates to `1.5` |
| `//` | Floor Division | `3 // 2` evaluates to `1` |
| `%` | Modulus (Remainder) | `3 % 2` evaluates to `1` |
| `**` | Exponentiation | `3 ** 2` evaluates to `9` |
| `==` | Equal | `3 == 2` evaluates to `False` |
| `!=` | Not Equal | `3 != 2` evaluates to `True` |
| `<` | Less Than | `3 < 2` evaluates to `False` |
| `>` | Greater Than | `3 > 2` evaluates to `True` |
| `<=` | Less Than or Equal To | `3 <= 2` evaluates to `False` |
| `>=` | Greater Than or Equal To | `3 >= 2` evaluates to `True` |
| `and` | Logical And | `True and False` evaluates to `False` |
| `or` | Logical Or | `True or False` evaluates to `True` |
| `not` | Logical Not | `not True` evaluates to `False` |
| `in` | Membership | `'a' in ['a', 'b', 'c']` evaluates to `True` |
| `not in` | Negative Membership | `'d' not in ['a', 'b', 'c']` evaluates to `True` |
| `is` | Identity | `3 is 3` evaluates to `True` |
| `is not` | Negative Identity | `3 is not 2` evaluates to `True` |




## OPERATORS

ENUMERATE

- prints tuples of index value + whatever it was going through
- example we want to have index of each letter in word:
- can take any itterable object and it returns index counter and the object itself

![](./pngs/operators_enumerate.png)

![](./pngs/operators_enumerate2.png)



---


# ZIP

- zip together two lists


```python
#
# having two lists and want to combine them:
#
>>> andre2
[1, 2, 3, 4, 5]
>>> andre
['fit', 'dedicated', '5AC', 'dedicated', 'handsome', 'fit', 'wolf']
>>>
>>> list(zip(andre,andre2))
[('fit', 1), ('dedicated', 2), ('5AC', 3), ('dedicated', 4), ('handsome', 5)]
>>>
#
# UNPACKING THE VALUES FROM ZIPPED ONES:
#
# 1) assign new names
for andre_adjective, and_number in zip(andre,andre2):
  print(andre_adjective)

# 2) example:
# assign new names to variables that we will place from zipped andre,andre2
>>> for andre_adjective, and_number in zip(andre,andre2):
...   print("andre is {} and {} times".format(andre_adjective,and_number)) # .format() method
...
andre is fit and 1 times
andre is dedicated and 2 times
andre is 5AC and 3 times
andre is dedicated and 4 times
andre is handsome and 5 times
```


---


### IN
- IN operator
- check if object is in list, tuple, dictionary, strings
- returns boolean

![](./pngs/operators_in.png)


The in keyword has two purposes:

The in keyword is used to check if a value is present in a sequence (list, range, string etc.).

The in keyword is also used to iterate through a sequence in a for loop:


MIN / MAX


### RANDOM
explain random.seed() 
why random.seed(1) is always the same ? 
other examples ? 

n Python, random.seed() is a method from the random module that allows you to set the starting point for generating random numbers. The starting point is known as the seed, and the same seed will always produce the same sequence of random numbers.

```python 
import random

# Generate a random number
num1 = random.random()
print(num1)

# Set the seed to 1
random.seed(1)

# Generate another random number
num2 = random.random()
print(num2)

# Generate another random number with the same seed
num3 = random.random()
print(num3)

# In this example, we first generate a random number using random.random(). This will generate a random number between 0 and 1.

# We then set the seed to 1 using random.seed(1). This means that any subsequent calls to random methods (e.g. random.random(), random.randint(), etc.) will produce the same sequence of random numbers as long as the seed remains the same.

# We then generate another random number using random.random(), which produces a different number than the first one because we set the seed to 1.

# Finally, we generate another random number using random.random() with the same seed, and this produces the same number as the second one because we used the same seed.

# This predictability can be useful in certain cases, such as in scientific simulations, where reproducibility is important.

# Another example is to use random.seed() to shuffle a list in a deterministic way. Here's an example:

import random

# Create a list of numbers
numbers = [1, 2, 3, 4, 5]

# Shuffle the list with a seed of 1
random.seed(1)
random.shuffle(numbers)
print(numbers)

# Shuffle the list again with the same seed
random.seed(1)
random.shuffle(numbers)
print(numbers)

# In this example, we first create a list of numbers. We then shuffle the list using random.shuffle() with a seed of 1. This produces a random ordering of the list. We then shuffle the list again with the same seed, which produces the same ordering as the first shuffle.

random.random() generates a random float number between 0 and 1 (inclusive of 0, but exclusive of 1), according to the documentation.

If you want to generate random numbers within a different range, you can use other methods from the random module, such as randint(), uniform(), or gauss(). For example, random.randint(a, b) generates a random integer between a and b (inclusive of both a and b).
import random

# Generate a random integer between 1 and 10 (inclusive)
num1 = random.randint(1, 10)
print(num1)     
2

# Generate a random float between 0 and 1
num2 = random.random()
print(num2)
0.4594964569679978

# Generate a random float between -1 and 1
num3 = random.uniform(-1, 1)
print(num3)
0.6965599747214852

# Generate a random number from a Gaussian distribution with mean 0 and standard deviation 1
num4 = random.gauss(0, 1)
print(num4)
-1.1447287731483977
```




## 



### INPUT

- always takes as strings

![](./pngs/input002.png)

- so what do we do to have input exaclty like we want ?
  - 1) make sure the data type is what we want
  - 2) check if input is within limits, or within choices we want


### user input validation examples

1) if type == init


2) isdigit()

![](./pngs/userinput01.png)

now same example but with more logic and checks:

![](./pngs/userinput02.png)





3) try: validate = int(userinput) except valueerror: print thats not intiger


4) INTERACTION WHERE USER PROVIDES VARIABLE WHICH CAN BE CHANGED BY HIM
- like we can use it for RCA ?
- user provides *timeframe* which we can use to search logs
- and that timeframe can be changed by user
- do kazdego zadania jest zrobiona funkcja

1) DISPLAY FUNCTION:

```python
#
# fist declare your game list variable
#
game_list = [0,1,2]

#
# than create function that will display that variable
#
def display_game(game_list):
  print("Here is current list: ")
  print(game_list)
```

2) FUNCTION TO GET POSITION CHOICE

```python
#
# always have to have INITIAL choice, here we set it as WRONG
#
def position_choice():

  choice = "wrong"

  # here we know that the choice must be either 0,1 or 2
  # in order to close off this wile loop we need to receive this three things
  while choice not in ['0','1','2']:

    choice = input("Pick a position 0,1,2: ")

    # czyli teraz if the choice is not in 0,1,2 we will print sorry provide the valid one
    if choice not in ['0','1','2']:
      print("Sorry, invalid choice!")

  # while loop is going over and over until we get correct choice
  # and when we get correct than we will return it
  return int(choice)
```
![](./pngs/userinput03.png)

3) REPLACEMENT FUNCTION

```python
#
# this function is after player has choosen correctly !
# - not player chooses replacement value
# - this one takes in two parameters: game_list and position return from previous function
def replacement_choice(game_list,position):

  user_placement = input("Type a string to place at position: ")

  # now we grab game list at the position previously passed and we make it same as user_placement
  game_list[position] = user_placement

  # and of course you have to return that gamelist
  return game_list
```

![](./pngs/userinput04.png)

4) NOW FUNCTION WHERE YOU PICK IF YOU WANT TO KEEP PLAYING

```python
#
#
#
def gameon_choice():
  # again we need to specify wrong choice first
  choice = "wrong"
  # and we will ask Y or N until we get the correct answear
  while choice not in ['Y', 'N']:
    choice = input("pick Y or N ")

    # if wrong choice we will print its wrong
    if choice not in ['Y', 'N']:
      print("only Y or N accepted ")

  # now we returning one choice either Y or N so we need if statement here
  if choice =='Y':
    return True
  else:
    return False
```

![](./pngs/userinput04.png)

5) NOW PUT ALL TOGETHER

```python
# first declare that game on is true
game_on = True
# and declare our list
game_list = [1,2,3]
# while gameon is true we display the game with current game list

while game_on: # since we have boolean we dont have to do "while game_on == True:"
  display_game(game_list)
  # we want to hvae display position function now where
  position = position_choice()
  # so once postition_choice function is called we know that player has provided position
  # we need to rewrite that position and display new game_list
  game_list = replacement_choice(game_list, position) #replacement_choice function takes in game list and postition so we need to specify it here
  # and since replacement_choice returns game_list we just reassigned all this to game_list

  # finnaly we display game with updated game_list
  display_game(game_list)

  # with while loop this would go for ever so we need to give user choice to break it
  # using gameon choice function
  game_on == gameon_choice()

```




- maybe also *pick which logs we want to check vmkernel or hostd*
**ale czy musze nad tym spedzac czas skoro mam grafana ?**



---

# STATEMENTS

## IF ELSE

![](./pngs/ifelse01.png)

## FOR LOOPS

for loops iterate over something

iterate meaning we can iterate over every element in the object, it could be:
- every element in a list
- or every character in a string,
- for every line in document,
- or iterate every key in dictionary

and for loops are used to iteration

![](./pngs/ifelse02.png)

for every item in items name we execute code (print item in this example)


![](./pngs/ifelse03.png)

with tuple unpacking we have acces to individual items

![](./pngs/ifelse04.png)

![](./pngs/ifelse05.png)

and example on how to iterate through dictionary
- by default it iterates by keys

![](./pngs/ifelse06.png)

- simirarly with dictionayrs if we dont match the structuire with a,b == key:value pairs we will iterate through all of it
- by default if we iterate throught dictionary we get keys
- but when we declare that we have two values a,b in d.items(), note we use function to get the items from dictionary
  - we can manipulate and get ony keys or only values from our dictionary
- this is also tuple unpacking at work
- but remember: dictionarys are unordered so when you iterate on large dictionary there is no guarantee you gonna get results as you put them in


## WHILE LOOPS
- while something is true continue
- but we have to remember to always put condition that will end the loop (x = x+1) so the loop ends

![](./pngs/ifelse07.png)






# BREAK CONTINUE PASS

CONTINUE:
- goes to the top of the closest enclosing loop

![](./pngs/ifelse08.png)


BREAK
- breaks out of the current closest enclosing loop

![](./pngs/ifelse09.png)

- it stops the loop when leter is equal to a


PASS:
- does nothing at all
- good as placeholder for loops or functions that dot work yet but with pass python wont break your code



---


# LISTS

- lists are declared with []
- list is a container object for other objects
- list is ordered sequence of elements
- ITEMS IN LIST ARE SAVED IN INDEX POSITION,
- each element has index, 0 based index
- select items from list using that index
- what you can do with index is call object by index
- or call object +1 czyli nie dodajemy jeden tylko nastepny index:

![](./pngs/lists001.png)


```python
#
# create a list from something, anything
#
>>> andre = 'andre'
>>> andre
'andre'
>>> list('andre')
['a', 'n', 'd', 'r', 'e']
>>>


andre = ['handsome', 'dedicated', '5AC']
andre[1]
'dedicated'

# get elements from to EXCLUDING the last one, so always go one more
andre[0:1]
['handsome']

andre[0:2]
['handsome', 'dedicated']

# select last element from list:
andre[-1]
'5AC'

- lists are mutable, meaning we can change them (strings are immutable - can not be changed)
- so we can change lists inplace, without destroying the object
```python
# change handsome to fit
andre[0] = 'fit'
andre
['fit', 'dedicated', '5AC']
```



---

## LIST COMPREHENSIONS
- logic here is essentially flattened out for loop
- element for element in itterable object:

![](./pngs/list_comprehensions01.png)

- list comprehension takes this element for elemnt in a list
-  if we want to add some more logic

![](./pngs/list_comprehensions02.png)

- *if statement* it goes to the right
- letter for letter in my string ONLY IF the letter is ...easy


```python
 andre
['fit', 'dedicated', '5AC', 'dedicated', 'handsome', 'fit', 'wolf']
 [a for a in andre]
['fit', 'dedicated', '5AC', 'dedicated', 'handsome', 'fit', 'wolf']


 ['andre is '+a for a in andre]
['andre is fit', 'andre is dedicated', 'andre is 5AC', 'andre is dedicated', 'andre is handsome', 'andre is fit', 'andre is wolf']
```


---

# TUPLES
- () or nothing
- another type of container (another data structure) that is very similar to lists
- ordered
- immutable, they can not be changed once assigned
- just like lists, tupple has zero based index
- so why touples if we have lists?
  - tuples used when there is always the same data structure that wont be changed
  - but for comparison purposes
- Python, tuples are immutable sequences of elements, which means they cannot be changed after they are created. However, you can perform several operations on tuples, such as:

Accessing Elements: You can access the elements of a tuple using indexing or slicing.

Concatenation: You can concatenate two or more tuples using the "+" operator.

Repetition: You can repeat a tuple multiple times using the "*" operator.

Length: You can find the number of elements in a tuple using the "len()" function.

Membership: You can check if an element is present in a tuple using the "in" keyword.

Sorting: You can sort the elements of a tuple using the "sorted()" function.

Minimum and Maximum: You can find the minimum and maximum elements of a tuple using the "min()" and "max()" functions, respectively.

Counting: You can count the number of occurrences of an element in a tuple using the "count()" method.

Note that since tuples are immutable, you cannot modify, add, or remove elements from a tuple.






```python
andre2
('andre', 38, 'whats that')

type(andre2)
<class 'tuple'>

# getting element from tuple, just like from list, use square brackets
andre2[0]
'andre'
```

![png](pngs/data_collections1.png)


---

## SETS
- declared with {}
- comma separated elements
- unordered container of only unique values

```python
# sets
>>> andre3 = {"networking","automation","upgrades","performance","networking"}

>>> type(andre3)
<class 'set'>

>>> andre3
{'performance', 'networking', 'automation', 'upgrades'}
#
# networking only once because sets are UNIQUE
#
# getting items by index or position does not work here, because its unordered
#
>>> andre3[0]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'set' object is not subscriptable

# add / remove from set
andre3.add('APIs')
andre3.discard('APIs')


# when we have two sets we can compare them
#
#  get whats in common with INTERSECTION :
#
>>> andre3
{'performance', 'networking', 'automation', 'upgrades'}
>>> andre4
{'networking', 'automation', 'APIs'}

>>> andre3.intersection(andre4)
{'networking', 'automation'}

# UNION is a bigger set containing all elements from both
#
>>> andre3.union(andre4)
{'performance', 'networking', 'automation', 'upgrades', 'APIs'}

# DIFFERENCE
#
# this goes two ways ALL ELEMENTS THAT ARE IN 1 BUT NOT IN 2
#
>>> andre3.difference(andre4)
{'performance', 'upgrades'}
>>>
>>> andre4.difference(andre3)
{'APIs'}
>>>

# change list into set is soo easy:
>>> andre
['fit', 'dedicated', '5AC', 'dedicated', 'handsome', 'fit', 'wolf']
>>> type(andre)
<class 'list'>
>>>
>>> set(andre)
{'dedicated', 'fit', 'wolf', '5AC', 'handsome'}
```


---



# DICTIONARY
- {}
- mutable and unordered
- with **Key:Value** pairs
- you can get data from dictionary using Key or .get() method,
- **.get()** doesnt give error so when there is no value to get the program will continue



```python
>>> andre11 = {'who':'me', 'where':'here','what':'pandas','why':'to automate the job'}

>>> andre11['why']
'to automate the job'

>>> andre11.get('why')
'to automate the job'
#
# whether we dont know if the key exists in dictionary we better use .get()
#
>>> andre11['5w']
Traceback (most recent call last):>>> andre11['5w']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: '5w'
>>> andre11.get('5w')

  File "<stdin>", line 1, in <module>
KeyError: '5w'
>>> andre11.get('5w')
#
# adding stuff to dictionary
#
>>> andre11['4W'] = "this is the 4 W's dict"

>>> andre11
{'who': 'me', 'where': 'here', 'what': 'pandas', 'why': 'to automate the job', '4W': "this is the 4 W's dict"}

# remove from disctionary:
#
>>> andre11.pop('4W')
"this is the 4 W's dict"

>>> andre11
{'who': 'me', 'where': 'here', 'what': 'pandas', 'why': 'to automate the job'}
#
# dictionaries can contain any value or container, even disctionary inside of dictionary
#
andre12 = {
  'who': 'me',
  'where': 'here',
  'what': 'pandas',
  # to jest moje why i tak to wyciagamy: andre12.get('why')
  'why': {  
  'why':'to automate the job',
  'morning why':'because I always wanted to code',
  'motiv':'I want to create',
  ('andre', 'me'): {'expertise':'networking', 'good at':'upgrades', 'great at':'visionary thinking'},
  10: [15, 3],
  }
}

>>> andre12
{'who': 'me', 'where': 'here', 'what': 'pandas', 'why': {'why': 'to automate the job', 'morning why': 'because I always wanted to code', 'motiv': 'I want to create', ('andre', 'me'): {'expertise': 'networking', 'good at': 'upgrades', 'great at': 'visionary thinking'}, 10: [15, 3]}}
#
# the key can BE IMMUTABLE DATA TYPE - so tuple, or string, or int or even a dictionaries BUT NOT LISTS
#
>>> andre12
{'who': 'me', 'where': 'here', 'what': 'pandas', 'why': {'why': 'to automate the job', 'morning why': 'because I always wanted to code', 'motiv': 'I want to create', ('andre', 'me'): {'expertise': 'networking', 'good at': 'upgrades', 'great at': 'visionary thinking'}, 10: [15, 3]}}

>>> andre12.keys()
dict_keys(['who', 'where', 'what', 'why'])

>>> andre12.values()
dict_values(['me', 'here', 'pandas', {'why': 'to automate the job', 'morning why': 'because I always wanted to code', 'motiv': 'I want to create', ('andre', 'me'): {'expertise': 'networking', 'good at': 'upgrades', 'great at': 'visionary thinking'}, 10: [15, 3]}])

>>> andre12.items()
dict_items([('who', 'me'), ('where', 'here'), ('what', 'pandas'), ('why', {'why': 'to automate the job', 'morning why': 'because I always wanted to code', 'motiv': 'I want to create', ('andre', 'me'): {'expertise': 'networking', 'good at': 'upgrades', 'great at': 'visionary thinking'}, 10: [15, 3]})])
>>>
#
# getting data from dictionary - ALWAYS PROVIDE THE KEY
#
>>> andre12.get('why')
{'why': 'to automate the job', 'morning why': 'because I always wanted to code', 'motiv': 'I want to create', ('andre', 'me'): {'expertiseknownissues_logs = knownissues['logs']': 'networking', 'good at': 'upgrades', 'great at': 'visionary thinking'}, 10: [15, 3]}
```


















---

## TEST STATEMENT

**scope determines visibility of that variable name to other parts of the code**

### LEGB RULES: >>THE ORDER IN WHICH PYTHON LOOKS FOR VARIABLE NAMES <<

- **L**: local - names assigned in any way within a function and NOT declared global in that function
- **E**: Enclosing - function locals, names in the local scope of any and all functions
- **G**: Global - names assigned at the top-level of module file OR declared global in a def
- **B**:  Build-in - all Pyhthon preassigned build-in names, *open, range, sum*
![](./pngs/logic_legb02.png)


### MORE EXPLANATION:
- when you create variable in Python that variable name is stored in *namespace*
- and that variables have a scope, scope determines visibility of that variable name to other parts of the code
- FIRST python looks for the namespace in **local** variable, this names are assigned in any way within a function (def, lambda)
- NEXT in **Enclosed Function locals**  variables in function inside the function
- THAN **GLOBAL** declared at the top-level of module file or declared global in def within a file
- and LAST in **BUILD IN** functions (like print(), sum()), any function that you can call help on it is build in ```help(sum())```
- local assignments does not affect global ones even when they have the same namings

![](./pngs/logic_legb03.png)

---

![](./pngs/logic_legb01.png)

---









---

# LOGIC - nested statements and scope






---

## METHODS

[comment]: _methods

**METHOD is a function defined inside a class body, if called as an attribute of an instace of that class, method will get the instance object as its first argument, which usualy is (self)**

**METHODS ARE FUNCTIONS BUILD INTO OBJECTS**
- to find build in methods that can be used for each object just type object **.** and hit tab,


- are similar to functions, also have parenesis **()**
- methods are *always attached to object* for example method UPPER attached to object STR   
  - ```'andre'.upper()```
- you have to provide the object first, then call .method
![pic](./pngs/how_to_call_methods.png)
- and if you dont know how to use the method just call *help()* function:

```bash
help(mylist.remove)
```

![](./pngs/how_to_call_for_help.png)

- or for help go to python documentation:
  - https://docs.python.org/3/







### method vs function 

In Python, a function is a block of reusable code that performs a specific task, whereas a method is a function that belongs to an object and is called on that object. 
In other words, a method is a function that is associated with an object and operates on the data within that object, while a function is a standalone piece of code that can be used anywhere in the program.

Here's an example of a function in Python:

python
Copy code
def add_numbers(x, y):
    return x + y
This function takes two arguments, x and y, and returns their sum.

And here's an example of a method in Python:

python
Copy code
my_list = [1, 2, 3]
my_list.append(4)
Here, my_list is an object of the list class, and the append() method is called on that object to add the value 4 to the end of the list.

In summary, the key differences between methods and functions are:

A function is a standalone block of code that can be called from anywhere in the program, whereas a method is a function that is associated with an object and operates on the data within that object.
Methods are called using the dot notation (e.g., my_list.append(4)), whereas functions are called by their name (e.g., add_numbers(2, 3)).

--- 

The first parameter of each method in Python is self. This parameter refers to the instance of the class on which the method is called. It is a convention in Python to use the name self for this parameter, although you could technically use any valid variable name.

Here's an example of a simple class with a method that takes self as the first parameter:

python
Copy code
class MyClass:
    def my_method(self):
        print("Hello, world!")
In this example, my_method() takes self as its first parameter, although it does not actually use it. When the method is called on an instance of the class, Python automatically passes the instance as the first argument.

Here's an example of how you would call this method on an instance of the class:

python
Copy code
my_obj = MyClass()
my_obj.my_method() # prints "Hello, world!"
The second (and any subsequent) parameters of a method depend on the specific method and what it is designed to do. They are defined by the method author and can vary widely depending on the purpose of the method.

--- 

### method examples



- **.format()** method:
  - for substitution example:
    - ```"we will be using pythong v{}".format(3.7)``` whatever we provide in format method it will be replaced within the brackets {}
    - ```"we can do it even better with multiple Key-Word-Arguments, like {this} and {this2} and {this3}".format(this="first key word argument",this2="nother key word argument",this3="can be anything we want")```
- **.append()**



--- 

## arguments in methods

1) Positional arguments:

- Positional arguments are the most common way to pass arguments to a Python function or method. 
- When using positional arguments, the values are passed in the order that they are listed in the function or method signature. 
- Here's an example:

```python 
def greet(name, age):
    print(f"Hello, {name}! You are {age} years old.")

# Call the function using positional arguments
greet("John", 30)

# In this example, the first argument ("John") is passed as the name parameter, and the second argument (30) is passed as the age parameter. 
# The order of the arguments matters - if you swapped the order of the arguments in the function call, you would get a different resul
```

2) Named arguments:
- Named arguments allow you to specify the parameter name along with the value, so that the order of the arguments doesn't matter. 
- Here's an example:

```python 
def greet(name, age):
    print(f"Hello, {name}! You are {age} years old.")

# Call the function using named arguments
greet(name="John", age=30)
greet(age=30,name="John")
# the parameter names are explicitly specified in the function call. 
# This means that you can pass the arguments in any order, as long as you use the correct parameter names.
# - both give same result: 
Hello, Jophn! You are 30 years old
```

3) Sequential arguments:
- Sequential arguments are used when you want to pass multiple values to a single parameter as a sequence. 
- There are two types of sequences commonly used in Python - tuples and lists. 
- Here's an example:

```python 
def greet(names):
    for name in names:
        print(f"Hello, {name}!")

# Call the function using a list of names
greet(["John", "Jane", "Joe"])
# a list of names is passed as a single argument to the greet function. The function then loops through the list and greets each person individually.
```

4) Keyword arguments:
- Keyword arguments are similar to named arguments, but they allow you to pass a dictionary of parameter names and values instead of individual arguments. Here's an example:

```python 
def greet(name, age):
    print(f"Hello, {name}! You are {age} years old.")

# Call the function using keyword arguments
person = {"name": "John", "age": 30}
greet(**person)
#a dictionary containing the parameter names and values is passed to the greet function using the ** operator. The function then uses the dictionary keys as the parameter names and the values as the arguments.
```









--- 


### append with MAP() function


```python


```




```python
andre.append('pythonista')
andre
['fit', 'dedicated', '5AC', 'pythonista']


- **.pop()** removes the item by index
- **.remove()** remove by name
- **.join()** create single string from list
```python
# first thing is the separator
 andre
['fit', 'dedicated', '5AC']
''.join(andre)
'fitdedicated5AC'

'-'.join(andre)
'fit-dedicated-5AC'

'&'.join(andre)
'fit&dedicated&5AC'

' & '.join(andre)
'fit & dedicated & 5AC'
```


---


# FUNCTIONS

---

[comment]: _functions

**FUNCTION IS A block of organized, resuable code, that runs when you call it**

Too write good functions / In order to became effective programmer you need to know about control flow, loops and other Python logic

**Basicaly the main point of functions is to execute block of (reusable) code**

Functions are object that can not be passed to another object, but you can call function inside another function


![](./pngs/functions_basiscs.png)



![](./pngs/functions_basiscs2.png)

![](./pngs/functions_basiscs4.png)


THE IMPORTANCE OF **RETURN**
- allows you to save to variable
- using PRINT doesnt allow you to save to variable

![](./pngs/functions_basiscs3a.png)


---

## FUNCTIONS LOGIC


![](./pngs/functions_basiscs5.png)

KEY POINTS:
- remember about indentations
- if else block
- return has its own indentation

---

![](./pngs/functions_basiscs6.png)

KEY POINTS:
- remember about empty place holder if you want to append anything down the line

---

THE RETURN:

![](./pngs/functions_basiscs7.png)



---

RETURNING MULTIPLE ITEMS FROM FUCTION

using tuple:

![](./pngs/functions_basiscs8.png)



---
### FUNCTIONS LOGIC ALSO MEANS USING LESS CODE TO ACHIEVE SAME THING

EXAMPLE1
![](./pngs/functions_basiscs92.png)



EXAMPLE2
![](./pngs/functions_basiscs91.png)


BOTH EXAMPLES ACHIEVE THE SAME THING, BUT EXAMPLE2 USES LESS CODE, WHY ?
BECAUSE ITS UTULIZES BUILD IN FUNCTIONS

**MIN** & **MAX** FUNCTIONS TAKES MUCH LESS THAN LOOKING FOR SMALLER NUMBER WITH IF ELSE


EXAMPLE 3
- if all your checks return BOOLEAN you can use them in the same line:

![](./pngs/functions_basiscs93.png)






---

## TYPES OF FUNCTIONS:

1. user defined functions  
2. Build-in functions
3. Lambda Functions
  - hey are anonymous, unnamed
4. recursion functions
  - functions that calls themselves


- python has tons of build in functions
- list of build in functions: https://docs.python.org/3/library/functions.html
- most commonly used functions: https://www.positronx.io/useful-python-built-in-functions-and-methods-list/


 

**hasattr()** 

hasattr() is a built-in function in Python. It is not a method because it does not belong to any specific object or class. Instead, it is a function that takes two arguments: an object and a string representing the name of an attribute or method. The function returns True if the object has the attribute or method with the given name, and False otherwise. Here's an example:

python
Copy code
class MyClass:
    def __init__(self):
        self.x = 1

my_obj = MyClass()
print(hasattr(my_obj, 'x')) # True
print(hasattr(my_obj, 'y')) # False
In this example, hasattr() is called with my_obj as the object and 'x' and 'y' as the attribute names. Since my_obj has an attribute called x, hasattr(my_obj, 'x') returns True, while hasattr(my_obj, 'y') returns False because my_obj does not have an attribute called y.




```python
# and few examplese here
>>> len(andre)
3
>>> min(andre)
'5AC'
>>> max(andre)
'fit'
>>> sorted(andre)
['5AC', 'dedicated', 'fit']
```


- another example of function:


```python
def moja_funkcja()

#tutaj define if function is expected to take any arguments, we call this argument as we want )  # function header

  # here in the body we do the job:

  return avg

# call the function by its name and provide
moja_funkcja()  

# jesli funkcja is expecting argument we need to give it to it

```

## functions ARGS & KWARGS

**ARGS**
- pass as many arguments as you want to your function
- example below shows that
![](./pngs/functions_basis_args.png)

- **args** can be any word actualy, as long as you have start before it it will work

![](./pngs/functions_basis_args2.png)

**KWARGS**
- same as args just creates dictionary instad of tuples



- we can also mix them toghether,
- **the thing is you have to use them in this order args, kwargs**
![](./pngs/functions_basis_args3.png)


---


# GENERATORS

- generator functions allow us to write a function that send back a value and later resume to pick up where it left off
- generators allow us to create sequence of values over time, so we dont have to create whole sequence at once and hold it in memory
- **yield** is a key word here
- with generators you dont declare any variable like you usualy do with functions (top of the functions, a holder if you will), so its not stored in memory

code example:

```python
# generate square number of N
def gensquares(N):
  # notis here we dont specify any holder for the squres, just for loop
  for i in range(N):
    yield i**2
# but this doesnt print it, and if you just call the function you will get the space in memory
# so next step is print each generated squaere with another for loop
for x in gensquares(5):
  print(x)
```


---

# DECORATORS

![](./pngs/decorator01.png)

- DECORATORS ALLOW YOU TO DECOTRATE THE FUNCTION
  - decorators allows you to add extra functionality to any existing function
  - decorators are used with **@** sign and are placed on top of original function
  - and than you can delete just one line from decorator if you dont need that extra functionality any more

BEFORE WE GET INTO DECORATORS, LETS SEE HOW WE CAN USE / CALL FUNCTION WITHIN FUNCTIONS:

FIRST WE RETURN FUNCTION:


![](./pngs/decorator03.png)

- functions must return something
- functions must be called within
- calling them outside of their indentention wont work

![](./pngs/decorator04.png)

- a little bit more logic here, that if/else returns one or other func
- once func returned and assigned to new object it can be called


NOW, EXAMPLE OF PASSING FUNCTION AS ARGUMENT:

![](./pngs/decorator05.png)

NOW, THE DECORATOR PART:

![](./pngs/decorator06.png)

- DECORATORS USED IN OTHERFRAMEWORK , LIKE IN FLASK ,
  - framework is software library that provides generic functionality which can be used to build applications, flask & django frameworks for web developement.

---


# class 

```python 
class ClassName:
    class_attribute = "value" # class attribute

    def __init__(self, arg1, arg2):
        self.instance_attribute1 = arg1 # instance attribute
        self.instance_attribute2 = arg2 # instance attribute

    def instance_method(self, arg):
        # instance method
        pass

    @classmethod
    def class_method(cls, arg):
        # class method
        pass

    @staticmethod
    def static_method(arg):
        # static method
        pass
```
A class is defined using the class keyword, followed by the class name and a colon.
Class attributes are defined at the top level of the class definition.
The __init__() method is the constructor for the class and is called when an instance of the class is created. It takes the self parameter (which refers to the instance being created) and any other required arguments.
Instance attributes are defined in the __init__() method.
Instance methods take the self parameter and can operate on instance attributes.
Class methods are defined using the @classmethod decorator and take the cls parameter (which refers to the class itself).
Static methods are defined using the @staticmethod decorator and do not take any special parameters.






In Python, a class is a blueprint for creating objects with certain properties and behaviors. The __init__ method is a special method that gets called when an object of the class is created. It is used to initialize the object's attributes.

(self, val) are the parameters of the __init__ method. self is a reference to the object being created, and val is a value that is used to set the val attribute of the object.

self.val = val sets the val attribute of the object to the value passed in as a parameter to the __init__ method.

get(self) and show(self) are also methods of the class. get returns the value of the val attribute, and show prints the value of the val attribute to the console.

Because get and show are methods of the same class, they can be accessed using the self keyword within the class. For example, you could call self.get() or self.show() within another method of the same class to retrieve or display the value of the val attribute.

Here is an example of how this class might be used:

```python 
class MyClass:
    def __init__(self, val):
        self.val = val

    def get(self):
        return self.val

    def show(self):
        print(self.val)

# Create an object of the class
my_object = MyClass(42)

# Call the get method to retrieve the value of the val attribute
value = my_object.get()
print(value) # Output: 42

# Call the show method to display the value of the val attribute
my_object.show() # Output: 42
```

In this example, my_object is an instance of the MyClass class. The __init__ method is called with a value of 42, which sets the val attribute of my_object to 42. The get method is called to retrieve the value of the val attribute, and the show method is called to display the value of the val attribute to the console.


# class instance

```python 
class x:
pass
class y(x):
pass
class z(y):
pass 
x=z()
z=z()
isinstance(x,z) isinstance(z,x)

# The first three lines of code define three Python classes x, y, and z. The x class has no attributes or methods, and the y and z classes inherit from x.

# The last two lines of code create two objects, one of type z and one of type x.

# The first line creates an object of type z and assigns it to the variable x. The second line creates another object of type z and assigns it to the variable z.

# The first isinstance() call checks whether the object x is an instance of the z class. Since x was created as an instance of the z class, this call will return True.

# The second isinstance() call checks whether the object z is an instance of the x class. However, the object z was created as an instance of the z class, not the x class. Therefore, this call will return False.

# isinstance(x, z) # True
# isinstance(z, x) # False
``` 










# CLASS CONSTRUCTORS: 


In summary, the constructor is a special method in Python classes that is used to initialize instance variables when objects are created. It is always named __init__() and takes self as its first argument.



onstructor is a special method that is used to initialize objects when they are created. The constructor method is always named __init__() and it takes at least one argument, self, which refers to the instance of the class that is being created.

Here's an example of a simple Python class that has a constructor:
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```
In this example, the Person class has a constructor that takes two arguments, name and age. The constructor initializes two instance variables, self.name and self.age, with the values of the name and age arguments.

When you create an instance of the Person class, you pass in values for the name and age arguments:
```person1 = Person("Alice", 25)```

This creates a new instance of the Person class, with self referring to the new instance. The constructor initializes the name instance variable to "Alice" and the age instance variable to 25.

You can access these instance variables using dot notation:
```python 
print(person1.name)
# Output: Alice

print(person1.age)
# Output: 25
```



What is true about Python class constructors? (Choose two.)
A. there can be only one constructor in a Python class
B. the constructor cannot be invoked directly under any circumstances
C. the constructor cannot return a result other than None
D. the constructor's first parameter must always be named self

C is true because the constructor in Python is a special method named __init__() that is called when an object is created. By convention, it should not return anything other than None. If it does, a TypeError will be raised.

D is true because the first parameter of a constructor in Python must always be named self. The self parameter refers to the instance of the class that is being created, and it is used to access the object's attributes and methods.

Option A is false because although Python does not have built-in support for multiple constructors, it is possible to simulate them using default parameter values or class methods.

Option B is false because the constructor can be invoked indirectly by creating an instance of the class, and it is the constructor that initializes the object's attributes.


---



Python class constructors:

A constructor is a special method in a class that is called when an object of that class is instantiated.
In Python, the constructor method is called init().
The constructor method can take parameters that are used to set the initial state of the object.
If no constructor is defined for a class, Python provides a default constructor with no parameters.
The constructor can also perform additional setup tasks that need to be done when the object is created.
In summary, a Python class constructor is a special method that is used to initialize the object's attributes when the object is created. The constructor method is called automatically when an object is instantiated, and it can take parameters to set the initial state of the object.


In Python, if a class's components have a name that starts with two underscores (__), they are considered to be "private" to the class. This means that they are intended to be used only within the class itself and are not intended to be accessed directly from outside the class.

For example, consider the following Python class:

```python 
class MyClass:
    def __init__(self):
        self.__private_var = 10

    def my_method(self):
        print(self.__private_var)

```

In this example, the class MyClass has a private variable called __private_var, which is set to 10 in the constructor method (__init__). The class also has a method called my_method that prints the value of the private variable.


In Python, mangling is used for class attributes that one does not want subclasses to use which are designated as such by giving them a name with two or more leading underscores and no more than one trailing underscore.

The double underscore prefix in the variable name __private_var is known as "name mangling". This means that the variable is actually renamed to include the class name, making it more difficult to accidentally access the private variable from outside the class.

For example, if we try to access the private variable from outside the class like this:

```python 
my_class = MyClass()
print(my_class.__private_var)

```

We will get an AttributeError, because the variable has been renamed to _MyClass__private_var. However, we can still access the private variable using this modified name:

```python 
my_class = MyClass()
print(my_class._MyClass__private_var)
```
Although technically possible, it is generally not recommended to access private variables or methods from outside the class. Instead, you should use public methods provided by the class to access or modify the private variables or methods.


In the given code, __foo is a method that has been defined with a double underscore prefix, which makes it a private method. Private methods and attributes in Python are intended to be used within the class only and cannot be accessed directly from outside the class.

The __foo method increments the var variable by 1 and returns the new value of var. It is an instance method, which means it operates on an instance of the class.

To call the __foo method, you need to first create an instance of the class class, and then call the method on that instance. In the given code, an instance of class is created using o = class(). Then, the method is called using o.__foo().

However, since the method is a private method, it is recommended to call it using a public method that wraps around it. This can be done by defining a public method with a different name that calls the private method inside the class. For example:

```python 
class MyClass:
    var = 0 
    
    def __foo(self):
        MyClass.var += 1
        return MyClass.var 
    
    def public_foo(self):
        return self.__foo()
``` 

In this modified code, public_foo is a public method that wraps around the private __foo method. To call the method, you can create an instance of MyClass and call the public_foo method on it, like this:
```python 
o = MyClass()
print(o.public_foo())  # Output: 1
print(o.public_foo())  # Output: 2
```









---

## lambda

A lambda function is a small anonymous function.

A lambda function can take any number of arguments, but can only have one expression.

One time use function that you quyickly use it and never reference again

Anonymous function:
- we dont give it a name
- we dont start it with def keyword
- simply start with keyword lambda
-

```python
x = lambda a : a + 10
print(x(5))
```

---

## filter()

- filter() function
- filter elements based on condistions of function you pass to it
- example:
![](./pngs/functions_filter01.png)


---

# inheritance

https://stackoverflow.com/questions/29214888/typeerror-cannot-create-a-consistent-method-resolution-order-mro




```python
the rule that when declaring a sub class which inherits from 2 (or more) classes which themselves are related through inheritance, the super class (class higher up in the inheritance hierarchy) needs to be passed after the sub class (class lower in the inheritance hierarchy). Using this rule lets analyze the answer choices:

In

class a3(A, B):
    pass
when declaring class 'a3' we are passing in class A BEFORE class B even though class A is the super class while B is the sub class. Therefore this option is incorrect (remember, sub classes come before super classes!).



These options are correct:

class a1(C, D):
    pass
class a2(D, C):
    pass
because we are declaring class 'a2' and 'a1' with classes D and C, there are not directly related in the inheritance chain so their order does not matter. Consider the inheritance chain has a human analogy:
Grand parents -> Parents -> Children. It is a linear relation. Using this analogy, D will be the uncle/aunt while C will be the nephew/niece. The above rule does not apply to this 'non-linear' relation.



class a4(B, C):
    pass
is incorrect because B comes before C even though B is the super class.



class a5(A, D):
    pass
is incorrect because A is the super class and should come after D
```







---

# WEB SCRAPING

- every page is unique so no one web scarping script will to it all
- HTML contains information
- CSS contains the styling
- PYTHON uses tags to locate specific info from a page
  - using *beautifulsoup* and libraris to format it internaly
- www.toscrape.com is website specificaly designed to practice web scraping


```python
#
# install beautifulsoup and libraries
#
pip3 install requests
pip3 install lxml
pip3 install bs4
```
- now right click the page > inspect > choose which class call or other calls you want to use

```python
#
# sample scrapping
#
import requests
result = requests.get("http://www.example.com")

# in the background the requests library goes to the url and gets response from that url
# so now when we check its type:
type(result)
Out[1]: requests.models.Response

# and now we can take the result.text and the output is plain text,
# storeg in python string,
Out[2]: '<!doctype html>\n<html>\n<head>\n    <title>Example Domain</title>\n\n    <meta charset="utf-8" />\n    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />\n    <meta name="viewport" content="width=device-width, initial-scale=1" />\n    <style type="text/css">\n    body {\n        background-color: #f0f0f2;\n        margin: 0;\n        padding: 0;\n        font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;\n        \n    }\n    div {\n        width: 600px;\n        margin: 5em auto;\n        padding: 2em;\n        background-color: #fdfdff;\n        border-radius: 0.5em;\n        box-shadow: 2px 3px 7px 2px rgba(0,0,0,0.02);\n    }\n    a:link, a:visited {\n        color: #38488f;\n        text-decoration: none;\n    }\n    @media (max-width: 700px) {\n        div {\n            margin: 0 auto;\n            width: auto;\n        }\n    }\n    </style>    \n</head>\n\n<body>\n<div>\n    <h1>Example Domain</h1>\n    <p>This domain is for use in illustrative examples in documents. You may use this\n    domain in literature without prior coordination or asking for permission.</p>\n    <p><a href="https://www.iana.org/domains/example">More information...</a></p>\n</div>\n</body>\n</html>\n'
# yes just a string, so now to parse thorught this we need beautiful soup
import bs4
soup = bs4.beautifulSoup(result.text,"lxml")
# and now when we call soup the format is as on the webstie
In [7]: soup
Out[7]:
<!DOCTYPE html>
<html>
<head>
<title>Example Domain</title>
<meta charset="utf-8"/>
<meta content="text/html; charset=utf-8" http-equiv="Content-type"/>
<meta content="width=device-width, initial-scale=1" name="viewport"/>
<style type="text/css">
    body {
        background-color: #f0f0f2;
        margin: 0;
        padding: 0;
        font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;

    }
    div {
        width: 600px;
        margin: 5em auto;
        padding: 2em;
        background-color: #fdfdff;
        border-radius: 0.5em;
        box-shadow: 2px 3px 7px 2px rgba(0,0,0,0.02);
    }
    a:link, a:visited {
        color: #38488f;
        text-decoration: none;
    }
    @media (max-width: 700px) {
        div {
            margin: 0 auto;
            width: auto;
        }
    }
    </style>
</head>
<body>
<div>
<h1>Example Domain</h1>
<p>This domain is for use in illustrative examples in documents. You may use this
    domain in literature without prior coordination or asking for permission.</p>
<p><a href="https://www.iana.org/domains/example">More information...</a></p>
</div>
</body>
</html>

In [8]:
# and to grab thigs from html document use soup.select()
soup.select('title')
# by default it returns a list, because you can have more than one value returned
soup.select('title')
Out[9]: [<title>Example Domain</title>]
# say all paragrafs which are <p> in html
soup.select('p')
[<p>This domain is for use in illustrative examples in documents. You may use this
     domain in literature without prior coordination or asking for permission.</p>,
 <p><a href="https://www.iana.org/domains/example">More information...</a></p>]
# and now to get only text without the tags:
# - we select an item from list, remember its a list
# - and than we use getText() method which returns:
In [13]: soup.select('p')
    ...:
Out[13]:
[<p>This domain is for use in illustrative examples in documents. You may use this
     domain in literature without prior coordination or asking for permission.</p>,
 <p><a href="https://www.iana.org/domains/example">More information...</a></p>]

In [14]: soup.select('p')[0].getText()
    ...:
Out[14]: 'This domain is for use in illustrative examples in documents. You may use this\n    domain in literature without prior coordination or asking for permission.'

In [15]:

```
![](./pngs/web_scrapping01.png)

```python
#
# grab a page (and later parse what data you want)
#
import requests
import bs4

resource = requests.get("https://en.wikipedia.org/wiki/Linksys_WRT54G_series")
soup = bs4.BeautifulSoup(resource.text,"lxml")
# because we want to get whole class we need to select .'class'
soup.select('.toc')

[<div aria-labelledby="mw-toc-heading" class="toc" id="toc" role="navigation"><input class="toctogglecheckbox" id="toctogglecheckbox" role="button" style="display:none" type="checkbox"/><div class="toctitle" dir="ltr" lang="en"><h2 id="mw-toc-heading">Contents</h2><span class="toctogglespan"><label class="toctogglelabel" for="toctogglecheckbox"></label></span></div>
 <ul>
 <li class="toclevel-1 tocsection-1"><a href="#Hardware_and_revisions"><span class="tocnumber">1</span> <span class="toctext">Hardware and revisions</span></a>
 <ul>
 <li class="toclevel-2 tocsection-2"><a href="#WRT54G"><span class="tocnumber">1.1</span> <span class="toctext">WRT54G</span></a></li>
 <li class="toclevel-2 tocsection-3"><a href="#WRT54GS"><span class="tocnumber">1.2</span> <span class="toctext">WRT54GS</span></a></li>
 <li class="toclevel-2 tocsection-4"><a href="#WRT54GL"><span class="tocnumber">1.3</span> <span class="toctext">WRT54GL</span></a></li>
 <li class="toclevel-2 tocsection-5"><a href="#WRTSL54GS"><span class="tocnumber">1.4</span> <span class="toctext">WRTSL54GS</span></a></li>
 <li class="toclevel-2 tocsection-6"><a href="#WRT54GX"><span class="tocnumber">1.5</span> <span class="toctext">WRT54GX</span></a></li>
 <li class="toclevel-2 tocsection-7"><a href="#WRT54GP2_and_WRTP54G"><span class="tocnumber">1.6</span> <span class="toctext">WRT54GP2 and WRTP54G</span></a></li>
 <li class="toclevel-2 tocsection-8"><a href="#WRT54GX2"><span class="tocnumber">1.7</span> <span class="toctext">WRT54GX2</span></a></li>
 <li class="toclevel-2 tocsection-9"><a href="#WRT54GX4"><span class="tocnumber">1.8</span> <span class="toctext">WRT54GX4</span></a></li>
 <li class="toclevel-2 tocsection-10"><a href="#WRT51AB"><span class="tocnumber">1.9</span> <span class="toctext">WRT51AB</span></a></li>
 <li class="toclevel-2 tocsection-11"><a href="#WRT55AG"><span class="tocnumber">1.10</span> <span class="toctext">WRT55AG</span></a></li>
 <li class="toclevel-2 tocsection-12"><a href="#WTR54GS"><span class="tocnumber">1.11</span> <span class="toctext">WTR54GS</span></a></li>
 <li class="toclevel-2 tocsection-13"><a href="#WRT54G2"><span class="tocnumber">1.12</span> <span class="toctext">WRT54G2</span></a></li>
 <li class="toclevel-2 tocsection-14"><a href="#WRT54GS2"><span class="tocnumber">1.13</span> <span class="toctext">WRT54GS2</span></a></li>
 <li class="toclevel-2 tocsection-15"><a href="#WRT54GC"><span class="tocnumber">1.14</span> <span class="toctext">WRT54GC</span></a></li>
 <li class="toclevel-2 tocsection-16"><a href="#WRT54G3G/WRT54G3GV2_Mobile_Broadband_router"><span class="tocnumber">1.15</span> <span class="toctext">WRT54G3G/WRT54G3GV2 Mobile Broadband router</span></a></li>
 <li class="toclevel-2 tocsection-17"><a href="#WRT54G-TM,_WRTU54G-TM,_and_WRTU54GV2-TM"><span class="tocnumber">1.16</span> <span class="toctext">WRT54G-TM, WRTU54G-TM, and WRTU54GV2-TM</span></a></li>
 <li class="toclevel-2 tocsection-18"><a href="#WRT54G-RG"><span class="tocnumber">1.17</span> <span class="toctext">WRT54G-RG</span></a></li>
 <li class="toclevel-2 tocsection-19"><a href="#WRT54GH"><span class="tocnumber">1.18</span> <span class="toctext">WRT54GH</span></a></li>
 </ul>
 </li>
 <li class="toclevel-1 tocsection-20"><a href="#Third-party_firmware_projects"><span class="tocnumber">2</span> <span class="toctext">Third-party firmware projects</span></a></li>
 <li class="toclevel-1 tocsection-21"><a href="#Hardware_versions_and_firmware_compatibility"><span class="tocnumber">3</span> <span class="toctext">Hardware versions and firmware compatibility</span></a></li>
 <li class="toclevel-1 tocsection-22"><a href="#See_also"><span class="tocnumber">4</span> <span class="toctext">See also</span></a></li>
 <li class="toclevel-1 tocsection-23"><a href="#References"><span class="tocnumber">5</span> <span class="toctext">References</span></a></li>
 <li class="toclevel-1 tocsection-24"><a href="#Further_reading"><span class="tocnumber">6</span> <span class="toctext">Further reading</span></a></li>
 <li class="toclevel-1 tocsection-25"><a href="#External_links"><span class="tocnumber">7</span> <span class="toctext">External links</span></a></li>
 </ul>
 </div>]
```

![](./pngs/web_scrapping02.png)

```python
#
# and now make it look better,
# - get rid of the tags with method .text
#
for item in soup.select('.toc'):
  print(item.text)

for item in soup.select('.toc'):
   print(item.text)

Contents

1 Hardware and revisions

1.1 WRT54G
1.2 WRT54GS
1.3 WRT54GL
1.4 WRTSL54GS
1.5 WRT54GX
1.6 WRT54GP2 and WRTP54G
1.7 WRT54GX2
1.8 WRT54GX4
1.9 WRT51AB
1.10 WRT55AG
1.11 WTR54GS
1.12 WRT54G2
1.13 WRT54GS2
1.14 WRT54GC
1.15 WRT54G3G/WRT54G3GV2 Mobile Broadband router
1.16 WRT54G-TM, WRTU54G-TM, and WRTU54GV2-TM
1.17 WRT54G-RG
1.18 WRT54GH


2 Third-party firmware projects
3 Hardware versions and firmware compatibility
4 See also
5 References
6 Further reading
7 External links
```

## webscrapping images

- images are usualy and *img* or *jpeg* or *png* they easy to find
- and those are html tags so simple soup.select('img') might work:

```python
link = requests.get("https://4kwallpapers.com/")
soup = bs4.BeautifulSoup(link.text,'lxml')
soup.select('img')
# list of all IMGs from the website:
 <img alt="Bugatti W16 Mistral, Sports cars, Hypercars, Roadster, Black cars" height="225" itemprop="thumbnail" src="https://4kwallpapers.com/images/walls/thumbs/9991.jpg" srcset="https://4kwallpapers.com/images/walls/thumbs_2t/9991.jpg 2.5x" width="400"/>,
<img alt="Phones and Mobiles" height="225" loading="lazy" src="https://4kwallpapers.com/images/walls/packs/99.jpg" width="400"/>,
<img alt="Playstore" height="60" loading="lazy" src="/images/common/playstore.png" width="200"/>]
# SRC is basicaly what we are looking for, source of the image.
# THUMBNAIL or THUMBIMAGE is a class of the images, in case you want to narow down search
# bacause its a class! we selet it with .class .thumbnail
soup.select('.thumbnail') # to nie dziawla na tej stronie...

# say we want to take 10th item from img list:
soup.select('img')[10]

Out[30]: <img alt="Lake Tahoe, Sierra Nevada mountains, Rocks, Landscape, 5K" height="225" itemprop="thumbnail" loading="lazy" src="https://4kwallpapers.com/images/walls/thumbs/9795.jpg" srcset="https://4kwallpapers.com/images/walls/thumbs_2t/9795.jpg 2.5x" width="400"/>
# assign it to variable
mypic = soup.select('img')[10]

mypic
Out[32]: <img alt="Lake Tahoe, Sierra Nevada mountains, Rocks, Landscape, 5K" height="225" itemprop="thumbnail" loading="lazy" src="https://4kwallpapers.com/images/walls/thumbs/9795.jpg" srcset="https://4kwallpapers.com/images/walls/thumbs_2t/9795.jpg 2.5x" width="400"/>
# and now we can call the source:
mypic['src']
Out[33]: 'https://4kwallpapers.com/images/walls/thumbs/9795.jpg'

# we can assign new variable to the image link:
mypiclink = requests.get('https://4kwallpapers.com/images/walls/thumbs/9795.jpg')

mypiclink
mypiclink.content     # the binary of the image :D
# and now we save it, remember to save in same format
# so open new file (with name of your choice) > in writeBinary mode (so its ready we feed it with content)
f = open('mynewpic.jpg', 'wb')
f.write(mypiclink.content)
f.close()
#now its saved locally !
In [39]: pwd
Out[39]: '/home/andre/Python'

In [40]: ls
__init__.py  level1/  main.py  mynewpic.jpg  one.py  __pycache__/  two.py
```



# books and quotes

- https://toscrape.com/
- free to learn web scraping ;)
- web scaping over multiple pages, grab multiple items

```python
#
#
#
import bs4
import requests
# example webpage:
https://toscrape.com/
# moving between pages:
https://books.toscrape.com/catalogue/page-2.html, https://books.toscrape.com/catalogue/page-3.html

# using dat format method, which is curly braces {} instead of number:
base_url = 'https://books.toscrape.com/catalogue/page-{}.html'
# with dot 20 the base url will autoamticaly be 20
base_url.format('20')
Out[3]: 'https://books.toscrape.com/catalogue/page-20.html'
# same as:
myfavpage = 10
base_url.format(myfavpage)
Out[4]: 'https://books.toscrape.com/catalogue/page-10.html'

# or the range:
for i in range(1,11):
     print(base_url.format(i))

https://books.toscrape.com/catalogue/page-1.html
https://books.toscrape.com/catalogue/page-2.html
https://books.toscrape.com/catalogue/page-3.html
https://books.toscrape.com/catalogue/page-4.html
https://books.toscrape.com/catalogue/page-5.html
https://books.toscrape.com/catalogue/page-6.html
https://books.toscrape.com/catalogue/page-7.html
https://books.toscrape.com/catalogue/page-8.html
https://books.toscrape.com/catalogue/page-9.html
https://books.toscrape.com/catalogue/page-10.html

#
# now find all books with rating 2
#
# - look for a name of the class that every rating 2 book has, that be:
# class: "star-rating Two"
#
# 1) take url
res = requests.get(base_url.format(1))
# 2) turn it into beautiful soup
soup = bs4.BeautifulSoup(res.text,'lxml')
# 3) select only books, here they are called "product_pod", and they are a class, hence .
soup.select(".product_pod")
# and this gives us all 20 products from this site 1, and if ou check how many items is on the site ? yes - 20
In stock

</p>
<form>
<button class="btn btn-primary btn-block" data-loading-text="Adding..." type="submit">Add to basket</button>
</form>
</div>
</article>,
<article class="product_pod">
<div class="image_container">
<a href="its-only-the-himalayas_981/index.html"><img alt="It's Only the Himalayas" class="thumbnail" src="../media/cache/27/a5/27a53d0bb95bdd88288eaf66c9230d7e.jpg"/></a>
</div>
<p class="star-rating Two">
<i class="icon-star"></i>
<i class="icon-star"></i>
<i class="icon-star"></i>
<i class="icon-star"></i>
<i class="icon-star"></i>
</p>
<h3><a href="its-only-the-himalayas_981/index.html" title="It's Only the Himalayas">It's Only the Himalayas</a></h3>
<div class="product_price">
<p class="price_color">Â£45.17</p>
<p class="instock availability">
<i class="icon-ok"></i>

In stock

</p>
<form>
<button class="btn btn-primary btn-block" data-loading-text="Adding..." type="submit">Add to basket</button>
</form>
</div>
</article>]
#
len(soup.select(".product_pod"))
Out[12]: 20

# if the class name has empty space in beautifulsoup you use .
# EXAMPLE: on the page its called: "star-rating Three" == beautifulSoup "star-rating.Three"
# assign all 20 items to check start
check_start = soup.select(".product_pod")
# now get first item:
check_start[0].select(".star-rating.Three")
Out[17]:
[<p class="star-rating Three">
 <i class="icon-star"></i>
 <i class="icon-star"></i>
 <i class="icon-star"></i>
 <i class="icon-star"></i>
 <i class="icon-star"></i>
 </p>]

# GETTING TITLE:
# - example how the html code looks like, and we looking for title:
</p>
<form>
<button class="btn btn-primary btn-block" data-loading-text="Adding..." type="submit">Add to basket</button>
</form>
</div>
</article>,
<article class="product_pod">
<div class="image_container">
<a href="its-only-the-himalayas_981/index.html"><img alt="It's Only the Himalayas" class="thumbnail" src="../media/cache/27/a5/27a53d0bb95bdd88288eaf66c9230d7e.jpg"/></a>
</div>
<p class="star-rating Two">
<i class="icon-star"></i>
<i class="icon-star"></i>
<i class="icon-star"></i>
<i class="icon-star"></i>
<i class="icon-star"></i>
</p>
<h3><a href="its-only-the-himalayas_981/index.html" title="It's Only the Himalayas">It's Only the Himalayas</a></h3>
# title is included in <a href so we looking for an "a"
<div class="product_price">
<p class="p

# first, assign first item from check_start to example:
example = check_start[0]
# now working on that one particular example we can get .select() function working
example.select('a')
[<a href="a-light-in-the-attic_1000/index.html"><img alt="A Light in the Attic" class="thumbnail" src="../media/cache/2c/da/2cdad67c44b002e7ead0cc35693c0e8b.jpg"/></a>,
 <a href="a-light-in-the-attic_1000/index.html" title="A Light in the Attic">A Light in the ...</a>]
# a href has two reurns here 1-is an image 2-is title

# thats why we gettig item 2 czyli indext 1 and grabbing 'title' - yes in beautifulSoup it has tags...
example.select('a')[1]['title']
'A Light in the Attic'
```

- WHOLE EXAMPLE IN ONE GO:

```python3
In [39]: # first we declare empty list

In [40]: two_start_titles = []

In [41]: # the loop to go from page 1 to page 50

In [42]: for n in range(1,51):
    ...:     # setting up scrape url with that number
    ...:     scrape_url = base_url.format(n)
    ...:     # now make the request with url from above
    ...:     res = requests.get(scrape_url)
    ...:
    ...:     # call soup and lxml as engine:
    ...:     soup = bs4.BeautifulSoup(res.text,'lxml')
    ...:     # recall list of books:
    ...:     books = soup.select(".product_pod")
    ...:
    ...:     # now filter out through the books
    ...:     for book in books:
    ...:         # check if two stars:
    ...:         if 'star-rating Two' in str(book):
    ...:             # so if it is there we grab the title:
    ...:             book_title = book.select('a')[1]['title']
    ...:             # and append book title to two star titles:
    ...:             two_start_titles.append(book_title)
    ...:
    ...:

In [43]: two_start_titles
Out[43]:
['Starving Hearts (Triangular Trade Trilogy, #1)',
 'Libertarianism for Beginners',
 "It's Only the Himalayas",
 'How Music Works',
 'Maude (1883-1993):She Grew Up with the country',
 "You can't bury them all: Poems",
 'Reasons to Stay Alive',
 'Without Borders (Wanderlove #1)',
 'Soul Reader',
 'Security',
 'Saga, Volume 5 (Saga (Collected Editions) #5)',
 'Reskilling America: Learning to Labor in the Twenty-First Century',
 'Political Suicide: Missteps, Peccadilloes, Bad Calls, Backroom Hijinx, Sordid Pasts, Rotten Breaks, and Just Plain Dumb Mistakes in the Annals of American Politics',
```

- and here too:

![](./pngs/web_scrapping03.png)


---

#  webscraping project
- price comparison
- reddit scrapping for posts about ?
  - crytpo ?
  - cos innego ?
  - hacker news ?
- news from few pages ?
- job search portal
  - glassdoor
  - linked in
  - jobs.ie
- security:
  - download blacklisted IPs and put them on router ?
  - https://www.abuseipdb.com/
  - https://pgl.yoyo.org/as/iplist.php?ipformat=iptables
  -

```python
#
#
#
import requests
import bs4
website = requests.get('https://pgl.yoyo.org/as/iplist.php?ipformat=iptables')
soup = bs4.BeautifulSoup(website.text,'lxml')


# linux
wget https://pgl.yoyo.org/as/iplist.php?ipformat=iptables -O iplist.txt
```













---

# BeautifulSoup program 1

```python
#
#
# imports
import requests
import bs4
# link
url = 'https://quotes.toscrape.com/'
request = requests.get(url)
# get all authors from first page, there are duplicate authors so we use SET instead of LIST
soup = bs4.BeautifulSoup(request.text,'lxml')
# now, figure out what is the class call to get names:
soup.select('.author')
# because we want unique, we set empty set first
authors = set()
for name in soup.select('.author'):
  authors.add(name.text)
#
#
# next get all quotes from first page,
# - this is very similar so the loop be similar to above one:
# - class for quotes is called text
quotes = []
for quote in soup.select('.text'):
  quotes.append(quote.text)
#
#
#
# now, about multipages:
# - base url:
url = 'https://quotes.toscrape.com/page/'
# - adding pages at the end:
authors = set()
for page in range(1,10):
  # can not add int to string so convert page number as string
  page_url = url+str(page)
  # now make request for that page
  res = requests.get(page_url)
  soup = bs4.BeautifulSoup(res.text,'lxml')

  # so now from all that pages getting names of authors, same loop:
  for name in soup.select('.author'):
    authors.add(name.text)
#
#
#
# NOW THE SAME WITH WHILE LOOP IF WE DONT KNOW HOW MANY PAGES IS THERE:
# - we knkow that when quoting page that is not found the website displays "No quotes found!"-use that
page_still_valid = True
authors = set()
page = 1

while page_still_valid:

  page_url = url+str(page)

  res = requests.get(page_url)

  if "No quotes found!" in res.text:
    break

  soup = bs4.BeautifulSoup(res.text,'lxml')

  for name in soup.select('.author'):
    authors.add(name.text)

  page = page+1
```











---

# IMAGES

- zacznij od ```pip3 install pillow``` library
- PIL python image library hence pillow
- https://pillow.readthedocs.io/en/stable/ <-- RTFM
- not displayed in ipython :(




---

# PDF & SPREEDSHEETS

- python can read PDFs and spreadsheets
- CSV comma separated output
- you can use google spreadsheets with python api
- not all PDFs can be readable with python because many of PDFs are encapsulated and displayed in fixed-layout flat document
- also PDFs has different fonts, images, tables etc which is all hard to read for python
- for PDFs use ```PyPDF2``` library


```python
#
# PDF
#

# open pdf as read binary
f = open('Coffee_Break_Python.pdf', 'rb')

# now craete new var and call the pypdf2 library for the file
pdf_reader = PyPDF2.PdfReader(f)

# check how many pages:
len(pdf_reader.pages)
89

# if you want to read pages or search through pages you need to pass them from pypdf2 into python
get_page = pdf_reader.pages[10]           # provide page number
get_page_text = get_page.extract_text()   # extract the text
get_page_text                             # read the text -- if empty, means that the extraction didnt really work...
f.close()
#
#
#
# READ ALL TEXT FROM THE PDF FILE WITH LOOP:
f = open('Coffee_Break_Python.pdf', 'rb')

# place holder for the text:
pdf_text = []
# create reader object:
pdf_reader = PyPDF2.PdfReader(f)
# for loop from range of all pages:
for num in range(len(pdf_reader.pages)):
  page = pdf_reader.pages[num]
  pdf_text.append(page.extract_text())

# now we have it all in
pdf_text
# and we can call by pages from pdf_text with index
pdf_text[11]
# and to make it more readable just print it
print(pdf_text[11])
```


# CSV files

```python
import csv
dta = open('location_of_my_csv',encoding='utf-8')
csv_data = csv.reader(data)
data_lines = list(csv_data)

```







---

# PROJECT

the flow of project is simple (the code can be difficult, challenging, can do a lot of stuff in background) the idea is usualy something like this:

1) user input

2) update variables with what user has input

3) new visualization , new output










![](./pngs/project1game01.png)


step 2 - player input:

![](./pngs/project1game02.png)


step 3 - takes in board list object , a marker X or O and desired positoin number 1-9 and assigns it to the board

![](./pngs/project1game03.png)

step 4 - function that will take board and mark X or O and then checks if marker won (if we have three of teh same in one row and column and diagonal  )


step 4 - win check

```python
def win_check(board, mark):

  # check if game is won ?

  # to win we need to have three accross with same marker in all ROWS
  # if we have this case that all marks are the same we know somebody won
  return ((board[1] == mark and board[2] == mark and board[3] == mark ) or
  # we have to rerutn boolean true or false
  # and yes we can place all the above inside the parentisis and have OR statement at the end
  # now checking next row
  (board[4] == mark and board[5] == mark and board[6] == mark ) or
  # the same thing but with different code would be:
  (board[7] == board[8] == board[9] == mark ) or

  # than check if same marker is all three COLUMNS
  (board[3] == mark and board[6] == mark and board[9] == mark ) or
  (board[2] == mark and board[5] == mark and board[8] == mark ) or
  (board[1] == mark and board[4] == mark and board[7] == mark ) or
  # and of course two DIAGONALS
  (board[7] == mark and board[5] == mark and board[3] == mark ) or
  (board[9] == mark and board[5] == mark and board[1] == mark ))

  #  

display_board(test_board)
win_check(test_board, 'X')


```












# and this is the whole code for project 1

ref: https://github.com/Pierian-Data/Complete-Python-3-Bootcamp

```python
#
# Step 1: Write a function that can print out a board.
# Set up your board as a list, where each index 1-9 corresponds with a number on a number pad, so you get a 3 by 3 board representation.
#

from IPython.display import clear_output

def display_board(board):
    clear_output()  
    # have to clear output because running dispaly_board multiple times will just display all the boards

    print('   |   |')
    print(' ' + board[7] + ' | ' + board[8] + ' | ' + board[9])
    print('   |   |')
    print('-----------')
    print('   |   |')
    print(' ' + board[4] + ' | ' + board[5] + ' | ' + board[6])
    print('   |   |')
    print('-----------')
    print('   |   |')
    print(' ' + board[1] + ' | ' + board[2] + ' | ' + board[3])
    print('   |   |')

# TEST Step 1: run your function on a test version of the board list, and make adjustments as necessary

test_board = ['#','X','O','X','O','X','O','X','O','X']
display_board(test_board)


# Step 2: Write a function that can take in a player input and assign their marker as 'X' or 'O'.
# using while loops to continually ask until you get a correct answer.
def player_input():
    marker = ''

    while not (marker == 'X' or marker == 'O'):
    # while marker is NOT equal to X AND NOT equal to O
        marker = input('Player 1: Do you want to be X or O? ').upper()
        # using upper() function so the choice is alsways capital letter no matter what user provides

    if marker == 'X':
    # output here is in form of TUPLE, with Player 1 marker, player 2:
        return ('X', 'O')
    else:
        return ('O', 'X')

# TEST Step 2: run the function to make sure it returns the desired output
player_input()

# Step 3: Write a function that takes in the board list object, a marker ('X' or 'O'), and a desired position (number 1-9) and assigns it to the board.
def place_marker(board, marker, position):
    board[position] = marker


# TEST Step 3: run the place marker function using test parameters and display the modified board
place_marker(test_board,'$',8)
display_board(test_board)

# Step 4: Write a function that takes in a board and checks to see if someone has won.
def win_check(board,mark):
  # what does it mean to win ?
  # means we need to have same markers in a row, horizontly of diagnoal so they all must equal the same thing:
    return ((board[7] == mark and board[8] == mark and board[9] == mark) or # across the top
    # return always returns boolean so this return () will return eiter True or False
    (board[4] == mark and board[5] == mark and board[6] == mark) or # across the middle
    (board[1] == mark and board[2] == mark and board[3] == mark) or # across the bottom
    (board[7] == mark and board[4] == mark and board[1] == mark) or # down the middle
    (board[8] == mark and board[5] == mark and board[2] == mark) or # down the middle
    (board[9] == mark and board[6] == mark and board[3] == mark) or # down the right side
    (board[7] == mark and board[5] == mark and board[3] == mark) or # diagonal
    (board[9] == mark and board[5] == mark and board[1] == mark)) # diagonal


# TEST Step 4: run the win_check function against our test_board - it should return True
win_check(test_board,'X')


# Step 5: Write a function that uses the random module to randomly decide which player goes first. You may want to lookup random.randint() Return a string of which player went first.
import random

def choose_first():
# randomint(options to random will pick from, 0 or 1)
    if random.randint(0, 1) == 0:
        return 'Player 2'
    else:
        return 'Player 1'


# Step 6: Write a function that returns a boolean indicating whether a space on the board is freely available.
def space_check(board, position):
# get the board at that position and check if its empty string:
    return board[position] == ' '


 # Step 7: Write a function that checks if the board is full and returns a boolean value. True if full, False otherwise.
def full_board_check(board):
     for i in range(1,10):
         if space_check(board, i):
         # double negative here because we are checking 1) if space is at the i and if there is we return false to our check (if the board is full check)
             return False
     # board is full when we return true          
     return True

# Step 8: Write a function that asks for a player's next position (as a number 1-9) and then uses the function from step 6 to check if its a free position. If it is, then return the position for later use.
def player_choice(board):
    position = 0
    # while position in NOT our available position or NOT FREE, we ask player for postion
    while position not in [1,2,3,4,5,6,7,8,9] or not space_check(board, position):
        position = int(input('Choose your next position: (1-9) '))

    return position


# Step 9: Write a function that asks the player if they want to play again and returns a boolean True if they do want to play again.
def replay():

    return input('Do you want to play again? Enter Yes or No: ').lower().startswith('y')

# Step 10: whole game logic here
#
#

print('Welcome to Tic Tac Toe!')

# first we need while loop to keep playing the game
# so while true we play the game:
while True:
    # in order to play the game we need to set the boards first
    # setting board as 10 empty list
    theBoard = [' '] * 10

    # what player choose here
    player1_marker, player2_marker = player_input()

    # choose who goes first:
    turn = choose_first()
    print(turn + ' will go first.')

    # ready to play Yes or No
    play_game = input('Are you ready to play? Enter Yes or No.')

    if play_game.lower()[0] == 'y':
        game_on = True
    else:
        game_on = False

    while game_on:
        if turn == 'Player 1':
            # Player1's turn.
            # show the board to player and than let him choose position
            display_board(theBoard)
            position = player_choice(theBoard)
            # take the player his marker and place it on the position he chose:
            place_marker(theBoard, player1_marker, position)

            # now when they have choosen the marker we need to test if they won             
            if win_check(theBoard, player1_marker):
                display_board(theBoard)
                print('Congratulations! You have won the game!')
                # and if its false it means that player WON  
                game_on = False
            # else we check if board is full and no one won:
            else:
                if full_board_check(theBoard):
                    display_board(theBoard)
                    print('The game is a draw!')
                    break
                else:
                    turn = 'Player 2'

        else:
            # Player2's turn.

            display_board(theBoard)
            position = player_choice(t
