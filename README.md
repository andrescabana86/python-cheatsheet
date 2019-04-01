# Python CheatSheet

</br>

## **Styleguide**

### Common

The standard style guide at the moment is *PEP8*  
Link: [PEP8 Style guide](https://www.python.org/dev/peps/pep-0008/)
> there is an alternative to PEP8, [The Google Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md) for google developers

***refs***

* [RealPython style guide article](https://realpython.com/python-pep8/)
* [Python guide article](https://docs.python-guide.org/writing/style/)

</br>

## **Types of variables**

### String

> Code example

```python
name="My Name"
```

> play with strings [example](https://repl.it/@andrescabana86/python-string-manipulation) :video_game:


### Numbers

> Code example

```python
age = 25
height = 1.96
dna_reference = 7+8j # this is a complex number
```

### Boolean

> Code example

```python
is_alive = True
```

### Sets

> Code example

![Python Sets](https://repl.it/@andrescabana86/python-sets)

</br>

## **Operators**

### Addition and Substraction

> Code example

```python
# add
x = 1
y = 2
result = x+y
print("result:", result) # $> result: 3

# substract
x = 5
y = 2
result = x-y
print("result:", result) # $> result: 3

# multiply
x = 1
y = 2
result = x*y
print("result:", result) # $> result: 2

# divide
x = 2
y = 2
result = x/y
rounded = x//y
print("result:", result) # $> result: 1.0
print("rounded result:", rounded) # $> rounded result: 1

# module
x = 3
y = 2
result = x%y
print("module:", result) # $> module: 1

# power
x = 2
y = 3
result = x**y
print("result:", result) # $> result: 8
```

> see working [example](https://repl.it/@andrescabana86/python-operators) :video_game:

</br>

## **Conditional operators**

### if/elif/else condition

> Code example

```python
age = 18
parent_authorization = True
if age>18:
    print("can have a drive license")
elif age>=18:
    print("can have an early drive license")
    if parent_authorization:
        print("can drive")
else:
    print("cannot drive")
```

> play with it on this [example](https://repl.it/@andrescabana86/python-conditional-operators) :video_game:

</br>

## **Logical operators**

### and/or/not operators

> Code example

```python
age = 18
parent_authorization = True
if age>=18 and parent_authorization:
    print("can have an early drive license")
    print("can drive")
else:
    print("cannot drive")

if age>=18 or parent_authorization:
    print("can drive b/c of one of the conditions")
else:
    print("cannot drive")

if not age>=18:
    print("cannot drive b/c is not adult")
```

> play with it on this [example](https://repl.it/@andrescabana86/python-logical-operators) :video_game:

</br>

## **Loops and Iterators**

### while/for

> Code example

```python
age = 3
growup_kid = True
while growup_kid:
    if age>=18:
        print("enough age to drive")
        break
    print("kid has to growup")
    age += 1
    # code will start again
    continue
    growup_kid = False

number = 0
for number in range(10):
    number = number + 1
    if number==5:
        # The break statement causes a program to
        # break out of a loop.
        print('Number before break ' + str(number))
        break
    print('Number is ' + str(number))

number = 0
for number in range(10):
    number += 1
    if number==5:
        """
        The pass statement occurring after the if conditional
        statement is telling the program to continue to run the
        loop and ignore the fact that the variable number evaluates
        as equivalent to 5 during one of its iterations.
        """
        print('Evaluate number when is ' + str(number))
        # code evaluates and continue
        pass
    print('Number is ' + str(number))
```

> play with it on this [example](https://repl.it/@andrescabana86/python-loops-and-iterators) :video_game:

</br>

## **Functions and Methods**

### Functions

> Code example

```python
"""
the main purpose of a Function is to return
something at the end. If not, then it may be
a Method that modify something somewhere
at a class or a global scope.
"""
def check_if_minor_age(age):
    return age<18

if check_if_minor_age(17):
    print("cannot drive at the city")

# fn with default params
def get_parent_authorization(authorize=False):
    return authorize

parent_authorization = get_parent_authorization(True)
is_not_kid = not check_if_minor_age(18)

if is_not_kid and parent_authorization:
    print("can drive in city town")
```

> play with it on this [example](https://repl.it/@andrescabana86/python-functions-and-methods) :video_game:

</br>

## **Output Formatting**

### Print formatting

#### Code example

```python
print("")
print ("".center(50, '#'))
print (" Print a tuple with format output ".center(50, '#'))
print ("".center(50, '#'))
tuple_two = (1, 35.4, 240, 3817.35718)
"""
The general syntax for a format placeholder is:
> %[flags][width][.precision]type
The formatting types
%d – integer
%f – float
%s – string
%x – hexadecimal
%o – octal
%r - raw data
"""
print("Number: %2d, Float: %5.2f, Int: %2d, BigFloat: %2.8f" %tuple_two)
# using format() method
print('I love {} for "{}!"'.format('Print', 'Console'))
# using format() method and refering
# a position of the object
print('{1} and {0}'.format('Console', 'Print'))
# combining positional and keyword arguments
print('First is {0}, second is {1}, and the {other}.'
    .format('Zero', 'One', other ='Other'))
# using format() method with number  
print("First:{0[0]:4.1f}, Second:{0[1]:7.3f}"
    .format(tuple_two))

print("")
print ("".center(50, '#'))
print (" Align output ".center(50, '#'))
print ("".center(50, '#'))
# Printing the left aligned
# string with "-" padding
print("The left aligned string is : ".ljust(40, '-'))
# Printing the right aligned string  
# with "-" padding
print ("The right aligned string is :".rjust(40, '-'))
```

### String Templating

> Code example

```python
# A Python program to demonstrate working of string template
from string import Template
print("")
print ("".center(50, '#'))
print (" String Templating ".center(50, '#'))
print ("".center(50, '#'))
# List Student stores the name and marks of three students
Student = [('Ram',90), ('Ankit',78), ('Bob',92)]
# We are creating a basic structure to print the name and
# marks of the students.
t = Template('Hi $name, you have got $marks marks')
for i in Student:
    print (t.substitute(name=i[0], marks=i[1]))
```

> play with it on this [example](https://repl.it/@andrescabana86/python-output-formatting) :video_game:

***refs***

* [Output formatting in Python](https://www.geeksforgeeks.org/python-output-formatting/)
* [String formatting in Python](https://www.geeksforgeeks.org/string-formatting-in-python-using/)
* [Template Class in Python](https://www.geeksforgeeks.org/template-class-in-python/)

</br>

## **Tuples, List, Dictionaries**

### Tuples

> Code example

```python
# tuples are inmutable objects
# help(tuple)
# dir(tuple) to get available methods
print("")
print ("".center(50, '#'))
print (" Play with Tuples ".center(50, '#'))
print ("".center(50, '#'))
tuple_one = ("name of person", 18, "country where it lives")
print("tuple_one:", tuple_one)
print("tuple_one length:", len(tuple_one))
print("tuple_one first elm is:", tuple_one[0])

print("")
print ("".center(50, '#'))
print (" Search into tuple ".center(50, '#'))
print ("".center(50, '#'))
if 18 in tuple_one:
    print("""tuple_one has {} in position {}"""
        .format(18, tuple_one.index(18)))

print("")
print ("".center(50, '#'))
print (" iterating over tuple with WHILE ".center(50, '#'))
print ("".center(50, '#'))
idx = 0
while idx < len(tuple_one):
    print("elm number", tuple_one[idx])
    idx+=1

print("")
print ("".center(50, '#'))
print (" iterating over tuple with FOR LOOP ".center(50, '#'))
print ("".center(50, '#'))
for value in tuple_one:
    print("for loop", value)

print("")
print ("".center(50, '#'))
print (" Get tuple from other tuple range ".center(50, '#'))
print ("".center(50, '#'))
tuple_two = (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
print("tuple_two: ", tuple_two)
print("get from 0-5", tuple_two[0:5])
print("get from :5", tuple_two[:5])
print("get from 2:5", tuple_two[2:5])
print("get from 5:", tuple_two[5:])

print("")
print ("".center(50, '#'))
print (" Iterate tuple inverted ".center(50, '#'))
print ("".center(50, '#'))
for idx in reversed(range(len(tuple_two))):
    print("value:", tuple_two[idx])
```

### Lists

> Code example

```python
# lists are mutable objects, in value and size
# help(list)
# dir(list) to get available methods
print("")
print ("".center(50, '#'))
print (" Order list of numbers ".center(50, '#'))
print ("".center(50, '#'))
list_of_numbers = [2,5,9,7,3,1,6,8]
print("unordered number list:", list_of_numbers)
print("ordered number list:", sorted(list_of_numbers))
print("reverse ordered number list:", sorted(list_of_numbers, reverse=True))
list_of_letters = ['z','d','e','l','p','a']
# to mutate the original elm use list_of_numbers.sort()
print("unordered letter list:", list_of_letters)
print("ordered letter list:", sorted(list_of_letters))
print("ordered reverse letter list:", sorted(list_of_letters,reverse=True))

print("")
print ("".center(50, '#'))
print (" Play with Lists ".center(50, '#'))
print ("".center(50, '#'))
list_one = ("jose", "peloc", 18, 1.71, "estonia")
print("list_one:", list_one)
print("list_one length:", len(list_one))
print("list_one first elm is:", list_one[0])

print("")
print ("".center(50, '#'))
print (" iterating over list with WHILE ".center(50, '#'))
print ("".center(50, '#'))
idx = 0
while idx < len(list_one):
    print("elm number", list_one[idx])
    idx+=1

print("")
print ("".center(50, '#'))
print (" iterating over list with FOR LOOP ".center(50, '#'))
print ("".center(50, '#'))
for value in list_one:
    print("for loop", value)

print("")
print ("".center(50, '#'))
print (" Get list from other list range ".center(50, '#'))
print ("".center(50, '#'))
list_two = (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
print("list_two: ", list_two)
print("get from 0-5", list_two[0:5])
print("get from :5", list_two[:5])
print("get from 2:5", list_two[2:5])
print("get from 5:", list_two[5:])

print("")
print ("".center(50, '#'))
print (" Concatenate two lists ".center(50, '#'))
print ("".center(50, '#'))
list_three = list_one+list_two
print("list_one + list_two: ", list_three)
list_four = list_one[2:] + list_two[4:7]
print("list_one[2:] + list_two[4:7]", list_four)

print("")
print ("".center(50, '#'))
print (" Search into lists ".center(50, '#'))
print ("".center(50, '#'))
location = "estonia"
if location in list_one:
    print("""list_one has {} in position {}"""
        .format(location, list_one.index(location)))

print("")
print ("".center(50, '#'))
print (" Iterate list inverted ".center(50, '#'))
print ("".center(50, '#'))
for idx in reversed(range(len(list_one))):
    print("value:", list_one[idx])
```

### Dictionaries

> Code example

```python
# dictionaries are mutable objects, in value and size
# help(dic)
# dir(dic) to get available methods
print("")
print ("".center(50, '#'))
print (" Play with Dictionaries ".center(50, '#'))
print ("".center(50, '#'))
dic_one = {
 'red': 1,
 'blue': 2,
 'green': 3,
 'yellow': 4,
 'orange': 5,
 'brown': 6,
 'purple': 7,
 'gray': 8,
 'white': 9,
 'black': 10
}
print("dic_one:", dic_one)
print("dic_one length:", len(dic_one))
print("dic_one red key is:", dic_one['red'])

print("")
print ("".center(50, '#'))
print (" iterating over dictionary with FOR LOOP ".center(50, '#'))
print ("".center(50, '#'))
print('Iterate over dic.items()')
for key, value in dic_one.items():
    print('for key: {}, value: {}'.format(key, value))
print('Iterate over dic.keys()')
for key in dic_one.keys():
    print('for key:', key)
print('Iterate over dic.values()')
for values in dic_one.values():
    print('for values:', values)
```

> play with it on this [example](https://repl.it/@andrescabana86/python-tuples-lists-diccionaries) :video_game:

</br>

## **File Manipulation**

### Local file manipulation

> Code example

```python
def read_file_by_line():
    cfile = open('data.txt', 'r')
    line = cfile.readline()
    while line!="":
        print('line content:', line)
        line = cfile.readline()
    print('end of file')
    cfile.close()

def create_file():
    cfile = open('data.txt', 'w')
    cfile.close()

def push_lines_to_file():
    cfile = open('data.txt', 'a')
    cfile.write('this is a new line\n')
    cfile.write('to see what happens in the file\n')
    cfile.write('end!\n')
    cfile.close()

create_file() # create an empty file and close
push_lines_to_file() # push new lines and close
read_file_by_line() # read line by line and close
```

> play with it on this [example](https://repl.it/@andrescabana86/python-file-manipulation) :video_game:

</br>

## **Classes and OOP**

### Class definition and use cases

> Code example

```python
import textwrap

class Person:
    # static class variables
    working = False
    can_work = False
    sleeping = False
    can_sleep = False

    def __init__(self, name, age):
        # instance variables
        self.name = name
        self.age = age
        self.is_instance = True

    # this is a instance method
    # first arg is the instance
    def can_work(self):
        return not self.sleeping

    def work(self):
        self.working = True
        return 'OK!'

    def can_sleep(self):
        return not self.working

    def sleep(self):
        self.sleeping = True
        return 'OK!'

    @property
    def is_property_of_instance(self):
        return "property value: True"

    # this is a static class method
    # it requires the decorator @classmethod
    # first arg is the class
    @classmethod
    def get_status_of_class(cls):
        text = textwrap.dedent("""\
            status of class:
              * working: {}
              * sleeping: {}
        """)
        print(text.format(cls.working, cls.sleeping))

    # this is a static method
    # it requires the decorator @staticmethod
    @staticmethod
    def static_method(is_instance=False):
        print("this is the pure static {} method\n".format(is_instance))


class Hombre(Person):
    sex = "M"

    def get_sex(self):
        return self.sex


"""
this is an example of how can we interact with classes and methods
"""
Person.get_status_of_class()
Person.static_method()
Person.static_method(True)

print("static variable 'working' from class:", Person.working)
print("static variable 'sleeping' from class:", Person.working)
print("")

print("Person.is_property_of_instance before instance", Person.is_property_of_instance)
# instance
jose = Hombre('jose', 26)
# properties can only be access within the instance object
print("Person.is_property_of_instance after instance", Person.is_property_of_instance)
print("Person.is_property_of_instance after instance (using instance object)", jose.is_property_of_instance)
print("")
print('Jose is sleeping?', jose.sleeping)
print('jose can work?', jose.can_work())
print('jose go and sleep', jose.sleep())
print('jose can work?', jose.can_work())
print('Why?, b/c is sleeping?', jose.sleeping)

print("")
print("# instrospection classes and methods")
print("jose isinstance of Hombre class", (isinstance(jose, Hombre)))
print("jose hasattr working", (hasattr(jose, "working")))
print("jose hasattr driving", (hasattr(jose, "driving")))
print("dir jose", dir(jose))


class SpecialMethodsClass():
    """
    this is a special method
    it has been called before __init__ constructor
    """
    def __new__(cls):
        print("__new__ special method called!")
        return super().__new__(cls)

    """
    this is a special method
    it has been called before __init__ constructor
    """
    def __init__(self):
        print("__init__ special constructor called!")

print("")
test_special_class = SpecialMethodsClass()
```

> play with it on this [example](https://repl.it/@andrescabana86/python-classes-and-oop) :video_game:

## **Polimorphism**

### Demostration of a polimorphism game dev

> Code example

```python
"""
this is a video game where animals from different
species can move forward using polimorphism
"""
class Dog():
    def move_forward(self):
        print("dog is moving using its legs")


class Bird():
    def move_forward(self):
        print("bird is flying forward")

class Worm():
    def move_forward(self):
        print("worm is moving underground zigzagging")

def move_animal_forward(animal):
    animal.move_forward()

eeve = Dog()
pidgeotto = Bird()
caterpie = Worm()
moves_to_finish = 3

while moves_to_finish > 0:
    move_animal_forward(eeve)
    move_animal_forward(pidgeotto)
    move_animal_forward(caterpie)
    moves_to_finish -= 1
```

> play with it on this [example](https://repl.it/@andrescabana86/python-polimorphism) :video_game:

</br>

## **Traceback errors and Exeptions**

### Catching exceptions

> Code example

```python
"""
playing with the different types of built-in exceptions
more docs at -> https://docs.python.org/3/library/exceptions.html
"""
# list example
elist = [2,3]

print("".center(50, "#"))
print("the next code output an error ".ljust(50, "."))
print("print(print out of range, elist[5]) ".ljust(50, "."))
print("this is how to catch the error ".ljust(50, "."))
print("".center(50, "#"))
print("")

try:
    print("print out of range", elist[5])
except IndexError:
    print("catching IndexError: this means you are out of range on this list.")

print("")
print("".center(50, "#"))
print("this is a complete workflow exception ".ljust(50, "."))
print("".center(50, "#"))
print("")

try:
    print("I am trying to print a number:", elist[1])
except IndexError:
    print("this is going to work thus there are no exceptions to print")
else:
    print("after printing (without any exception error, this block will execute some code")
finally:
    print("this always execute some code")

try:
    print("I am trying to print a number:", elist[5])
except IndexError:
    print("this is going to fail: exception failure catched")
else:
    print("this block is not going to execute")
finally:
    print("this always execute some code")

print("")
print("".center(50, "#"))
print("catch more than one exception ".ljust(50, "."))
print("".center(50, "#"))
print("")

try:
    print("trying to print out of range")
    print("success", elist[4])
    print("trying to print type error")
    print("success", elist["a"])
except(IndexError, TypeError) as error:
    print("this catch the error, type:", error)

print("") # other block fail

try:
    print("trying to print out of range")
    print("success", elist[1])
    print("trying to print type error")
    print("success", elist["a"])
except(IndexError, TypeError) as e:
    print("this catch the error, type:", e)


print("")
print("".center(50, "#"))
print("custom exception handlers ".ljust(50, "."))
print("".center(50, "#"))
print("")


class MyException(Exception):
    def __init__(self,error):
        print("creating my exception: ", error)

try:
    raise MyException("because I said so... :)")
except MyException as error:
    print("I handle my own exception", error)

```

> play with it on this [example](https://repl.it/@andrescabana86/python-traceback-and-exceptions) :video_game:

</br>

## **Regular expressions**

### Basic use cases, search and sub

> Code example

```python
"""
work with strings

think about...
alternation |
quantity {1} ? + *
grouping ()
exclusion []

=== types of special regex chars === 
. represents a char
\n new line
/r return
\t horizontal tab
\w any char 0-9 a-z
\W any char 0-9 A-Z
\s all chars between \w and \W
\S any char except white space
\d number 0-9
\D any char exept 0-9
^ start of string or start with
$ end of string or end with
\ escape chars
[] any char inside a range are allowed
^[] any char inside a range are forbidden
\b separation between number or letter

=== meta chars ===
types of repetitions
+ one or more repetitions
* zero or more repetitions
{n} n number of repetitions 
? zero or one repetition
{n:o} min and max range of repetitions
"""

import re

regex = re.compile("\d{3}")
chain = "kilo912meter"
result = regex.search(chain)
print("chain:", chain)
print("result regex:", result)
print("result value:", result.group())
print("")

regex = re.compile("\Aa[0-9].*(end|fin)$")
chain = "S4 is the chain to test. end"
result = regex.search(chain)
print("chain:", chain)
print("result regex false:", result)
print("")

regex = re.compile("^\S[0-9].*(end|find)$")
result = regex.search(chain)
print("chain:", chain)
print("result regex true:", result)
print("result value:", result.group())
print("")

print("make a substitution, replace all numbers")
chain = "thi2s i98s a9238 com923pli8239ca92ted s798t784r367i87n556g"
regex = re.compile("\d")
result = regex.sub("", chain)
print("chain:", chain)
print("result:", result)
print("")

print("make a substitution, replace the first 5 numbers")
chain = "thi2s i98s a9238 com923pli8239ca92ted s798t784r367i87n556g"
regex = re.compile("\d")
result = regex.sub("", chain, 7)
print("chain:", chain)
print("result:", result)
print("")

print("Ignore case")
"""
IGNORECASE
ALL
MULTILINE
"""
chain = "THIS IS UNDER CONSTRUCTION"
regex = re.compile("un", re.IGNORECASE)
result = regex.search(chain)
print("chain:", chain)
print("result regex:", result)
print("result value:", result.group())
print("")

```

> play with it on this [example](https://repl.it/@andrescabana86/python-regex) :video_game:

</br>

## **XML Manipulation**

### Basic use cases xml

> Code example

```python
# node manipulation
from xml.dom.minidom import parse, Node

xml_tree = parse("catalog.xml")

print("names of plants:")
for node in xml_tree.getElementsByTagName("COMMON"):
    for child in node.childNodes:
        if (child.nodeType == Node.TEXT_NODE):
            print(child.data)
print("")
```

> play with it on this [example](https://repl.it/@andrescabana86/python-xml-manipulation) :video_game:

</br>

## **JSON Manipulation**

### Basic use cases json

> Code example

```python
# json manipulation
import json

with open("data.json") as json_file:
    data = json.load(json_file)

print(data)
print("")
print("only first key")
print(data["quiz"])

```

> play with it on this [example](https://repl.it/@andrescabana86/python-json-manipulation) :video_game:

</br>

## **Compression of files**

### Basic use cases zip files

> Code example

```python
print("zip manipulation")
from zipfile import ZipFile
with ZipFile('file.zip', 'w') as z_file:
    z_file.write('file.json')
    z_file.write('file.xml')
    z_file.printdir()
    z_file.close()

print("")
print("gzip manipulation")
import gzip
with open("file.xml", "rb") as file_to_gzip:
    with gzip.open("file.xml.gzip", "wb") as gzip_file:
        gzip_file.writelines(file_to_gzip)
        gzip_file.close()

print("")
print("bz2 manipulation")
import bz2
chain = b"chain chain chain chain chain"
bz2_chain = bz2.compress(chain)
print("original chain:", chain)
print("bz2 chain:", bz2_chain)
decompress_chain = bz2.decompress(bz2_chain)
print("decompress chain:", decompress_chain)

print("")
print("tarball manipulation")
import tarfile
tar_file = tarfile.open("file.tar.gz", "w:gz")
tar_file.add("file.json")
tar_file.add("file.xml")
tar_file.list(False)
tar_file.close()
```

> play with it on this [example](https://repl.it/@andrescabana86/python-zip-files) :video_game:

</br>

## **Reference Docs**

### Useful links

* [GeeksForGeeks articles](https://www.geeksforgeeks.org/python-programming-language/)
