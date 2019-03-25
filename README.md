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

## **Tuples, List, Dictionaries**

### Tuples

> Code example

```python
# tuples are inmutable objects
tuple_one = (
    "name of person",
    18,
    "country where it lives"
)
print("tuple_one first elm is:", tuple_one[0])

# iterate over tuples
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
```

### Lists

> Code example

```python

```

> play with it on this [example](https://repl.it/@andrescabana86/python-tuples-lists-diccionaries) :video_game:

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

***refs***

* [Output formatting in Python](https://www.geeksforgeeks.org/python-output-formatting/)
* [String formatting in Python](https://www.geeksforgeeks.org/string-formatting-in-python-using/)
* [Template Class in Python](https://www.geeksforgeeks.org/template-class-in-python/)

</br>

## **Reference Docs**

### Useful links

* [GeeksForGeeks articles](https://www.geeksforgeeks.org/python-programming-language/)
