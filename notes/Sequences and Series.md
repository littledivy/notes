---
attachments: [Clipboard_2020-12-30-11-14-17.png]
title: Sequences and Series
created: '2020-12-30T04:51:47.821Z'
modified: '2020-12-30T06:00:29.884Z'
---

# Sequences and Series

Sequence is a succession of terms a<sub>1</sub>, a<sub>2</sub>, a<sub>3</sub>, a<sub>4</sub> ...... 

Series is the sum of terms of the sequence. 

```python
# Series of n terms a1, a2, a3 ... an
def A(k):
  # logic for progression goes here.
  return

sum = 0
for k in range(1, n):
  sum += A(k)
```

## Arithmetic progression

A.P. is a sequence whose terms differ by a fixed number (common difference 'd').

a, a + d, a + 2d, a + 3d ... a + (n - 1)d

```python
# nth terms of an AP
# a is first term and common difference is d
def T(n):
  return a + ((n - 1) * d)
```

```python
# sum of n terms of an AP
# a is first term and common difference is d
def Sum(n, l = False):
  if l:
    return (n / 2) * (a + l)
  else:
    return (n / 2) * (2 * a + (n - 1) * d)
```

## Geometric progression

A sequence of _non-zero_ numbers where each term is its previous terms multiplied by constant (r).

a, ar, ar<sup>2</sup>, ar<sup>3</sup>, ar<sup>4</sup> .....
```python
# nth term of a GP
# a is the first terms and r is the common ratio
def T(n):
  return a * (r ^ (n - 1))
```

```python
# sum of n terms of a GP
# a is the first terms and r is the common ratio
def Sum(n):
  if r == 1:
    raise Exception("Not a GP")
  return (a * (r^n - 1)) / (r - 1)
```

```python
# sum of infinite terms of a GP
# a is the first terms and r is the common ratio
def Sum():
  if abs(r) < 1 or abs(r) > 0:
    return a / (1 - r)
  raise Exception("0 < |r| < 1 is false")
```

## Harmonic progression

Reciprocal of its terms are in A.P.

a<sub>1</sub>, a<sub>2</sub>, a<sub>3</sub> are in HP if 1 / a<sub>1</sub>, 1 / a<sub>2</sub>, 1 / a<sub>3</sub> are in A.P.

## Means

### Arithmetic mean

Middle term between n number of terms in a **AP** is called the A.M. of the other terms.

So a, b, c -> b is the A.M. of a & c.

```python
# sum of n AM's inserted between a & b 
# where A is the single AM between A and B
sum = 0
for r in range(1, n):
  sum += n * A
```

### Geometric mean
Middle term between n number of terms in a **GP** is called the G.M. of the other terms.

So a, b, c -> b is the G.M. of a & c.

```python
# the product of n GMs between a & b
def G(n):
  return a * ((b / a) ^ (n / n + 1))

for r in range(1, n):
  G(r)
```

## Arithmetico - Geometric series

Formed when corresponding terms of an Ap and GP are multiplied. eg 1 + 3x + 5x<sup>2</sup> + .....

```python
# sum of n terms of an AGP
# a is the first term, d is the common difference of the AP, r is the common ratio of the GP.
def Sum(n):
  if r == 1:
    raise Exception("r should not be 1")
  return (a / 1 - r) + (d * r * (1 - r^(n - 1)) / (1 - r)^2) + (((a - ((n - 1) * d)) * r^n) / 1 - r)
```

![](@attachment/Clipboard_2020-12-30-11-14-17.png)

