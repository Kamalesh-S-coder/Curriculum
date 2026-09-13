---
id: comprehensions
title: Comprehensions
sidebar_label: Comprehensions
sidebar_position: 5
lesson: true
isDraft: true
---
# Comprehensions
Comprehensions in Python provide a short and clear way to create new sequences from existing iterables. Basicly they are a *fancy* syntax for simple **for-loop** pattern.

## Lesson Overview {#overview}
At the end of the lesson you will know:
* What are comprehensions in Python
* How to write `list`, `dict` or `set` coprehension
* How to use conditions in coprehensions

The key to understanding list comprehensions is that they’re just `for-loops` over a collection expressed in a more terse and compact syntax.

We will start with **list coprehension** as it is most common.

## List Coprehension
Syntax for this looks like:
```python
[item for item in iterable]
```

Let's imagine we have a task of creating a list of **square** numbers from some other list of numbers. For example, let's assume we have a following list of numbers:
```python
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
```
To create a new list with **square** of all numbers in a list, we need to first get each element in the list and apply a mathematical operation on it. So it would look something like this:
```python interactive
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
squared = []
for nmb in nmb_list:
    squared.append(nmb**2)

print(squared)
```
And the result is correct, but in Python, we can do better. Let's convert our `for-loop` to **list coprehension**.
```python interactive
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
squared = [nmb**2 for nmb in nmb_list]
print(squared)
```
Result is completly the same, but our code is simpler and more concise. In this simple example we may not see the benefit, but let's add a check there, to only collect **even** numbers.

If we use **for-loop** we may do something like this.
```python interactive
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
squared_even = []
for nmb in nmb_list:
    if nmb % 2 == 0:
        squared_even.append(nmb ** 2)

print(squared_even)
```
If we use **list comprehension** it would look like this:
```python interactive
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
squared_even = [nmb ** 2 for nmb in nmb_list if nmb % 2 == 0]
print(squared_even)
```
The result is again, completly the same, but the syntax is shorter and more concise.

You do not need to worry about understanding **coprehensions** right away, but they become extremly useful the more you write your code.

Now that we learned what are list coprehensions, let's look at **dictionary coprehensions** which are very similar in syntax but allows us to create dictionaries in a similar manner.

## Dictionary Coprehension
When creating a new dictionary using dictionary comprehension, you can perform various operations using expressions to determine the data (key and/or value) that will be stored in the new dictionary.

Syntax for this looks like:
```python
{key: value for (key,value) in iterable}
```

To demonstrate this, let's imagine that you are building a currency converter. You would maybe have a dictionary representing prices in USD and need to convert them to EUR. In traditional **for-loop** you would do something like this:
```python interactive
EUR_CONV_RATE = 0.92
prices_in_usd = {'pen': 4, 'book': 15, 'keyboard': 60}
prices_in_eur = {}
for name, price in prices_in_usd.items():
    prices_in_eur[name] = round(price * EUR_CONV_RATE, 2)
print(prices_in_eur)
```
To use **dict coprehension** we would rewrite the above code to:
```python interactive
EUR_CONV_RATE = 0.92
prices_in_usd = {'pen': 4, 'book': 15, 'keyboard': 60}

prices_in_eur = {key: round(value * EUR_CONV_RATE, 2) for (key, value) in prices_in_usd.items()}

print(prices_in_eur)
```
:::tip
`round()` function rounds the numbers decimal point to specified number of places. It takes in `float` and a number of decimal places - an `integer`.
```python interactive
a = 43.24214213213
b = round(a, 2)
print(b)
```
:::

:::info
In the above code we use `EUR_CONV_RATE` to declare **constant**. Constants are just variables, but are not supposed to be changed during running of your program. They are useful for declaring things that would not change during runtime of your program, and its a convention in Python to write them in `ALL_CAPS`. Unlike some other languages, in Python, these are considered just like regular variables and Python will not stop you from changing them during runtime, so you need to consider this when writing your application.

The golden rule is: 
* If the variable will change during your application runtime, its just a variable and should be written as `variable_name`.
* If the variable will **not** change during your application runtime, then you can consider it a **constant** and write them as `VARIABLE_NAME`.

Remember that this is just a convention and it is not a rule you *must* follow.
:::

Now that we covered dictionary coprehensions, we can finally meet **set coprehensions**.

## Set Coprehension
Set comprehension works best when you want a clean transformation and you also want duplicates to disappear without extra effort. The syntax for **set coprehension** is:
```python
{expression for item in iterable}
```

For example, let's use our *squared* example from before:
```python interactive
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
squared = {nmb ** 2 for nmb in nmb_list}
print(squared)
```
We can also use conditionals to get only specific values:
```python interactive
nmb_list = [1, 2, 3, 4, 5, 6, 7, 8]
squared_even = {nmb ** 2 for nmb in nmb_list if nmb % 2 == 0}
print(squared_even)
```

:::explore
Documentation Hunting
:::

## Answer These Questions

## Exercise

## Assignment {#assignment}

## What's Next {#next-lesson}
Coprehensions are very useful in every day life as a Python programmer, but there is one thing that is universal accross all languages, so let's start a new chapter; *code organization*. First thing to learn are **functions** which enable us to write modular code.