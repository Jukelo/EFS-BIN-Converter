---
###### v0.1.1 2023-11-05

* Renamed some items in Presets.xml for better clarity.
* Fixed wrong height for EFSBUT5 and EFSBUT16 presets.
* Fixed wrong file name for FLET100 presets (was FLEET100.BIN, should be FLET100.BIN).
* Fixed import output buffer not reverting to previous state when trying to open empty ```.BIN``` file. #4
* Fixed export preview failing to update when loading different files with same name. #5
* Fixed crash when exporting unrecognized file. #6
* Fixed manual preset change in import tab removing a loaded ```.BIN``` file's contents from the buffer. The contents are now kept and resized according to the selected preset.  #8
---
###### v0.1.0-beta 2023-10-12

First public release, barely tested, things might break.

This is the start of great things! 