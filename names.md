## conventions for choosing mod names
mod names are specified to be an arbitrary utf-8 string of up to 256 bytes by [the lrb spec](https://github.com/lrbspec/lrb/tree/main).

mod names can be "namespaced" to group them. the namespace is a section of the mod name before a "."

namespaces might describe any of the following (non-exhaustive list):
- a logical grouping of mods for certain types of features (like "[base](https://github.com/lrbspec/base)" or "[common](https://github.com/lrbspec/common)")
- a grouping of mods that originated from a certain implementation (like "lro" or ".com")
- a grouping of mods that were made by a certain developer (like "moss7")

there are no technical rules on how namespaces need to be written. 
they may even contain the namespace separator (".") like ".com", because they aren't intended to be parsed.


mod names should be kept short but not to an extent that it makes it hard to tell mods apart. for example `base.simline` describes simulation lines. it could be `bsl` but that would be miserably unreadable to anyone who isn't already familiar with the spec.
