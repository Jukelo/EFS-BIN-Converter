### BIN Converter for Emperor of the Fading Suns

This tool for modders of Emperor of the Fading Suns allows easy conversion to and from the ```.bin``` file format used by the game for storing graphical elements.

This is a **.NET 4.7.2** program for **Windows**. 

###### No game files are distributed with this tool.

---

##### Get started:

* Create a ```.bmp``` image out of a ```.bin``` file in the [Export image](#exporting-to-a-bmp) tab;
* Edit the image using your preferred image editor (make sure to export to 256 colors BMP);
* Convert your ```.bmp``` image into a ```.bin``` file for use by the game in the [Import image](#converting-back-to-a-bin) tab.

---	
###### Exporting to BMP

 The **Export Image** tab allows you to extract graphical elements (*items*) contained in the game's ```.bin``` files and save them as ```.bmp``` files[^1]; 

1.  Load one of the game's ```.bin``` files using the **Select file** button. Those are located in the BIN folder of your game's install.
2.  Select a destination file for your image with the **Export to BMP** button.


The *Preset* in **Preset Format** will be automatically chosen based on the ```.bin``` file's name. A *Preset* defines the expected dimensions, shape and number of items stored in each ```.bin``` file for the program.

The *Split* check box allows you to export individual items instead.

---
###### Converting back to BIN

 The **Import Image** tab allows you to convert one or more ```.bmp```[^1] files back into a ```.bin``` file for the game to use; 

1. Load one or more ```.bmp``` files **belonging in the same** ```.bin``` using the **Import BMP item(s)** button. 
2. Pick the preset corresponding to the ```.bin``` file you want to save to if one wasn't automatically selected for you. Adjust byte offsets as needed.
3. Press **Save to BIN** and select a file to save to.[^2]

The **Format Preset** control defines the length of the ```.bin``` file created by the program when saving. It also controls how the program reads an imported file's pixel data, as images representing hexagonal items need variable-length padding to be usable in an image editor.

The **Copy BIN Content** button is a way of copying an existing ```.bin``` file's contents directly into the output buffer. All imported ```.bmp``` image will be layered on top of it. This is convenient if you only exported a select few items.

It should be noted that ```.bmp``` entries are layered on top of each other in the order in which they were entered in the table: Newer will therefore overwrite older if any overlap exists. The preview area will help in that regard.

---

##### A note on file names:

A 5-characters string is prefixed to the name of exported ```.bmp``` files in the Export tab. This string is used by the importer to identify the item represented by the ```.bmp``` file and therefore conveniently pick the right preset and offsets for each imported item.

*The rest of the file name is ignored by the importer and can be changed by the modder without consequence.*

The string is composed of two parts: the first 2 characters make up the unique identifier for the preset associated with the ```.bin``` file from which the image was exported, as defined in ```Presets.xml```. The next 3 (decimal) digits are the item's index, defining its position within the .bin file.
Exporting the ```Noble``` item (index 45) from ```EFSUNITS.BIN``` (Id 18) would therefore produce a file named ```18045_EFSUNIT_Noble.BMP``` where 18045 uniquely identifies the Noble for the importer. The importer will therefore know to load the EFSUNIT preset, and to insert the Noble at offset  46080 in the entries table (1024 \* 45).

If the importer fails to recognize a ```.bmp``` file's identifier, it will position the image's pixel data at the beginning of the pixel buffer, along with every other unrecognized file's, forcing the user to manually assign preset and offset.


[^1]: The only supported format is 256 color BMP, indexed against the game's color palette. 
[^2]: You should probably not save this directly in your game's BIN folder. Use a game mod instead.
