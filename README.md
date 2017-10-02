# Photoshop-to-iOS-Asset-Exporter
Export layers in Photoshop to Xcode Asset Catalogue ready images

How To Use
=========

*Asset Exporter* allows you to export layers ina PSD file to either JPEG or PNG format images.  The images are generated for @1x, @2x and @3x resolutions.  The are saved to an .xcassests folder which includes a Contents.json file.  This way the xcassets folder can be dragged right into your Xcode projects Asset Catalogue.  A plist file is also generated during exporting and it contains dimension and coordinate data for programmatic layouts.

Asset Export uses 7 layer naming conventions: img, btn, txtlbl, txtweb, txtbtn, bdef & ani.  Any layer or group in a PSD project starting with any of the aforementioned keywords will be use for exporting.  

**img** is standard type and is saved as either a JPEG or PNG.   To save as a JPEG file, _jpeg_ must come after the type keyword in the layer name.  

**btn & txtbtn** can export multiple images representing different button states but first make the button later a group object.  The layers within the group will be exported as button states as long as they are named either 'normal', 'highlighted', 'selected' or 'disabled'.

**txtlbl, txtbtn, txtweb layer** or groups will not export text layers as images.  Instead the text info is saved to the plist file.  Text size, font & RGB hex color are all included.

**bDef** (bounds definition) is a special layer or group that will not export any images or plist data.  It is used to set a relative postion fora layer.  This way exported coordinate data will be relative to the bdef's coordinates and not the global coordinate system.

**ani** is for groups only and will export layers within the group as animation frames.

The *Rename Layers* script allows you to easily configure existing PSD projects for exporting by selecting multiple layer / groups of the certain type and then batch renaming them to include the require keywords.  It also handles formatting layer names to ensure they will save properly as files.

Installation
========

To install the scripts into Photoshop, locate the Adobe Photoshop application directory, then go to Presets > Scripts.  Copy Asset_Exporter_Main.jsx and the include folder into the Scripts directory.  

To run the script, restart Photshop if it is currectly running.  Make sure a PSD file is already opened and saved before attampting to run the Exporter or Renamer script. Go to File > Scripts in Photoshop's menu and choose Asset_Exporter_Main to export or Asset_Exporter_Rename_Layers to rename selected layers in the current project.

Author
=====

Created and maintained by DMASCanada Inc.

License
======

This project is licensed under the MIT License - see the LICENSE.md file for details
