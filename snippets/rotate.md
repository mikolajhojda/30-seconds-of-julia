---
title: rotate
tags: array,rotate
---

Rotates the array by the number of shifts.

```jl
function rotate(array, shift = 1)
        array_copy=copy(array)
        for i=1:length(array)
            if (i+shift > length(array))
           array[i] = array_copy[mod(i+shift, length(array))]
            
        else
            array[i] = array_copy[i+shift]
            end
        end 
  return array
end
```

```jl
rotate([1, 3, 5, 2, 4]) #[3, 5, 2, 4, 1]
rotate([1, 3, 5, 2, 4], 2) #[5, 2, 4, 1, 3]
```
