---
title: lcm
tags: math,array,beginner
---

Returns the least common multiple of two or more numbers.

Use `gcd()` to get the greatest common divisor and the fact that `lcm(x,y) = x * y / gcd(x,y)` to determine the least common multiple. 
Use `reduce()` to apply the `lcm_` formula to each pair of numbers and get the result.

```jl
function lcm(nums...)
  lcm_(x,y) = (x * y) / gcd(trunc(Int64, x), trunc(Int64, y))
  return trunc(Int64, reduce(lcm_, nums))
end
```

```jl
lcm(12, 7) #84
lcm(1, 3, 4, 5) #60
```
