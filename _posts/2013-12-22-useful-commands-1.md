---
layout: post
title: Useful Commands 1
comments: true
author: Seb Spain
published: true
categories:
- Coding
- Useful Commands
---

This page is mainly an *aide-mémoire* for me but some of these may be useful for others. Add suggestions for improvements in the comments.

These should all run on bash, additional requirements are noted.

##Create a set of test images

This creates a set of images with the numbers 1 to 10 in the middle. Useful for creating a set of images for further scripting tests. Requires [ImageMagick](http://www.imagemagick.org/).

**Single line version**

```{sh}
for i in {1..10}; do convert -size 800x600 xc:#ffffccff -fill black -pointsize 80 -draw "text 400,300 '$i'" test-img-$i.jpg; done
```
**Script version**

```{sh}
#!/bin/bash
for i in {1..10}
	do
		convert -size 800x600 xc:#ffffccff -fill black -pointsize 80 -draw "text 400,300 '$i'" test-img-$i.jpg
	done
```

##List directories
*Updated 2014-01-03 to make it compatible with spaces in directory names*

This lists subdirectories of the current directory while stripping the closing / making it useful where directory names need to be used as a variable.

```{sh}
#!/bin/bash
ls -d */ | while read line
	 do
	 	dir=${line%*/}
	 	echo $dir
	 done
```

##Strip spaces
Replaces spaces in filenames with underscores for all files (non-hidden files) in the current directory

```{sh}
#!/bin/bash
ls | while read -r FILE
	do
		mv -v "$FILE" `echo $FILE | tr ' ' '_' `
	done
```

##Unzip archives to individual subdirectoies
Unzips all zip archives in the current directory creating a subfolder for each that is named after the archive (minus the zip extension)

```{sh}
ls *.zip | while read file
	do
		unzip "$file" -d ./"${file/.zip/}"
	done
```

##Bulk renaming
Examples are image renaming but will work with others. Affects all files in the current directory.

Add text between filename and extension. Renames filename.png to filename-text.png

```{sh}
ls *.png | while read file
	do
		mv "$file" "${file/.png/}"-text.png
	done
```

Add text before filename. Renames filename.png to text-filename.png

```{sh}
ls *.png | while read file
	do
		mv "$file" text-"$file"
	done
```

*Added 2014-01-04*

##Batch conversion of SVG files
These convert all SVG files in a directory to EPS or PNG for use with $LaTeX$ etc. This method requires [Inkscape](http://www.inkscape.org).

**EPS Conversion**

```{sh}
#!/bin/bash

ls *.svg | while read file
	do
		inkscape "$file" --export-eps="${file/.svg/}.eps"
	done
```

**PNG Conversion**

This script takes an additional argument to determine the resolution (DPI) of the output files. Personally I have it saved in my PATH as svg2png and run as svg2png \<DPI\>. E.g. "svg2png 300" will export 300 DPI PNG files.

```{sh}
#!/bin/bash

ls *.svg | while read file
	do
		inkscape "$file" -d $1 -e "${file/.svg/}.png"
	done
```
