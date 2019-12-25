---
title: pretty_bytes
tags: utility,string,math,advanced
---

Converts a number in bytes to a human-readable string.

Use an array of units to be accessed based on the exponent. 
Use `round()` to truncate the number to a certain number of digits. 
Return the prettified string by building it up, taking into account the supplied options and whether it is negative or not. 
Omit the second keyword argument, `precision`, to use a default precision of `3` digits. 
Omit the third keyword argument, `add_space`, to add space between the number and unit by default.

```jl
function pretty_bytes(bytes; precision = 3, add_space = true)
  units = ['B', "KB", "MB", "GB", "TB", "PB", "EB", "ZB", "YB"]
  if abs(bytes) < 1
    return string(bytes) * (add_space ? ' ' : "") * units[1]
  end
  expo = Int64(min(floor(log10(bytes < 0 ? -bytes : bytes) / 3) + 1, length(units)))
  n = round((bytes < 0 ? -bytes : bytes) / (1000 ^ (expo - 1)), sigdigits = precision)
  return (bytes < 0 ? '-' : "") * string(n) * (add_space ? ' ' : "") * units[expo]
end
```

```jl
pretty_bytes(1000) # 1.0 KB
pretty_bytes(-27145424323.5821, precision = 5) # -27.145 GB
pretty_bytes(123456789, precision = 3, add_space = false) # 123.0MB
```
