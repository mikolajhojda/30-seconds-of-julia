---
title: pull_at_index
tags: array,advanced
---
Mutates the original array to filter out the values at the specified indexes. Returns the removed elements.

Use `filter!()` to pull out the values that are not needed. Use `push!()` to re-populate a new array with only the values pulled.

```jl
function pull_at_index(arr, pullArr)
  removed=String[]
  counter=0
  for i in pullArr
    value = arr[i-counter]
    filter!(x -> x != value, arr)
    push!(removed, value)
    counter=counter+1
  end
removed
end
```

```jl
myArray = ["a", "b", "c", "d"]
pulled = pull_at_index(myArray, [1,3]) #myArray=["b", "d"]; pulled=["a", "c"]
```
