<div align="center">
  <h1> 30 Days Of Python: Day 12 - List Comprehension</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> First Edition: Nov 22 - Dec 22, 2019</small>
</sub>

</div>
</div>

[<< Day 12](../12_Day/12_module.md) | [Day 14>>](../14_Day/14_higher_order_function.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [📘 Day 13](#%f0%9f%93%98-day-13)
  - [List Comprehension](#list-comprehension)
  - [Lambda Function](#lambda-function)
    - [Creating a lambda function](#creating-a-lambda-function)
    - [Lambda function inside other function](#lambda-function-inside-other-function)
  - [💻 Exercises: Day 13](#%f0%9f%92%bb-exercises-day-13)

# 📘 Day 13

## List Comprehension

List comprehension in Python is a compact way of creating a list from a sequence. It is a short way to create a new list. List comprehension is considerably faster than processing a list using the for loop.

```py
# syntax
[i for i in iterable if expression]
```

**Example:1**

For instance if you want to change a string to a list of characters. You can use a couple methods. Let's see some of them

```py
# One way
language = 'Python'
lst = list(language) # changing the string to list
print(type(lst))     # list
print(lst)           # ['P', 'y', 't', 'h', 'o', 'n']

# Second way: list comprehension
lst = [i for i in language]
print(type(lst)) # list
print(lst)       # ['P', 'y', 't', 'h', 'o', 'n']

```

**Example:2**

For instance if you want to generate a list of numbers

```py
# Generating numbers
numbers = [i for i in range(11)]  # to generate number from 0 to 10
print(numbers)                    # [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# It is possible to do mathematical operation during iteration
squares = [i * i for i in range(11)]
print(squares)                    # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

# It is possible to do mathematical operation during iteration
numbers = [(i, i * i) for i in range(11)]
print(numbers)                             # [(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]

```

**Example:2**
List comprehension can be combined with if expression

```py
# Generating even numbers
even_numbers = [i for i in range(21) if i % 2 == 0]  # to generate even number between 0 to 21
print(even_numbers)                    # [0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# Generating odd numbers
odd_numbers = [i for i in range(21) if i % 2 != 0]  # to generate odd number between 0 to 21
print(odd_numbers)                      # [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
# Filter numbers: let's filter positive and even numbers from the list below
numbers = [-8, -7, -3, -1, 0, 1, 3, 4, 5, 7, 6, 8, 10]
positive_even_numbers = [i for i in range(21) if i % 2 == 0 and i > 0]
print(positive_even_numbers)                    # [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]

# Flattening two dimensional array
two_dimen_list = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened_list = [ number for row in two_dimen_list for number in row]
print(flattened_list)    # [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## Lambda Function

Lambda function is a small anonymous function without name.A lambda function can take any number of arguments, but can only have one expression. Lambda function is similar to anonymous function in JavaScript. We need lambda function when we want to write an anonymous function inside another function.

### Creating a lambda function

To create a lambda function we use _lambda_ keyword followed by parameter, followed by expression. See the syntax and the example below. Lambda function do not use return but it explicitly return the expression.

```py
# syntax
x = lambda param1, param2, param3: param1 + param2 + param2
print(x(arg1, arg2, arg3))
```

**Example:**

```py
# Named function
def add_two_nums(a, b):
    return a + b

print(2, 3)     # 3
# Lets change the above function to lambda function
add_two_nums = lambda a, b: a + b
print(add_two_nums(2,3))    # 5

# Self invoking lambda function
(lambda a, b: a + b)(2,3) # 5

square = lambda x : x ** 2
print(square(3))    # 9
cube = lambda x : x ** 3
print(cube(3))    # 27

# Multiple variables
multiple_variable = lambda a, b, c: a ** 2 - 3 * b + 4 * c
print(multiple_variable(5, 5, 3))
```

### Lambda function inside other function

Using lambda function inside another function.

```py
def power(x):
    return lambda n : x ** n

cube = power(2)(3) # 8
two_power_of_five = power(2)(5) # 32
```

## 💻 Exercises: Day 13

1. Filter only negative or zero in the list using list comprehension
   ```py
   numbers = [-4, -3, -2, -1, 0, 2, 4, 6]
   ```
1. Flatten the following list of lists of lists to a one dimensional list :

   ```py
   list_of_lists =[[[1, 2, 3]], [[4, 5, 6]], [[7, 8, 9]]]

   output
   [1, 2, 3, 4, 5, 6, 7, 8, 9]
   ```

1. Using list comprehension create the following list of tuples:
   ```py
   [(0, 1, 0, 0, 0, 0, 0),
   (1, 1, 1, 1, 1, 1, 1),
   (2, 1, 2, 4, 8, 16, 32),
   (3, 1, 3, 9, 27, 81, 243),
   (4, 1, 4, 16, 64, 256, 1024),
   (5, 1, 5, 25, 125, 625, 3125),
   (6, 1, 6, 36, 216, 1296, 7776),
   (7, 1, 7, 49, 343, 2401, 16807),
   (8, 1, 8, 64, 512, 4096, 32768),
   (9, 1, 9, 81, 729, 6561, 59049),
   (10, 1, 10, 100, 1000, 10000, 100000)]
   ```
1. Change the following list to a flatten list:
   ```py
   countries = [[('Finland', 'Helsinki')], [('Sweden', 'Stockholm')], [('Norway', 'Oslo')]]
   output:
   ['FINLAND', 'HELSINKI', 'SWEDEN', 'STOCKHOLM', 'NORWAY', 'OSLO']
   ```
1. Change the following list to a list of dictionaries:
   ```py
   countries = [[('Finland', 'Helsinki')], [('Sweden', 'Stockholm')], [('Norway', 'Oslo')]]
   output:
   [{'country': 'FINLAND', 'city': 'HELSINKI'},
   {'country': 'SWEDEN', 'city': 'STOCKHOLM'},
   {'country': 'NORWAY', 'city': 'OSLO'}]
   ```
1. Change the following list of lists to flat list:
   ```py
   names = [[('Asabeneh', 'Yetaeyeh')], [('David', 'Smith')], [('Donald', 'Trump')], [('Bill', 'Gates')]]
   output
   ['Asabeneh Yetaeyeh', 'David Smith', 'Donald Trump', 'Bill Gates']
   ```
1. Write a lambda function which can solve slope or y-intercept.

🎉 CONGRATULATIONS ! 🎉

[<< Day 12](../13_Day/13_list_comprehension.md) | [Day 15>>](../15_Day/15_python_type_error.md)
