---
title: "CS61A: Structure and Interpretation of Computer Programs"
---

## 函数柯里化

函数的柯里化（Currying）是指将一个接受多个参数的函数转换成一系列只接受一个参数的函数的过程。换句话说，柯里化后的函数每次只接受一个参数，并返回一个新的函数，该函数继续接受剩余的参数，直到所有参数都被接受完毕，最终返回结果。

```python
def make_adder(n):
    return lambda k: n + k

>>> make_adder(2)(3)
5
>>> add(2, 3)
5
```