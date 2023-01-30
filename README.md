# KuroTools
Tools for working with Kuro no Kiseki .dat and .tbl files.

# Compatability
KuroTools is currently compatible with CLE's Steam release of Kuro no Kiseki and mostly works with CLE's Steam release of Kuro no Kiseki 2 -CRIMSON SiN-.

# Requirements
- Python 3.10 and +

If the file is encrypted (CLE encryption):
- zstandard package is required

# Rundown of Main files
- dat2py.py: Extracts scena files (.dat) intto .py for editing and can be used to recompile back into .dat post editing.
- tbl2json.py: Extracts table files (.tbl) into .json for editing.
- json2tbl.py: Compiles .json files into .tbl which can be loaded by Kuro no Kiseki.
- kuro2compresses.py: Compresses files to be loaded into Kuro no Kiseki 2 -CRIMSON SiN-
- kuro2encrypter.py: Encrypts files to be loaded into Kuro no Kiseki 2 -CRIMSON SiN-

# Guide
Please see the following document, which contains a tutorial to make a simple mod using TBL and scripts editing.\
You will also find instructions on how to use the tool.

[Guide for TBL & Scena editing](https://docs.google.com/document/d/19ajbTZzda54i5xZWDLXOq0oOVQrhJYXU9rmgz3Ya3Bc/edit?usp=sharing)

It's advised you use the disassemble mode for scena editing, as it will round trip perfectly (Decompilation might not round trip perfectly for some files, resulting in unreachable code. If that happens it may or may not cause issue after recompilation). To use the diassembler, just add --decompile False to the command.

Also see [this](https://docs.google.com/document/d/1n_nECCpRQJacN2i3g4gAVZtsiHF1Bg2XzVwrp7oOGl8/edit?usp=sharing) to learn how to add your own schemas to the tool.
 
For Kuro 2, The textures and Models will require compression, and the dat and tbl files will require compression+encryption (Remember: Its always compression first, encryption second) 

# MDL extraction
![shizuna_run](https://user-images.githubusercontent.com/69110695/185493665-86b7cf3f-23a2-40e7-84d2-cb868ba66348.gif)

From version 1.2.0, we introduce a new tool for asset extraction. Very experimental, mainly made to reinsert stuff in english CS4. If a mdl doesn't work on your end please open an issue on github and we might investigate.

To use the tool, either drag and drop a mdl on ED9AssetExporter.exe, or put the base mdl (ex: chr0000.mdl) together with their animations (ex : chr0000_mot_ev_ride_bike_wait.mdl) in the same folder, then drop that folder on ED9AssetExporter.exe (it will hopefully add the animations to the base model).

The tool outputs a single fbx file.
textures are not included in the mdl so you have to retrieve them from the game files and put them in the same folder than the output fbx before opening it in blender or whichever 3D tool you are using.
# Alternative tools

The script disassembler is very rough and not very userfriendly, more like a prototype type of thing made from the study of PS4 eboot. If you find it too difficult, please have a look at other alternatives to decompile the script files:
- [Xxmyl Kuro Modify Tool](https://github.com/Xxmyl/KuroModifyTool/tree/v0.5-beta/KuroModifyTool)
- [Ouroboros' ED9Decompiler](https://github.com/Ouroboros/Falcom/tree/master/Decompiler2/Falcom/ED9) <= This one is likely to be the best tool given a few weeks/months

As for MDL extraction, if you encounter problems when using our tool (for example, running on Linux, which was not tested, please have a look at this tool:
[uyjulian's mdl parser py file](https://gist.github.com/uyjulian/9a9d6395682dac55d113b503b1172009)
