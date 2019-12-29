---
title: rotate
tags: array,beginner
---

Rotates the array by the number of shifts.

```jl
function rotate(array, shift)
  return circshift(array, shift);
end
```

```jl
rotate([1, 3, 5, 2, 4], 2) #[3, 5, 2, 4, 1]
rotate([1, 3, 5, 2, 4], 3) #[5, 2, 4, 1, 3]
```
