## conventions for describing strings in mod specs
there are a few different ways to write strings that work better depending on the scenario.

### text encodings
there are [a lot of ways to encode characters](https://en.wikipedia.org/wiki/Character_encoding#Common_character_encodings).

a string with a certain text encoding could be described as (utf-8 for example) `string with encoding utf-8`.

### fixed strings
sometimes strings are quite short and it doesn't really matter to have their size written, instead always reading a constant amount of characters.

a fixed string like this could be denoted as `fixedstring[n]` where `n` is the number of "code units" from the text encoding.

if a fixed string can be variable length with a null termination (only the bytes up until a 0x00 byte are relevant) then it should also be specified `with null-termination`. the string is still assumed to take up the entire fixed width even if it is null-terminated.

### length specified strings
the alternative to fixed strings is to write a number in the data and read that many codeunits. this can be assumed to be called a `string`, where the length type is specified like (using a u16 for example) `string with u16 length`.

the length is assumed to be written before the text data.

### examples
`string with u8 length and utf-8 encoding` describes a string that writes a u8 for the number of bytes followed by that many utf-8 encoded codeunits (bytes and codeunits are indentical here).

`string with u32 length and utf-16 encoding` describes a string that writes a u32 for the number of codeunits followed by that many utf-16 encoded codeunits (two bytes each).

`fixedstring[256] with ascii encoding and null-termination` describes a string that writes 256 code units of ascii (one byte each just like utf-8) and writes a null terminator at the end of the text if it is less than 256 bytes. (the entire fixedstring always takes up 256 bytes but the length of the contents written may be less than 256 with null termination)

***
### null terminated strings
these strings write no length and are read until the reader encounters a null byte (0x00). this means they are completely arbitrary length and if written wrong (accidentally or maliciously) may cause out of bounds accesses. I personally will never use these when writing specs but for the purpose of this document they may be written as the following, using ascii for example:
`null-terminated string with ascii encoding`
