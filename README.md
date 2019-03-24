# Python CheatSheet

<br>

## **Styleguide**
The standard style guide at the moment is *PEP8*  
Link: [PEP8 Style guide](https://www.python.org/dev/peps/pep-0008/)
> there is an alternative to PEP8, [The Google Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md) for google developers

<br>

## **Types of variables**
### String
#### Code example
```python
name="My Name"
```

### Numbers
#### Code example
```python
age = 25
height = 1.96
dna_reference = 7+8j # this is a complex number
```

### Boolean
#### Code example
```python
is_alive = True
```

<br>

## **Operators**
### Addition and Substraction
#### Code example
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

<br>

## **Conditional operators**
### if/elif/else condition
#### Code example
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

<br>

## **Logical operators**
### and/or/not operators
#### Code example
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

<br>

## **Loops and Iterators**
### while/for
#### Code example
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

<br>

## **Functions and Methods**
### and/or/not operators
#### Code example
```python

```
> play with it on this [example](https://repl.it/@andrescabana86/python-functions-and-methods) :video_game:

<br>

## **Reference**
### Useful links
#### &ensp;&ensp; Style guide
* [RealPython style guide article](https://realpython.com/python-pep8/)
* [Python guide article](https://docs.python-guide.org/writing/style/)
