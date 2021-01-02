---
title: Derivative
created: '2021-01-02T06:34:32.639Z'
modified: '2021-01-02T08:21:55.282Z'
---

# Derivative

The slope of a function at any point.

```python
# Python3
from math import *
def derive(f, x):
    h = 1e-5
    return (f(x + h) - f(x - h))/(2 * h)
```

```rust
// Rust
fn derive(f: fn(f64) -> f64, x: f64) -> f64 {
  let h = 1.0 * 10_f32.powi(-5) as f64;
  (f(x + h) - f(x - h))/(2.0 * h)
}

fn main() {
  let sin = |x: f64| {
    x.sin()
  };
  println!("{}", derive(sin, 20.0));
}
```
