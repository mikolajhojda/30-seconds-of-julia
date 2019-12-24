---
title: camel
tags: vector,beginner
---
Converts string into camelCase. 

Use `Vector{Char}` to convert immutable string into mutable vector.
Replace all hyphens and underscores with space.
Iterate through the `Vector`, checking if there are spaces and if so, converting the character in front of it to uppercase if not done so already.
Delete all spaces from string.
Finally, append elements in vector back to a `String`

```jl
function camel(str)
    str = Vector{Char}(str)
    replace!(str, '_' => ' ')
    replace!(str, '-' => ' ')
    for i = 1:length(str) - 2
        if (str[i] == ' ' && str[i] != length(str))
            if (Int(str[i+1]) > 90)
                str[i+1] = Char(Int(str[i+1])-32)
            end
        end
    end
    filter!(e->e!=' ', str)
    tempstr = ""
    if Int(str[1]) < 90
        str[1] = Char(Int(str[1])+32)
    end
    for i in str
        tempstr = tempstr * i
    end
    return tempstr
end
```

```jl
camel("Coding_is_awesome") # codingIsAwesome
camel("Hello world") # helloWorld
camel("Julia-Is-a-really-cool-lang") # juliaIsAReallyCoolLang
camel("some-mixed_string with spaces_underscores-and-hyphens") # someMixedStringWithSpacesUnderscoresAndHyphens
```
