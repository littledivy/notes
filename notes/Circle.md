---
title: Circle
created: '2020-12-30T06:07:11.318Z'
modified: '2020-12-30T06:35:29.773Z'
---

# Circle

A circle is the locus of a  point which moves in a plane in such a way that its distance from a fixed point (in thesame given plane) remains constant. The fixed point is called the centre of the circle and the constant distanceis called the radius of the circle.

## Standard equations

### Central form

```rust
/// XXX: Test this code
type Centre = (i32, i32);
pub struct Circle {
  centre: Centre,
}
 
impl Circle {
  pub fn new(centre: Centre) -> Self {
    Self { centre }
  }
 
  pub fn radius(&self, x: i32, y: i32) -> i32 {
      let (h, k) = self.centre;
      let r2 = (x - h).pow(2) + (y - k).pow(2);
      (r2 as f64).sqrt() as i32
  }
}
```
