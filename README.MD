## BIN Converter for Emperor of the Fading Suns

This Windows tool for modders of Emperor of the Fading Suns allows easy conversion to and from the ```.bin``` file format used by the game for storing graphical elements.


---
#### How to:

The program is split into two main functionalities:
* conversion from ```.bin``` into ```.bmp``` in the [Export image](#exporting-to-a-bmp) tab;
* conversion back from ```.bmp``` into ```.bin``` in the [Import image](#converting-back-to-a-bin) tab.

---	
###### Exporting to a BMP

 The **Export Image** tab allows you to extract graphical elements (*items*) from a ```.bin``` file and save them as ```.bmp``` files[^1]; 

1.  Load one of the game's ```.bin``` files using the **Select file** button.
2.  Select a destination file with the **Export to BMP** button.

Optionally, the **Items to extract** area lists all elements known to be contained in the loaded ```.bin``` file. Some files contain dozens of items and would be unwieldy to work with if converted into one big file: you may instead flag individual items for conversion[^2], which will save each into its own file. With no item selected, the program extracts all.

The *preset* in **Preset Format** will be automatically chosen based on the ```.bin``` file's name. Presets define the expected dimensions, shape and number of items for each ```.bin``` file. 

---
###### Converting back to a BIN

 The **Import Image** tab allows you to convert one or more ```.bmp``` files back into a ```.bin``` file for the game to use; 

1. Select the preset matching the ```.bin``` file you are targetting in the **Format Preset**. 
2. Load one or more[^3] ```.bmp``` files[^1] **belonging in the same** ```.bin``` using the **Select BMP File(s)** button
3. Adjust individual offsets if the program failed to recognize any item[^4].
4. (Optionally) Load the contents of your target ```.bin``` file into the output buffer using the **Select BIN** button. All ```.bmp``` items will be layered on top in the order they were entered.
5. Press **Commit** and select a file to save to.

The **Format Preset** control will define the length of the ```.bin``` file created by the program when saving; any overflowing item will be truncated. If a Preset is not defined, the output file will be as long as it needs to be to fit all the images in the table. 
The selected preset also controls recognition of subsequent entries into the Items table (for automatically populating offsets).

It should be noted that entries in the output buffer are drawn in the order in which they were entered in the table: if any overlap exists, newer entries will display on top of older. There is no support for transparency.

---

[^1]: The only supported format is 256 color BMP, indexed against the game's color palette.
[^2]: The UI is ~~crap~~ slow and will be unresponsive for a couple seconds if operating on large arrays of items.
[^3]: These should be either individual elements or the whole file in ```.bmp``` format.
[^4]: The program will recognize ```* <PRESET NAME>.BMP``` and ```* <PRESET NAME>+<ITEM NAME>.BMP``` (case insensitive) and populate Preset, Offset and Item Name according to the matching Preset.
