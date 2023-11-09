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
