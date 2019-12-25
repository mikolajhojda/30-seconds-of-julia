---
title: is_odd
tags: math,beginner
---

Returns `true` if the given number is odd, `false` otherwise.

Checks whether a number is odd or even using the modulo (`%`) operator. 
Returns `true` if the number is odd, `false` if the number is even.

```jl
function is_odd(num)
  return num % 2 == 1
end
```

```jl
is_odd(4) # false
is_odd(5) # true
```
