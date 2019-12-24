---
title: is_even
tags: math,beginner
---

Returns True if the given number is even, False otherwise.

Checks whether a number is odd or even using the modulo (%) operator. Returns True if the number is even, False if the number is odd.

```jl
function is_even(num)
  return num % 2 == 0
end
```

```jl
is_even(4) # true
is_even(5) # false
```