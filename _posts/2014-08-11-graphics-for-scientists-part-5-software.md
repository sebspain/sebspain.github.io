---
author: sspain
comments: true
layout: post
slug: graphics-for-scientists-part-5-software
title: Graphics for Scientists - Part 5 - Software
categories:
- Graphics
- Graphics for Scientists
- Science
---

_This is part of a series of posts about producing publication quality graphics. [See here for the introduction and links to other parts](http://sebspain.co.uk/graphics/graphics-for-scientists-intro/)._

Now that you know about the different types of graphics files you need to know what software you can use to create them. This list doesn't aim to be exhaustive, instead covering software that I'm reasonably familiar with. If we look at the figure mock-up below we have various types of data in one figure:

A. A chemical reaction scheme

B. A graph/plot of some kind

C. A microscopy image or other "photograph"

D. A schematic

So we need to be able to produce each of these parts and then put them all together and add annotations like the labeling of the sub-figures.

![Mock-up of a compound figure](http://sebspain.co.uk/files/2014/08/11/mock_figure.png)

##Chemical Structure Drawing
###ChemDraw
The _de facto_ 2D chemical drawing package is [Chem(Bio)Draw](http://www.cambridgesoft.com/Ensemble_for_Chemistry/ChemBioDraw/Default.aspx). It has the best tools and templates, and can export to a wide range of formats including EPS, PDF and SVG, and a variety of raster formats as well.

###MarvinSketch
I also recommend [Marvin Sketch](http://www.chemaxon.com/products/marvin/marvinsketch/) which has free academic licenses available if you don't have, or can't afford, a ChemDraw license. It runs on almost anything, including Linux, can export to useful formats and has some nice features including the ability to save each structure in a scheme to individual files that can then be used later.

##Graphing Software
There are a lot of good graphing and data analysis softwares available. The golden rule in making publication quality graphs is...


###Don't use Excel

There are various reasons for this that I'll expand upon in a later post but the main problem is that Excel cannot export graphs to a good vector format and that's how graphs should be exported (again, I'll expand on this later). In fact [it can barely export graphs at all](http://www.ablebits.com/office-addins-blog/2013/08/27/save-excel-chart-as-image/).

Graphing software that will produce good quality vector graphics include:

###[Graphpad Prism](http://www.graphpad.com/scientific-software/prism/)
This would be my general recommendation for good data analysis/stats/graphing software. Runs on both Windows and Mac, user friendly with a [great online guide](http://www.graphpad.com/guides/prism/6/user-guide/) and can produce layouts of multiple graphs easily.

###[SigmaPlot](http://www.sigmaplot.co.uk/products/sigmaplot/sigmaplot-details.php)
Windows only but still very good.

###[Origin](http://www.originlab.com/index.aspx?go=PRODUCTS/Origin)
Windows only. One of the most powerful data analysis packages there is but licenses are expensive.

###[R](http://www.r-project.org/)
My personal favourite. It's free (opensource) and it runs on anything. However, it is command-line based so has a steep learning curve. The plot above is made with R.


##Raster Images/"Photographs"
Generally the only source of raster images should be photographs and micrographs. Good microscopes will produce high quality TIFF files as well as their own format (usually a container with additional information, then the TIFFs). For photographs, if possible use a camera that record either to TIFF or RAW. These days a lot of lab photos are taken on phones which inevitably save as JPEG, make sure the highest quality settings are used.

###[Adobe Photoshop](http://www.adobe.com/uk/products/photoshop.html)
Adobe Photoshop is the industry standard software for editing raster images, so much so that photoshop has been verbified and become synomynous with any form of image editing, [much to Adobe's annoyance](http://www.adobe.com/legal/permissions/trademarks.html#photoshoptrademark).
It holds this position because it is very powerful, however that comes at a high price, even with discounted Academic licensing, and is a complex piece of software.
As the only modifications you should be making to images are minor ones (e.g. cropping, resizing, minor contrast/brightness changes and, in some circumstances, false colouration) most of the power is wasted so I don't recommend it. If you do have a copy anyway then it is the best there is.

###[GIMP](http://www.gimp.org/)
GNU Image Manipulation Program (GIMP) may not have the most attractive name but is a raster editor that is more than capable of doing pretty much anything you'll need.
It is not as powerful as Photoshop, but that also makes it easier to use (in my opinion anyway) and it has the added benefits of being free (opensource) and running on all major operating systems.

###[ImageJ](http://imagej.nih.gov/ij/)
ImageJ is an image processing and analysis package provided by the NIH free of charge (public domain).
It supports plugins, many of which have been written for specific tasks (e.g. reading manufacturer specific microscopy files) and can be scripted to allow processing of large numbers of images automatically.
It is not that user friendly but there are good guides available and it is brilliant for fluorescent/confocal microscopy, or where you need to get information out of an image (e.g. [counting/sizing particles](http://fzu.cz/~dominecf/misc/imagej_particles.html)).

##Schematics
Schematics are generally drawn in a vector graphics editor. As with making graphs there is a golden rule in making publication quality graphics...

###Don't use Powerpoint

As with with Excel I'll expand upon this at a later date but the main problem, again, is the inability to export to suitable formats.

Software that is suitable for making vector graphics

###ChemDraw
It's drawing tools are that powerful but ChemDraw is perfectly good for drawing simple schematics. The biological templates available in some versions are also very useful, although I end up editing them in something more powerful.

###[Adobe Illustrator](http://www.adobe.com/uk/products/illustrator.html)
As with Photoshop, Illustrator is the industry standard for vector graphics but it also suffers form the same problems as well, very powerful = very complicated. If you have it, and understand it, then use it as it has some really useful features (Artboards are excellent).

###[Inkscape](http://www.inkscape.org)
As GIMP is to Photoshop, Inkscape is to Illustrator. Inkscape is a free, multiplatform, vector editor that is less powerful than its commercial cousin but has the benefit of being a lot easier to use.
