---
title: fibonacci
tags: math,beginner
---

Generates an array, containing the Fibonacci sequence, up until the nth term.

Create an empty array, initializing the first two values (`0` and `1`).
Loop until the `length()` of the sequence is equal to `n`, using `append!` to add the sum of the last two values to the sequence.

```jl
function fibonacci(n)
  seq = [0, 1]
  while length(seq) < n
    next = seq[length(seq)] + seq[(length(seq)) - 1]
    append!(seq, next)
  end
  return seq
end 
```

```jl
fibonacci(6) # [0, 1, 1, 2, 3, 5]
```
