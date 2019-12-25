---
title: luhn
tags: math,utility,advanced
---

Implementation of the [Luhn Algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm) used to validate a variety of identification numbers, such as credit card numbers, IMEI numbers, National Provider Identifier numbers, etc.

Define a `digit_sum()` method to get the sum of the digits of a number, using `sum()` and `digits()`.
Convert the given number to a string, store the check digit, `chk`, using `string(num[end])`.
Use slicing, `parse()` and `digit_sum()` on each digit to implement the Luhn Algorithm and produce `parta` and `partb`.
Finally, return `true` if the sum of `parta`, `partb` and `chk` is divisible by `10`, `false` otherwise. 

```jl
function digit_sum(number)
  return sum(digits(number))
end

function luhn(number)
  num = "$number"
  chk = string(num[end])
  parta = digit_sum(parse(Int, reverse(num)[3:2:end]))
  partb = sum(digit_sum.(2 * digits(parse(Int, reverse(num)[2:2:end]))))
  return((parta+partb+chk) % 10 == 0 ? true : false)
end
```

```jl
luhn(79927398713) # true
luhn(79927398714) # false
```
