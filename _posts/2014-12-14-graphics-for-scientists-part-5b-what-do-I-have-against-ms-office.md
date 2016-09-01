---
author: sspain
comments: true
layout: post
slug: graphics-for-scientists-part-5b-what-do-I-have-against-ms-office
title: Graphics for Scientists - Part 5b - What do I have against MS Office?
categories:
- graphics for scientists
- graphics
- software
- Microsoft Office
---

_This is part of a series of posts about producing publication quality graphics. [See here for the introduction and links to other parts](/2013/01/29/graphics-for-scientists-intro.html)._

In [my last post](/2014/08/11/graphics-for-scientists-part-5-software.html) I introduced two golden rules for making publication quality graphics.

1. Don't use Excel
2. Don't use Powerpoint

If you know me, you'll probably know I have a near pathological hatred of Microsoft Word, but I reluctantly use it for writing papers with collaborators who don't use $\LaTeX$. However, I still occasionally use Excel and Powerpoint out of choice, so why am I so against them for creating graphics?
Basically it comes down to having the right tool for the job.
You *can* use Powerpoint for making figures and, with some workarounds, you [can produce something of near publication quality](http://support.microsoft.com/kb/827745).
Similarly, you can cut a plank of wood with a chisel, but using a saw is going to be quicker, easier, and give a better result.

The main reason for not using in are the poor choices for exporting to a usable format, go and try saving an image of a graph from Excel, here are some other reasons not ot use Excel:

### It's statistically flawed.
The statistical analyses in Excel are known to be full of errors. There have been multiple papers written on the subject [1], and yet many of them still haven't been fixed by Microsoft, although that may be changing [2].
Basically, Excel is pretty crap at data analysis so you may as well use something else.


### The default graphs are *ugly*.
Take the two graphs below, made using the default settings from Office 2011 (left) and Prism 6.0e (right).
Which one of these looks like it belongs in an scientific publication?
I'd guess most people would pick the one on the right.

![Comparison of the default scatter plot and trendline formatting for Excel 2011 and Prism 6](http://spain-lab.co.uk/files/2014/12/14/excel_vs_prism.png)

You can change a lot of settings to make an Excel plot look "right" but it's extra, unnecessary effort.

### Excel makes it easy to represent data badly.
This isn't really a flaw in Excel as the user is responsible for choosing how data should be represented.
However, the corporate environment seems to have been seduced by the idea that fancy colours, gradients and 3D effects are important for graphs and Microsoft seemingly provide more eye-bleeding monstrocities for them in each release.
I won't go into too much detail here as I have a post coming up on data representation but by way of example look at the two bar charts below.
I have seen both of these charts used in papers and conference presentation despite them making even the most basic bit of information hard to see.
If you don't have these options you can't use them.

![Examples of 3D Bar Charts made with Excel](http://spain-lab.co.uk/files/2014/12/14/excel_3D_bar_plots.png)

### References

1. a). D. McCullough and B. Wilson; "On the accuracy of statistical procedures in Microsoft Excel 97", Comput. Stat. Data An. 1999, **31**, 27-37. [\[DOI\]](http://dx.doi.org/10.1016/S0167-9473(99)00004-3).
b) B. D. McCullough and B. Wilson; "On the accuracy of statistical procedures in Microsoft Excel 2003", Comput. Stat. Data An. 2005, **49**, 1244-1252. [\[DOI\]](http://dx.doi.org/10.1016/j.csda.2004.06.016)
c) B. D. McCullough and D. A. Heiser; "On the accuracy of statistical procedures in Microsoft Excel 2007", Comput. Stat. Data An. 2008, **52**, 4570-4578. [\[DOI\]](http://dx.doi.org/10.1016/j.csda.2008.03.004)
d) For more info see [here](http://www.practicalstats.com/xlsstats/excelstats.html)

2. G. Melard; "On the accuracy of statistical procedures in Microsoft Excel 2010", Comput. Stat. 2014. [\[DOI\]](http://dx.doi.org/10.1007/s00180-014-0482-5)
