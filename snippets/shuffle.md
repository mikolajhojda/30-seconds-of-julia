---
title: shuffle
tags: array,random,intermediate
---

Randomizes the order of the values of an array, returning a new array.

Use `copy()` to create a new array from `arr`.
Use the [Fisher-Yates algorithm](https://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle#Fisher_and_Yates'_original_method) to reorder the elements of the array.

```jl
function shuffle(arr)
  a = copy(arr)
  x = length(a)
  while (x != 0)
    i = rand(1:x)
    a[x], a[i] = a[i], a[x]
    x -= 1
  end
  return a
end    
```

```jl
shuffle([1,2,3, 4]) # [3, 1, 2, 4]
```
