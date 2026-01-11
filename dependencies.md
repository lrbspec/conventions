# Dependencies
some mods rely on data from other mods to be loaded first, and some mods rely on being processed before specific other mods (like `common.singlescn` which specifies that `base.scnline` reads and writes its scenery lines in a different structure)

this should be indicated in the mod spec, and the mod table should be ordered such that these mods appear with the "dependencies" first. this isn't technically required by the lrb spec but your track can and will fail to load properly in software that has this expectation.
