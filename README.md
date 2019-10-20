# MGSV Normal Map Channels Converter

Converts RGBA channels of DDS texture files between Fox Engine style normals and regular style normals using ImageMagick.

Both files and entire directories containing texture files can be sent to the script (the script will only convert the normal maps among them). Directories are parsed non-recursively.

The script by default also handles conversion of normal map texture files that have a custom filename and lack the standard `_nrm`/`_hnm` suffix. It achieves this by performing color matching comparisons that requires a minimum threshold to pass as a normal map of either the Fox Engine or regular style. This is only performed on inputs that lack the standard suffixes and due to the added delay of the comparison the method is excluded from directories parsed to avoid unintended slowdown.

***

Example GIF of script usage, with both files and a directory as inputs:

![Example](https://user-images.githubusercontent.com/34178938/67155397-30a16300-f35a-11e9-86c1-c36634277f2e.gif)

Example GIF of suffix-less filename conversion:

![Example of suffix-less conversion](https://user-images.githubusercontent.com/34178938/67155399-3dbe5200-f35a-11e9-87bb-5dfc659922dd.gif)

*Note: in the GIFs above the uncompressed intermediate setting was disabled so the thumbnails could update to show the conversion more visually. By default an uncompressed intermediate is used to avoid compressing twice to DTX5.*

***

### Dependancies

- [ImageMagick v7+](https://imagemagick.org/script/download.php#windows) (for its `magick.exe`)

***

### Installation

1. Install ImageMagick.
2. Download and unpack the top zip from the [Releases tab](https://github.com/chocmake/MGSV-Normal-Map-Channels-Converter/releases/latest).

***

### Usage

The script can launched a couple different ways:

- Dropping DDS file(s) on its icon.
- Launching it from selected DDS file(s) via a custom Send To context menu shortcut (refer to [this guide](https://github.com/chocmake/MGSV-Custom-Texture-Path-Hex-Replacer/wiki/Using-the-script#optional-adding-a-shortcut-to-the-send-to-menu) from my other repository for a howto).

***

### Settings

The script includes a handful of default settings that can be edited by opening the script in a text editor (eg: Notepad). The settings are explained by comments.

Among the settings are:
- Suffix-less matching.
- Compression for intermediate (regular style) DDS.
- Backup the original normal map files or replace upon conversion.
- Disabling of the green channel inversion (only disable if sure your normal map editor requires it).
