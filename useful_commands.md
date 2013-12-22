---
layout: page
title: Useful Commands
---

This page is mainly an *aide memoire* for me but some of these may be useful for others

###Create a set of test images
This creates a set of images with the numbers 1 to 10 in the middle. Useful for creating a set of images for further scripting tests. Requires [ImageMagick](http://www.imagemagick.org/).

**Single line version**

```{sh}
for i in {1..10}; do convert -size 800x600 xc:#ffffccff -fill black -pointsize 80 -draw "text 400,300 '$i'" test-img-$i.jpg; done
```
**Script version**

```{sh}
for i in {1..10}
	do convert -size 800x600 xc:#ffffccff -fill black -pointsize 80 -draw "text 400,300 '$i'" test-img-$i.jpg
	done
```
