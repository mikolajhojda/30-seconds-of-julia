---
title: camelize
tags: string,regexp,advanced
---

Converts a string into camelcase. 

Use `replace()` with a regular expression to remove the `'` and `` ` `` characters from the string.
Use `split()` with a regular expression to convert the given string to an array of words.
Use `map()` and `uppercasefirst()` to capitalize the first letter of each word.
Finally, use `join()` to combine the words and `lowercasefirst()` to convert the first letter of the string to lowercase.

```jl
function camelize(str)
  return lowercasefirst(join(map(uppercasefirst,split(replace(str,r"['`]" => ""),r"[a-z]\K(?=[A-Z][a-z])|\W|_"))))
end
```

```jl
camelize("Coding_is_awesome") # codingIsAwesome
camelize("some-mixed_string with spaces_underscores-and-hyphens") # someMixedStringWithSpacesUnderscoresAndHyphens
```
