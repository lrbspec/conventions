## conventions for describing bitflags in mod specs
- write a character for each bit of the data
- contiguous identical characters are assumed to be multiple bits of the same piece of data
- `0` is assumed to be written as a zero and ignored when reading
- round the size of the flags data up to the nearest byte and pad the extra space with `0`

### example
`0000CBAA`
- A is a two bit value
- B and C are 1 bit values
- the 4 most-significant bits are `0`
