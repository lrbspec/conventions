## conventions for writing data types mod specs
- assume all values are little endian
- write integers as `u` for unsigned and `i` for signed, followed by the number of bits, so a `u8` is one byte of unsigned data.
- write floats as `f` followed by the number of bits, so an `f64` is a double precision float and an `f32` is a single precision float (IEEE-754 binary64 and binary32 respectively).
- write bools as one byte, which is `0` if it is false, or otherwise true.
