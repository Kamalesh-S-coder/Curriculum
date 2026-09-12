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
Result is completly the same, but our code is simpler and more concise.

:::explore
Documentation Hunting
:::

## Answer These Questions

## Exercise

## Assignment {#assignment}

## What's Next {#next-lesson}