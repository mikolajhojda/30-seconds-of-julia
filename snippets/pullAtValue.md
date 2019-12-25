---
title: pullAtValue
tags: array,advanced
---
Mutates the original array to filter out the values specified. Returns the removed elements.

Use `filter!()` to pull out the values that are not needed. Use `push!()` to re-populate a new array with only the values pulled.

```jl
function pullAtValue(arr, pullArr)
  removed=String[]
  for i in pullArr
    filter!(x -> x != i, arr)
    push!(removed, i)
  end
  removed
end
```

```jl
myArray = ["a", "b", "c", "d"]
pulled = pullAtValue(myArray, ["b", "d"])  #myArray=["a", "c"]; pulled=["b", "d"]
```
