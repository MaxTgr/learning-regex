# Learning Regex / Cheat Sheet
Regex is case sensitive /max/ will not match "Max"
Special characters need to be "escaped" (\char) , for example to match a dot you need to use \.

- Flags
- - `/.../` -> container for a regex sequence.
- - `/.../g` -> the g flag will return a array of all the matches instead of only the first one.
- - `/.../i` -> the i flag will ignore the capitalization. for example `/word/i` will match _word_ and _Word_.

- Word Literal
```
"The baby and the babysitter" -> /baby/g = "baby", "baby"
"phone and headphones" -> /phone/g = "phone", "phone"
```

- Dot - any character but line breaks `/./`
```
"abcde" -> /./ = "a"
"abcde" -> /./g = "a", "b", "c", "d", "e"

"head" -> /head./ = ""
"headset" -> /head./ = "heads"
"headset headphone" -> /head./g = "heads", "headp"
```

- [...] - character range
```
"A C R V" -> /[ABC]/g = "A", "C"
"unity Game maker Unity" -> /[Uu]nity/g = "unity", "Unity"
"source.x source.y source.z" -> /source\.[xy]/g = "source.x", "source.y"
```
- - there are shorthands for some combinations like: [0-9] for all numbers and [a-z] for lower case letters
```
"baser laser cases eased raser" -> /[a-z]aser/g = "baser", "laser", "raser"
"Lia Mia ria Sia jane" -> /[A-Z]ia/g = "Lia", "Mia", "Sia"
"We are in 2018" -> /[0-9]/g = "2", "0", "1", "8"
```

- [^...] - deny character
```
"We are in 2018" -> /[^0-9]/g = "W", "e", " ", "a", "r", "e", " ", "i", "n", " "
"12:42" -> /[^:]/g = "1", "2", "4", "2"
```

- Shorthands
- - [0-9] = [0123456789]
- - [a-z] = [abcdefghijklmnopqrstuvwxyz]
- - [A-Z] = [ABCDEFGHIJKLMNOPQRSTUVWXYZ]
- - \d = [0-9]
- - \D = [^0-9]
- - \w = [a-zA-z0-9_]
- - \W = [^a-zA-z0-9_]
