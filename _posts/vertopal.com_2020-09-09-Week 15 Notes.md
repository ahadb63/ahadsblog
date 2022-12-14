---
jupyter:
  kernelspec:
    display_name: Python 3.9.12 (\'base\')
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.9.12
  nbformat: 4
  nbformat_minor: 2
  orig_nbformat: 4
  vscode:
    interpreter:
      hash: ffbc78dc5ed357358f9061e93273b418d0a5d8c7f8a463c0e2f989d33fa7039d
---

::: {.cell .markdown}
# Notes Week 15

-   toc: true
-   badges: true
-   comments: true
-   categories: \[notes, 3.8, 3.10\]
:::

::: {.cell .markdown}
# 3.8 and 3.10 {#38-and-310}

## Lists

Lists: a sequence of variables

-   we can use lists to store multiple items into one variable
-   used to store collections of data
-   changeable, ordered, allow duplicates
:::

::: {.cell .code execution_count="1"}
``` {.python}
fruits = ["apple", "grape", "strawberry"]
index = 1

print (fruits[index])

# Index starts at 0 and not 1, so grape will be printed and not apple (College Board starts at 1)
```

::: {.output .stream .stdout}
    grape
:::
:::

::: {.cell .code execution_count="2"}
``` {.python}
sports = ["football", "soccer", "baseball", "golf", "basketball"]

# add "golf" as the 3rd element in the list
print (sports)
```

::: {.output .stream .stdout}
    ['football', 'soccer', 'baseball', 'golf', 'basketball']
:::
:::

::: {.cell .code execution_count="3"}
``` {.python}
sports = ["football", "hockey", "baseball", "basketball"]

# change the value "soccer" to "hockey"
print (sports)
```

::: {.output .stream .stdout}
    ['football', 'hockey', 'baseball', 'basketball']
:::
:::

::: {.cell .markdown}
-   Output of list practice is
-   unusual,
:::

::: {.cell .markdown}
# Iteration

-   Iteration is the repetition of a process or utterance applied to the
    result or taken from a previous statement.
-   Types of Iteration include using a \"for loop\", using a \"for loop
    and range()\", using a \"while loop\", and using comprehension
:::

::: {.cell .code execution_count="4"}
``` {.python}
# Using an example of iter()
a = ['alpha', 'bravo', 'charlie']

itr = iter(a)
print(next(itr))
print(next(itr))
print(next(itr))
```

::: {.output .stream .stdout}
    alpha
    bravo
    charlie
:::
:::

::: {.cell .markdown}
# Loops

-   Well, above is basically just printing them again, so how do we
    takes these iterators into something we can make use for?
-   Loops take essentially what we did above and automates it, here are
    some examples.
:::

::: {.cell .markdown}
# Iteration HW
:::

::: {.cell .code execution_count="5"}
``` {.python}
words = ["alfa", "bravo", "charlie", "delta", "echo", "foxtrot", "golf", "hotel", "india", "juliett", "kilo",
"lima", "mike", "november", "oscar", "papa", "quebec", "romeo", "sierra", "tango", "uniform", "victor", "whiskey", "xray", "yankee", "zulu"]

inp = input().lower()


itr = iter(words)

name = ["delta", "alpha", "hotel"]
d = "delta"
a = "alfa"
h = "hotel"

```
:::

::: {.cell .markdown}
# 2d List Challenge {#2d-list-challenge}
:::

::: {.cell .code execution_count="6"}
``` {.python}
print_matrix3 = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [" ", 0, " "]]

```
:::

::: {.cell .markdown}
# 3.8 and 3.10 Hacks {#38-and-310-hacks}

> hacks for 3.8 and 3.10
:::

::: {.cell .code execution_count="7"}
``` {.python}
sports = ["football", "hockey", "baseball", "basketball"]

# change the value "soccer" to "hockey"
print (sports)
```

::: {.output .stream .stdout}
    ['football', 'hockey', 'baseball', 'basketball']
:::
:::

::: {.cell .code execution_count="8"}
``` {.python}
sports = ["football", "soccer", "baseball", "golf", "basketball"]

# add "golf" as the 3rd element in the list
print (sports)
```

::: {.output .stream .stdout}
    ['football', 'soccer', 'baseball', 'golf', 'basketball']
:::
:::

::: {.cell .code execution_count="9"}
``` {.python}
keypad =   [[1, 2, 3],
            [4, 5, 6],
            [7, 8, 9],
            [" ", 0, " "]]
```
:::

::: {.cell .code execution_count="10"}
``` {.python}
def print_matrix3(matrix):
    for row in matrix:
        print(*row)

print_matrix3(keypad)
```

::: {.output .stream .stdout}
    1 2 3
    4 5 6
    7 8 9
      0  
:::
:::

::: {.cell .code execution_count="11"}
``` {.python}
def print_matrix1(matrix): 
    for i in range(len(matrix)):  
        for j in range(len(matrix[i])):  
            print(matrix[i][j], end=" ") 
```
:::

::: {.cell .code execution_count="12"}
``` {.python}
print("Raw matrix (list of lists): ")
print(keypad)
print("Matrix printed using nested for loop iteration:")
print_matrix1(keypad)
print()
```

::: {.output .stream .stdout}
    Raw matrix (list of lists): 
    [[1, 2, 3], [4, 5, 6], [7, 8, 9], [' ', 0, ' ']]
    Matrix printed using nested for loop iteration:
    1 2 3 4 5 6 7 8 9   0   
:::
:::

::: {.cell .code execution_count="13"}
``` {.python}
def print_matrix2(matrix):
    for row in matrix:  # Iterates through rows. Iterates through every value in matrix and list. 
        for col in row:  # Iterates value in row. row values stored in col.
            print(col, end=" ") 
        print() 

print_matrix2(keypad)
```

::: {.output .stream .stdout}
    1 2 3 
    4 5 6 
    7 8 9 
      0   
:::
:::

::: {.cell .code execution_count="14"}
``` {.python}
words = ["alfa", "bravo", "charlie", "delta", "echo", "foxtrot", "golf", "hotel", "india", "juliett", "kilo",
"lima", "mike", "november", "oscar", "papa", "quebec", "romeo", "sierra", "tango", "uniform", "victor", "whiskey", "xray", "yankee", "zulu"]

output = ""

for letter in inp:
    for word in words:
        if letter == word[0]: # fidns rigth words
            output += word + " " # adds space

print(inp + "\n" + output)
# input is ahad biabani
```

::: {.output .stream .stdout}
:::
:::

::: {.cell .markdown}
Print what month you were born and how old you are by iterating through
the keyboard (don\'t just write a string).
:::

::: {.cell .code execution_count="15"}
``` {.python}
keyboard = [["`", 1, 2, 3, 4, 5, 6, 7, 8, 9, 0, "-", "="],
            ["Q", "W", "E", "R", "T", "Y", "U", "I", "O", "P", "[", "]"],
            ["A", "S", "D", "F", "G", "H", "J", "K", "L", ";", "'"],
            ["Z", "X", "C", "V", "B", "N", "M", ",", ".", "/"]]
```
:::

::: {.cell .code execution_count="16"}
``` {.python}
# row column
month = keyboard[2][1] + keyboard[1][2] + keyboard[1][9] + keyboard[1][4] + keyboard[1][2] + keyboard[3][6] + keyboard[3][4] + keyboard[1][2] + keyboard[1][3]
age = str(keyboard[0][1]) + str(keyboard[0][8])

print(month[:1] + month[1:].lower())
print(age)
```

::: {.output .stream .stdout}
    September
    18
:::
:::

::: {.cell .markdown}
## NOTES
:::

::: {.cell .markdown}
VARIABLE : A variable is a named location in a computer\'s memory where
a programmer can store and retrieve data. The data stored in a variable
can be of various types, such as numbers, strings, or booleans (true or
false values).

DATA TYPE : Data types refer to the different types of data that a
variable can hold. Some common data types include integers,
floating-point numbers, strings, and booleans.

ASSIGNMENT OPERATORS : Assignment operators are used to assign a value
to a variable. For example, the equal sign (=) is an assignment operator
that is used to assign a value to a variable on the left side of the
equal sign.

LISTS : Lists are a data structure that allows a programmer to store and
manipulate multiple values in a single, ordered collection.

2D LISTS :lists are lists that contain other lists as elements. They can
be thought of as a grid, with rows and columns, where each element in
the grid is itself a list.

DICTIONARIES : Dictionaries are another data structure that allows a
programmer to store and manipulate data. Unlike lists, which are ordered
collections of data, dictionaries are unordered collections of key-value
pairs.

CLASS ALGORITHMS : A class is a concept in object-oriented programming
that allows a programmer to define a new data type. A class can contain
variables and functions (called methods) that operate on those
variables.

ALGORITHMS Algorithms are a set of steps or instructions that a computer
can follow to solve a problem or accomplish a task.

SEQUENCE : A sequence is a common control flow pattern in which a set of
instructions is executed in order, one after the other.

SELECTION : Selection is a control flow pattern in which a program only
executes certain instructions depending on whether a certain condition
is met.

ITERATION : Iteration is a control flow pattern in which a set of
instructions is executed repeatedly until a certain condition is met.
This is often accomplished using a looping construct, such as a for loop
or a while loop.
:::

::: {.cell .code execution_count="17"}
``` {.python}
x = 3
y = 4
print(x + y)
print ("variable example")
```

::: {.output .stream .stdout}
    7
    variable example
:::
:::

::: {.cell .code execution_count="18"}
``` {.python}
# This is a variable with an integer data type
my_var = 10

# This is a variable with a floating-point data type
my_other_var = 10.5

# This is a variable with a string data type
my_string = "Hello, world!"
 

print("data type examples")
```

::: {.output .stream .stdout}
    data type examples
:::
:::

::: {.cell .code execution_count="19"}
``` {.python}
# This is a variable that is assigned the value 10
my_var = 10

# This is a variable that is assigned the value of another variable
my_other_var = my_var

print("assignment operator example")
```

::: {.output .stream .stdout}
    assignment operator example
:::
:::

::: {.cell .code execution_count="20"}
``` {.python}
# This is a list of strings
my_list = ["apple", "banana", "orange"]

# This is a list of integers
my_other_list = [1, 2, 3, 4, 5]

# This is an empty list
my_empty_list = []

print("list examples")
```

::: {.output .stream .stdout}
    list examples
:::
:::

::: {.cell .code}
``` {.python}
```
:::

::: {.cell .markdown}
# 3.12 - 3.13 Notes {#312---313-notes}
:::

::: {.cell .markdown}
-   ## Calling Procedures

Slide 1:

-   A (procedure) is a named group of programming instructions that may
    have parameters and return values.
-   Procedures are referred to by different names, such as (method) or
    (function), depending on the programing language.
-   Parameters are input values of a procedure. (arguments) specify the
    values of the parameters when procedure is called.
-   A procedure call interrupts the sequential execution of statements
    causing the program to execute the statements within the procedure
    before continuing. One the last statement in the procedure (or a
    return statement) has executed, flow or control is returned to the
    point immediately following where the procedure was (called).

Slide 2:

-   When calling procedures, it\'s important to take notice to whether
    it returns data, or a block of (statements).
-   If the procedure just returns a block of statements, you call the
    procedure by referring to the procedure name, and (input) the
    arguments.
-   If the procedure returns some sort of data like a (boolean) or
    (value), then you will assign that value to a variable

Slide 3:

-   Assume the Temperature outside is Fahrenheit.
-   The procedure convertFahrenheit is intended to convert from
    Fahrenheit to Celsius.
-   Convert the following psuedocode to python
:::

::: {.cell .markdown}
-   ## Developing Procedures

Slide 8:

Picking a descriptive name is important in case you revisit the code
later on (separate words with capitals) There are 2 different types of
procedures- ones that return a value and those that simply execute a
block of statements Steps of developing procedure: picking a useful
name, thinking of parameters (what data does the procedure need to
know), making a flowchart or writing procedure in pseudocode, and
actually developing the procedure.

Slide 9:

In this example, a teacher is writing a program that will replace the
grade on a previous quiz if the new grade is better than the previous.

    What would be a good name for this procedure?
    What parameters do we need for this procedure?
    Try writing this procedure out in python based on the given pseudocode
:::

::: {.cell .code}
``` {.python}
quizGrade = 0
currentPoints = 100
def replace_quiz_grade(currentPoints):
    global quizGrade
    currentGrade = currentPoints / 40
    currentGrade = currentGrade * 100
    if currentGrade > quizGrade:
        quizGrade = currentGrade
        
print(quizGrade)
replace_quiz_grade(currentPoints)
print(quizGrade)
```
:::

::: {.cell .markdown}
3.12-3.13 Homework and hacks
:::

::: {.cell .code execution_count="2"}
``` {.python}
def grade_tracker():
  math_grade = input("What is your current grade in Math? ")
  chemistry_grade = input("What is your current grade in Chemistry? ")
  computer_science_grade = input("What is your current grade in Computer Science? ")
  history_grade = input("What is your current grade in History? ")

  print("Here are your current grades:")
  print("Math: " + math_grade)
  print("Chemistry: " + chemistry_grade)
  print("Computer Science: " + computer_science_grade)
  print("History: " + history_grade)

grade_tracker()
```

::: {.output .stream .stdout}
    Here are your current grades:
    Math: 90
    Chemistry: 90
    Computer Science: 90
    History: 82
:::
:::

::: {.cell .markdown}
\# 3.16 HW
:::

::: {.cell .code execution_count="3"}
``` {.python}
# Define the initial position and velocity of the object
pos = 0
vel = 5 

# Define the time step (in seconds)
dt = 0.1

# Simulate the motion of the object
while pos >= 0:
    # Update the position of the object
    pos += vel * dt
    print(f"Position: {pos}")

    # Update the velocity of the object (assuming constant acceleration)
    vel += -9.81 * dt

# Print a message when the object hits the ground
print("The object has hit the ground!")

# This simulation models the motion of an object under the influence of gravity.
#  It updates the position and velocity of the object at each time step, using a simple kinematic equation.
#  The simulation continues until the object hits the ground (i.e., its position becomes negative), at which point it prints a message.
```

::: {.output .stream .stdout}
    Position: 0.5
    Position: 0.9019
    Position: 1.2057000000000002
    Position: 1.4114000000000002
    Position: 1.5190000000000001
    Position: 1.5285000000000002
    Position: 1.4399000000000002
    Position: 1.2532
    Position: 0.9684000000000001
    Position: 0.5855000000000001
    Position: 0.10450000000000015
    Position: -0.4745999999999998
    The object has hit the ground!
:::
:::
