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

Now that you know about the different types of graphics files you need to know what software you can use to create them. If we look at the figure mock-up below we have various types of data in one figure:

A. A chemical reaction scheme

B. A graph/plot of some kind

C. A microscopy image or other "photograph"

D. A schematic

So we need to be able to produce each of these parts and then put them all together and add annotations like the labeling of the sub-figures.

![Mock-up of a compound figure](http://sebspain.co.uk/files/2014/08/07/mock_figure.png)

####Chemical Structure Drawing
The _de facto_ 2D chemical drawing package is [Chem(Bio)Draw](http://www.cambridgesoft.com/Ensemble_for_Chemistry/ChemBioDraw/Default.aspx). It has the best tools and templates, and can export to a wide range of formats including EPS, PDF and SVG, and a variety of raster formats as well.

I also recommend [Marvin Sketch](http://www.chemaxon.com/products/marvin/marvinsketch/) which has free academic licenses available if you don't have, or can't afford, a ChemDraw license. It runs on almost anything, including Linux, can export to useful formats and has some nice features including the ability to save each structure in a scheme to individual files that can then be used later.

####Graphing Software
There are a lot of good graphing and data analysis softwares available. The golden rule in making publication quality graphs is...


#####Don't use Excel
<!---
add in link once written above the evils of office

add in link to post about file sizes, efficiency and vector vs. raster
-->

There are various reasons for this that I'll expand upon in a later post but the main problem is that Excel cannot export graphs to a good vector format and that's how graphs should be exported (again, I'll expand on this later).

Graphing software that will produce good quality vector graphics include:

#####[Graphpad Prism](http://www.graphpad.com/scientific-software/prism/)
This would be my general recommendation for good data analysis/stats/graphing software. Runs on both Windows and Mac, user friendly with a [great online guide](http://www.graphpad.com/guides/prism/6/user-guide/) and can produce layouts of multiple graphs easily.

#####[SigmaPlot](http://www.sigmaplot.co.uk/products/sigmaplot/sigmaplot-details.php)
Windows only but still very good.

#####[Origin](http://www.originlab.com/index.aspx?go=PRODUCTS/Origin)
Windows only. One of the most powerful data analysis packages there is but licenses are expensive.

#####[R](http://www.r-project.org/)
My personal favourite. It runs on anything but is command-line based so has a steep learning curve. The plot above is made with R.


####"Photographs"






