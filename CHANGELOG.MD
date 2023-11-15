###### v0.2.1 2023-11-09

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
