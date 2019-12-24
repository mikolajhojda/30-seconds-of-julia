---
title: fibonacci
tags: array,beginner
---
(Non-recursive)

Generates an array, containing the Fibonacci sequence, up until the nth term.

Starting with 0 and 1, use `append!` to add the sum of the last two numbers of the array to the end of the sequence, until the length of the array reaches n. If n is less or equal to 0, return an array containing 0.

```jl
function fibonacci(x)
    if x <= 0
        return [0]
    end
    seq = [0, 1]
    while length(seq)<=x
        next = seq[length(seq)] + seq[(length(seq)) - 1]
        append!(seq, next)
    end
    return seq
end
        
```

```jl
fibonacci(4) # [0, 1, 1, 2, 3]
```
