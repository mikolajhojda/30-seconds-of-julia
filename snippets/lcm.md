---
title: lcm
tags: math,list,recursion,advanced
---

Returns the least common multiple of two or more numbers.

Use the greatest common divisor (GCD) formula and the fact that `lcm(x,y) = x * y / gcd(x,y)` to determine the least common multiple. The GCD formula uses recursion.

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
