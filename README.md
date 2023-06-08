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

**Q:** What is the difference between `__getatrribute__` and `__getattr__`? When are they called?

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

---

**Q:** What is the `__mro__`? How does it relate to `__dict__` and `__getattr__`?

---

**Q:** What is the Descriptor protocol? How does it relate to the previous question?

## Gotchas


**Q:** What will happen when running the following code?

```python
def func(n):
    yield n
    yield from func(n+1)
    
for i in func(n):
    print(i)
```

---

**Q:** What will be the output of the following code?

```python
class Node:
    def __init__(self, name: str) -> None:
        self._name = name

    def next(self, value: "Node") -> None:
        self._next = value

    def __del__(self) -> None:
        print("Inside __del__", self._name)

    def __delete__(self, instance) -> None:
        print("Inside __delete__", self._name)


a = Node("a")
b = Node("b")
c = Node("c")

# create a graph that looks like this
# a -> b <-> c
a.next(b)
b.next(c)
c.next(b)


del a
del b
del c

print("finished script")
```

How would it change if we call `gc.collect()` att any point? 

**Q:** What will happen when running the following code?

```python
class A:
    def __str__(self):
        print("Calling A")
        return "foo"

class B(A):
    def __str__(self):
        print("Calling B")
        return super().__str__()

class C(A):
    def __str__(self):
        print("Calling C")

class D(B, C):
    def __str__(self):
        print("Calling D")
        return super().__str__()

print(D())
```
