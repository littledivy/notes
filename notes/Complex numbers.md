---
title: Complex numbers
created: '2021-01-01T04:40:00.374Z'
modified: '2021-01-01T09:03:04.312Z'
---

# Complex numbers

Complex numbers are defined as expressions of the form a + ib where a & b are rational numbers and i = sqrt(-1)

z = a + ib
Re(z) = a
Im(z) = b

> Zero is both purely real as well as purely imaginary but not imaginary.

## Argand diagram

Horizontal axis is real & Vertical axis is imaginary.

## Algebraic ops

The algebraic operations on complex numbers are similar to those on real numbers treating it as a polynomial.

### Addition

```python
import cmath

i = 1j # python's representation of complex unit i
z = a + ib
z2 = c + id

# (a + bi) + (c + di) = (a + c) + (b + d)i
def add(x, y):
  return x.real + y.real + ((x.imag + y.imag) * i)
```

### Subtraction

```python
# (a + bi) - (c + di) = (a - c) + (b - d)i
def subtract(x, y):
  return x.real - y.real + ((x.imag - y.imag) * i)
```

### Multiplication

```python
# (a + bi) (c + di) = (ac – bd) + (ad + bc)i
def mul(x, y):
  return (x.real * y.real - x.imag * y.imag) + ((x.real * y.imag + x.imag * y.real) * i)
```

### Division

```python
def div(x, y):
  return ((x.real * y.real + x.imag * y.imag) + ((x.imag * y.real - x.real * y.imag) * i)) / (y.real)^2 + (y.imag)^2
```

### Equality

Two complex numbers z<sub>1</sub> and z<sub>2</sub> are equal if and only if their real and imaginar y par ts arerespectively equal

```python
def is_equal(x, y):
  return x.real == y.real && x.imag == y.imag
```

## Operations

### Conjugate

For z = a + ib, conjugate(z) = a - ib

```python
def conjugate(x):
  return x.real - x.imag * i
```

### Modulus

```python
def mod(z):
  return sqrt(z.real^2 + z.imag^2)
```

### Argument or Amplitude

Amplitude is the prinicipal value of the argument.

```python
import math

def amp(z):
  theta = math.degrees(math.atan(z.imag / z.real))
  if theta >= 0 && theta <= (pi / 2):
    return theta
```

## Polar representation

### Eular's formula

e<sup>ix</sup> = cosx + isinx

```python
import math

def euler(x):
  return complex(math.cos(x), math.sin(x))
```

## Exponential representation

Let z be a complex number such that |z| = r and arg z = q , then z = r * e<sup>iq</sup>

```python
theta = amp(z)
r = mod(z)

z = r * euler(theta)
```

## De'moivre’s theorem

If n is any integer:

* (cosQ + isinQ)<sup>n</sup> = cos(nQ) + isin(nQ)
```python
import math

def euler_n(n, theta):
  return complex(math.cos(n * theta) + math.sin(n * theta))
```

* (cos q<sub>n</sub> + i sin q<sub>1</sub>) (cos q<sub>2</sub> + i sin q<sub>2</sub>) (cosq<sub>3</sub> + i sin q<sub>3</sub>) .....(cos q<sub>n</sub> + i sin q<sub>n</sub>) = cos (q<sub>1</sub> + q<sub>2</sub> + q<sub>3</sub> + ......... q<sub>n</sub>) + i sin (q<sub>1</sub> + q<sub>2</sub> + q<sub>3</sub> + ....... + q<sub>n</sub>)

```python
import math

# sigma_euler(
#   30 + 30j, 
#   30 + 30j,
# )

def sigma_euler(*terms):
  sum_theta = 0
  for k in terms:
    sum_theta += k.real
  sum_theta = math.radians(sum_theta)
  return complex(math.cos(sum_theta), math.sin(sum_theta))
```

```python
import math

# euler_pow_rational(
#   30 + 30j, 
#   1,
#   1,
# )

def euler_pow_rational(eu, p, q):
  _sum = 0
  # k = 0, 1, 2, 3 ... q - 1
  # note: range(...) fn is exclusive
  for k in range(0, q):
    r = math.radians((2*k*math.pi + p*eu.real) / q)
    _sum += complex(math.cos(r), math.sin(r))
  return _sum
```

## Cube roots of unity

```python
import cmath 
  
def cuberoot_n(n): 
  if n <= 0: 
    return None
  _roots = []
  for k in range(n):
    _roots.append(cmath.exp((2 * cmath.pi * 1j * k) / n))
  return _roots
```
