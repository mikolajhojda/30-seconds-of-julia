---
title: luhn
tags: math,utility,advanced
---

Implementation of the [Luhn Algorithm](https://en.wikipedia.org/wiki/Luhn_algorithm) used to validate a variety of identification numbers, such as credit card numbers, IMEI numbers, National Provider Identifier numbers, etc.

Define a `digit_sum()` method to get the sum of the digits of a number. Then, first format the number to be luhn-checked as a String, and save the last digit using `string(num[end])` as the check digit.
Then, get the sum of the alternate digits of the reversed number as `parta` using slicing, and `parse` on each digit as to get an `Int` from a `String`, and using `digit_sum()` to get the sum of the digits.
Then, get the digits of the reversed number alternately (this time the other numbers, not the ones we just summed up) using `reverse()`, `parse()`, `digits()`, and slicing, multiply them by two, get each of their sums of digits using `digit_sum.()`, and save the sum of the sums of digits as `partb` using `sum()`.
Finally, add up `parta` and `partb`, and the check digit `chk`, and check if the sum obtained is a multiple of ten. If it is, the number is luhn-checked. Else, it is not.

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
