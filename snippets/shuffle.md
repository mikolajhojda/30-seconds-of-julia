---
title: shuffle
tags: array, random, beginner
---
Randomizes the order of values of an integer array, returning a new shuffled array.

```jl
function shuffle(arr)
    a = copy(arr)
    x = length(a)
    while (x != 0)
        i = rand(1:x)
        a[x], a[i] = a[i], a[x]
        x-=1
    end
    return a
end
        
```

```jl
shuffle([1,2,3, 4]) # e.g [3, 1, 2, 4]
```
