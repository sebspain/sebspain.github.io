---
author: sspain
comments: true
date: 2013-01-29 22:01:30+00:00
layout: post
slug: graphics-for-scientists-part-1-raster-vs-vector-graphics
title: Graphics for Scientists - Part 1 - Raster vs. Vector Graphics
wordpress_id: 197
categories:
- Graphics
- Graphics for Scientists
- Science
---

_This is part of a series of posts about producing publication quality graphics. [See here for the introduction and links to other parts](http://sebspain.co.uk/graphics/graphics-for-scientists-intro/)._

So the _Journal of Pretty Pictures over Content _requires that you submit all vector graphics as EPS files in the CMYK colo(u)r space with defined bounding boxes and raster graphics must be TIF/LZW format. Hopefully I will explain the basics of what this means over the next few posts. It probably won't be strictly correct as I'm not an expert in file formats for graphics but as some of the advanced features of these files are only relevant and accessible to experts hopefully it will be illuminating enough.


### Raster vs. Vector Graphics


There are two major categories of image files: raster (aka bitmap) and vector.


#### Raster graphics


Even if you don't know it you are probably familiar with raster graphics as this is the type of file produced by digital cameras. In its simplest form a raster image is a grid of squares (pixels) of different colours, consequently they can not be made larger without a loss in quality (pixelation) as the only way to increase size is to make the pixels larger. The result of this can be seen in the two images of benzene below.

[![benzene](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene1.png)](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene1.png)


[![benzene](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene1.png)](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene1.png)


Both are produced from the same image file (benzene.png, click the images if you want to check) but in the second picture I've made it show it at 4 times the size. As your computer can't magically make more information appear all it can do is increase the pixel size and the result is a blocky, _pixelated_, image (see the [Wikipedia page](http://en.wikipedia.org/wiki/Raster_graphics) for a colour example).

Example formats: JPEG, PNG, GIF, TIF(F), BMP


#### Vector graphics


Like raster graphics, you are probably familiar with vector graphics without even realising it. Go to your preferred journal now and open a PDF version of a current article ([alternatively download this PDF](http://sebspain.co.uk/wp-content/uploads/2013/01/vector_pdf_example.pdf)) then zoom in. Does the text pixelate like the example above? Assuming you've chosen an article from the last 10 years I'd guess not. Why? Because text/fonts are generally vector graphics. Unlike raster graphics vector graphics aren't defined by a grid of pixels, instead they are defined mathematically. So for the picture of benzene above, instead of saying "we have a grid of x by y squares and this square is black, this square is white, this square is a bit grey..." it says "we have a grid of x by y squares and there is a line that goes from x,y = n,m to x,y = n-2, m-3 and it is x/p thick". This may seem more complicated (it is computationally see below) but the end result is that what the image should look like can be calculated by the computer it is shown upon. Consequently the end result (what you see on screen or what is printed) doesn't pixelate (see below).

[![benzene](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene.svg)](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene.svg)


[![benzene](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene.svg)](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene.svg)




As with the raster example both of the images above are of the same file (benzene.svg) and I've increased the size by the same amount (400%) but here there is no pixelation as your computer takes the maths from the files and multiplies by 4 (if you have problems with the images above (i) update your browser (ii) open the [PDF version here](http://sebspain.co.uk/wp-content/uploads/2013/01/benzene.pdf) and zoom, the effect is the same).




Example formats: SVG, EPS, PDF





### Which should I use, vector or raster?


This is a difficult question to answer as it depends on the image you want to display and, to complicate matters, vector formats can usually contain raster elements albeit with quality loss on scaling. As such I'll cover this in more detail as I add more sections to this guide. In general for anything that is like a photograph (e.g. microscopy images, scans of things) you should use a raster image. For simple images based around geometric shapes (lines etc) and text (e.g. graphs) vector graphics will produce smaller file sizes without loss of resolution.
