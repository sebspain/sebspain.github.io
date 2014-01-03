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

###Create a set of test images
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

###List directories
This lists subdirectories of the current directory while stripping leading ./ and closing / making it useful where directory names need to be used as a variable.

```{sh}
#!/bin/bash
for dir in ./*/
	do  
		dir=${dir%*/} #strips closing /
    	echo ${dir##*/} #prints and strips leading ./
	done
```

Alternatively the leading ./ may be removed before the echo command

```{sh}
for dir in ./*/
 	do 	
 		dir=${dir%*/} #strips closing /
 		dir=${dir##*/} 	#strips leading ./
 		echo $dir #prints list
 	done
```

###Strip spaces
Replaces spaces in filenames with underscores

```{sh}
#!/bin/bash
ls | while read -r FILE
	do 	
		mv -v "$FILE" `echo $FILE | tr ' ' '_' `
	done
```

###Unzip archives to individual folders
Unzips all zip archives in the current folder creating a subfolder for each that is named after the archive (minus the zip extension)

```{sh}
for file in *.zip
	do 
		unzip $file -d ./${file/.zip/} 
	done
```

###Bulk renaming
Examples are image renaming but will work with others

Add text between filename and extension. Renames filename.png to filename-text.png

```{sh}
for file in *.png
	do 
		mv $file ${file/.png/}-text.png
	done
```

Add text before filename. Renames filename.png to text-filename.png

```{sh}
for file in *.png
	do 
		mv $file text-$file
	done
```