###### v0.4.1 2022-04-13

* Fixed crash when exporting split BIN file.

###### v0.4.0 2022-04-12

* Added search box to filter items list by names in the export tab.
* Included optional palette ```EFS-Gimp-Fix.gpl``` with distinctive and separated colours for indices 10-13 (the 'blinking' blues). This is intended for use with GIMP, which cannot distinguish between colour map indices sharing the same colour values.
	Rename it to palette.gpl (or export_palette.gpl) for the exporter to save images using this palette. 
		This palette is only intended for GIMP use with indexed colour images exported from BIN files and/or converted back to BIN.
		If you wish to create graphics imported directly into the game as BMPs and PNGs (as opposed to inserted back into a BIN file such as EFSUNITS), use the default palette instead to extract a base or template from a BIN file.
* Fixed significant lag caused by splitting files with large number of items (looking at your EFSTILE).
* Fixed 'Select folder' export dialog would not default to the last selected directoty but one level up.
* Fixed palette in image format would read pixels in the wrong order. #30

###### v0.3.2 2024-04-04

* Fixed Corrupted buffer when using the Remove all entries button after importing an image.

###### v0.3.1 2024-04-04

* Added support for exporting to indexed colors PNG. The dropdown menu allows choosing a file format for split exports. This was supposed to be part of the 0.3.0 build...
* Merged BMP and PNG into the same filter in the import image dialog (there was no reason for them to be separate).
* Fixed imported items sometimes not being cleared from the preview area when using the 'Remove all entries' button. #22
* Fixed BIN contents layer being lost after using 'Remove all entries' button and changing preset.

---
###### v0.3.0 2024-03-24

* Added support for importing .BMP and .PNG files with pixel formats other than 8-bit. Not all options have been tested, expect trouble. Compression down to 256-colors is slower and basic (simple RGB distance), so it is still recommended to stick to the game's palette and use indexed colors images.
	Note that 8-bit images do not go through any compression, and their color map is ignored entirely, only indexes are copied.
* Changed Offset field in the import table to shift items by whole item lengths rather than bytes. #20
* Added parser for custom palettes. A valid palette file in the same directory as the executable will override the tool's hardcoded one. Valid files are Gimp `.GPL` files, JASC-PAL `.PAL` files, Gimp `.TXT` exports, as well as `.BMP` and `.PNG` files. #21
	Note that this has no effect on the color palette used by the game, it is mainly aimed at better maintainability but can have niche artist workflow benefits.
* Fixed crash upon importing image with unrecognized name.

---
###### v0.2.1 2023-11-15

* Fixed changing preset would fail to re-run file recognition. Changing preset will now update imported items names and offset according to the new preset. Offsets are only adjusted if set to zero. #2
* Fixed exported images and saved ```.bin``` files are now sized according to the maximum item index defined in ```Presets.xml``` instead of the number of items. 
* Fixed crash when importing ```.bmp``` file with wrong size while a preset with hexagonal format is selected #17
* Fixed wrong item name when imported file with index matching no item for the recognized preset.
* Last used directories for the various file dialogs are now saved per dialog, somewhere in AppData probably.
* Presets drop down lists displayed in alphabetical order rather than the order in which they appear in ```Presets.xml```
* Added warning in Export tab when a mismatch occurs between the loaded file's length and the total length of all items defined in the preset.
* Added warning in Export tab when no preset was found for the loaded file.

---
###### v0.2.0 2023-11-09

* Updated the naming system for newly exported ```.bmp``` files : a 5-characters string made from the preset id and the item index identifies each image for automatic selection of preset and offset when importing images. #9
  * images were previously named after and identified by preset and item GUI names, leading to compatibility and workflow issues when changing those in ```Presets.xml```.
* Improved performance appreciably when loading large numbers of items. Things are now merely *slow*. #1
* Improved control flow when navigating with Tab key. #3
* Moved controls in Import tab for more sensible flow. #3
* Fixed save to ```.bin``` window was missing a pre-filled filename. #16
* Fixed and adjusted several item names ```Presets.xml```. #12
* Fixed duplicates in import table sometimes couldn't be removed. #11
* Fixed ```Presets.xml``` loading or validation failure would leave the program in a unusable state. The program will now properly crash instead.
* Fixed *Split* checkbox remained disabled when loading a new file or changing preset after selecting subset of items. #14

---
###### v0.1.1 2023-11-05

* Renamed some items in ```Presets.xml``` for better clarity.
* Fixed wrong height for ```EFSBUT5``` and ```EFSBUT16``` presets.
* Fixed wrong file name for ```FLET100``` presets (was ```FLEET100.BIN```, should be ```FLET100.BIN```).
* Fixed import output buffer not reverting to previous state when trying to open empty ```.bin``` file. #4
* Fixed export preview failing to update when loading different files with same name. #5
* Fixed crash when exporting unrecognized file. #6
* Fixed manual preset change in import tab removing a loaded ```.bin``` file's contents from the buffer. The contents are now kept and resized according to the selected preset.  #8

---
###### v0.1.0-beta 2023-10-12

First public release, barely tested, things might break.

This is the start of great things! 
