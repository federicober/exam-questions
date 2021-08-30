# exam-questions

The one interview you don't want to stumble upon.

## Python

---

**Q:** What is the difference between multi-threading, multi-processing and asynchronous? How does Python differ from other programming languages?

---

**Q:** What is the space-complexity of `range(n)` in Python3? Is it the same in Python2? Why?

---

**Q:** What is a `Sequence` in Python?

---

**Q:** What is the difference between `__getitem__` and `__getattr__`? When are they called?

---

**Q:** Explain the following concepts as related to testing: fixture, mock, patch.

---

**Q:** Python is written in what language? Name other implementations.

---

**Q:** What underlying data structure is found at the base of (almost) all Python objects? How can you access it? Can you name one type of class that uses a different base structure?

---

**Q:** What is a closure? Where is it commonly used?

---

**Q:** Explain the usage of the `else` clause in `try` and `for` blocks.

---

**Q:** What is the Garbage collector in Python? How does it work? How can you reference an object without affecting its garbage collection?

---

**Q:** Exaplain the difference between methods (or any other object) that have: a single-leading underscore (`_func`), double-leading underscores (`__func`), a double-leading-and-trailing underscores (`__func__`).

---

**Q:** Exaplain the difference between the expressions `x == True` and `x is True`? Why is the `is` operator must commonly used with booleans and None?

---

**Q:** What (usually) unexpected behaviour will arise from the following statement `matrix = [[0] * n_columns] * n_rows` ?

---

**Q:** What is the difference between an iterable and an iterator? What function(s) can be called in them to turn them into the other?


## Gotchas


**Q:** This functions tries to build an infinite generator. What will happen?

```python
def func(n):
    yield n
    yield from func(n+1)
```

---

**Q:** What will happen when trying to use the following OOP system *at scale*.

```python
from typing import List

class Developer:
    def __init__(self, applications: "List[Application]"):
        self.applications = applications

class Application:
    def __init__(self, developer: "Developer"):
        self.developer = developer
```
