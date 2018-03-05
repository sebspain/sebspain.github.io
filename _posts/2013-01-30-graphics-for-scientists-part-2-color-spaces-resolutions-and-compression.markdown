---
author: sspain
comments: true
date: 2013-01-30 21:51:06+00:00
layout: post
slug: graphics-for-scientists-part-2-color-spaces-resolutions-and-compression
title: Graphics for Scientists - Part 2 - Color Spaces, Resolutions and Compression
wordpress_id: 238
categories:
- Graphics
- Graphics for Scientists
- Science
tags:
- science
- graphics
---

_This is part of a series of posts about producing publication quality graphics. [See here for the introduction and links to other parts](/2013/01/29/graphics-for-scientists-intro.html)._


## Colour Spaces/Models

<img class="inline-left" width="200" height="200" src="http://upload.wikimedia.org/wikipedia/commons/c/c2/AdditiveColor.svg">
<img class="inline-left" width="200" height="200" src="http://upload.wikimedia.org/wikipedia/commons/1/19/SubtractiveColor.svg">


There are two main colour models for images: RGB (red, green and blue) and CMYK (cyan, magenta, yellow and key/black). RGB is the model used by computer screens etc to produce different colours as your eyes respond by adding them together to produce other colours. Consequently it is generally used to create images that will be viewed on screen.

However, as your childhood art lessons will have taught you mixing red and green paint does not produce yellow and so for printed media a different model is used, CMYK. By varying the amount of each printed you get different colours.

So which should you use? Whichever the journal requests. In most graphics software it is a simple button click to change. You'll probably find that the colours will change slightly as the two models do not map onto one another perfectly but if you happy with red being red rather than red being a very, very precise shade of red it makes very little difference. The colour will vary with the printer anyway, which is why proper graphic designers use [Pantone](http://en.wikipedia.org/wiki/Pantone#Pantone_Color_Matching_System).





## Resolution


To prevent [raster images](http://sebspain.co.uk/graphics/graphics-for-scientists-part-1-raster-vs-vector-graphics/) from pixelating like the example I used in my previous post you need to use a high enough resolution. It is also important when creating vector images as some effects used (e.g. blurring) use rasterisation to produce them. Image resolution is the number of pixels the image is made up of and how those pixels are spaced. The key figure that is usually given in journal information sections is the required _dots per inch_ (DPI). As the name suggests this is the number of pixels or printed dots per inch of media. Where possible you want to be using the highest resolution images you can while making your graphics and then reduce resolution to the required size when you make the final image. I'll cover this in more detail in a later post.


## Compression


Image files can be very large. For a typical single column figure (7 cm wide, 5 cm high) at a commonly requested resolution (300 DPI) a file is about 2 MB in size for a TIF. Considering most articles will contain multiple small images like this or a couple of large ones the resulting document can end up very large. Consequently images are usually compressed to reduce their size. Again, there are two main types of compression: lossless and lossy.


### Lossless compression


Unsurprisingly, lossless compression decreases file sizes without removing (losing) data. There are various algorithms that do this and different file formats use different ones but they all do the same basic job. It's the mechanism that is used as when you create a zip archive/file, when you open up a zip file do you find that parts of the contained files have gone? No. Lossless compression is what you should always be aiming to use.

Common types: LZW, deflate (as used by zip), packbits


### Lossy compression


Lossy compression reduces files size by throwing away bits of data that the algorithm thinks aren't needed. This is how many audio/video compression methods work and the terrible results of misuse can be witnessed on youtube. In general avoid them at all costs as once the data is gone it can't be recovered unless you still have an uncompressed version. Avoiding lossy compression isn't just a case of using certain file types. Most graphics software will give you an option of what compression to use for a TIF file, at all costs avoid JPEG (It probably deserves a post of its own at some point).

Common types: JPEG
