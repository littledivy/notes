---
attachments: [Clipboard_2020-12-23-17-31-05.png, Clipboard_2020-12-23-18-26-41.png, Clipboard_2020-12-23-18-29-53.png, Clipboard_2020-12-29-11-51-11.png, Clipboard_2020-12-29-11-53-50.png]
title: Binomial theorem
created: '2020-12-21T11:37:20.407Z'
modified: '2020-12-29T06:39:51.277Z'
---

# Binomial theorem

The formula by which any positive integral power of a  binomial expression can be expanded in the form of aseries is known as BINOMIAL THEOREM.

The general term for ![](https://latex.codecogs.com/svg.latex?r%20&plus;%201) is ![](https://latex.codecogs.com/svg.latex?%5EnC_r%20a%5E%7Bn-r%7Db%5Er)

```python
# Expansion
from math import comb

# (x + y)^n
sum = 0
for r in range(0, n):
  sum += comb(n, r) * x^(n - r) * y^r
```

```python
# General term
from math import comb

# (r + 1)th term in expansion of (x + y)^n
T = comb(n, r) * x^(n - r) * y^r
```

### Binomial coefficient

The `C(n, r)` part of a term is its binomial coefficient.

> `C(n, r)` is equal to `C(n, n - r)`

## Middle term

```python
# XXX: not yet tested
# (x + y)^n
from math import comb

is_even = n % 2 == 0
T = 0

if is_even:
  # n is even, only one middle term exists.
  T = comb(n, n / 2) * x^(n / 2) * y^(n / 2)
else:
  # n is odd, there are 2 middle terms
  # at n & n + 1
  T = comb(n, n / 2) * x^(n / 2) * y^(n / 2)
  n += 1
  T += comb(n, n / 2) * x^(n / 2) * y^(n / 2)

```

Middle term contains highest binomial coefficient.

## Numerically greatest term
![](@attachment/Clipboard_2020-12-29-11-53-50.png)
![](@attachment/Clipboard_2020-12-29-11-51-11.png)

```python
# (a + b)^n
from math import comb

# For term, T_(r+1)
m = n + 1 / (1 + abs(a / b))

# calculates the term
def T(r):
  return comb(n, r) * a^(n - r) * b^r

# if m is an integer, we have two greatest terms m & m + 1
if isinstance(m, int):
   T(m)
   T(m + 1)
# otherwise, the it is the (integral + 1)th term 
else:
   # get integral & decimal value of a float m
   integral, decimal = (lambda x, y: (int(x), int(x*y) % y/y))(m, 1e0)
   T(integral + 1)
```

===

Q) Prove that integral part of (3 + root(7))<sup>n</sup> is an odd number & Prove that (I + f)(1 - f) = 2<sup>n</sup>, where I and f are integral & fractional parts.

I + f = <sup>n</sup>C<sub>0</sub> 3<sup>n</sup> + <sup>n</sup>C<sub>2</sub> 3<sup>n-2</sup>root(7) + ... 

f` = <sup>n</sup>C<sub>0</sub> 3<sup>n</sup> + <sup>n</sup>C<sub>2</sub> 3<sup>n-2</sup>root(7) + ... 

Therefore, I + f + f` = 2(Integer)

f + f` = Integer

I + 1 = 2(Integer) 

**(I + f)f` = 2<sup>n</sup>**



