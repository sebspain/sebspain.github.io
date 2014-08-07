---
author: sspain
comments: true
layout: post
slug: graphics-for-scientists-part-4-vector-file-formats
title: Graphics for Scientists - Part 4 - Vector File Formats
categories:
- Graphics
- Graphics for Scientists
- Science
---

_This is part of a series of posts about producing publication quality graphics. [See here for the introduction and links to other parts](http://sebspain.co.uk/graphics/graphics-for-scientists-intro/)._

In part [three](/2014/08/04/graphics-for-scientists-part-3-raster-file-formats.html) I went through the major raster image formats. Here I'll run through the most common vector ones and some advantages/disadvantages.

###Vector Formats

####EPS (.eps)
Encapsulated PostScript has been a standard "publication/print quality" vector format for many years but it is not well known outside of professional publishing. The EPS format is now very old (it a derivative of PostScript, released in 1982) so is not very advanced but still maintains strong support from publishers.

#####Advantages

- widely accepted industry standard

#####Disadvantages

- poor software support*
- no support for layers
- no support for transparency

####PDF (.pdf)
You'll be familiar with Portable Document Format (PDF), particularly for written documents, but PDF is also a very good vector format. 

#####Advantages
- easily read, [there are many viewers/readers](http://en.wikipedia.org/wiki/List_of_PDF_software)
- commonly accepted
- supports layers, transparency etc

#####Disadvantages
- perceived to be difficult to edit/create (they aren't!)
- poor software support*

####SVG (.svg)
Scalable Vector Graphics (SVG) are a relative new comer. Originally designed as an open standard vector format for the web they are becoming more common for general graphics work, although I don't know of any publishers that accept them directly. In essence they are text file that is interpreted into an image so they can easily be compressed in a lossless manner and even searched. For example, the brief code below defines the image beneath it. However, in general you create them with a graphics package.

```{xml}
<svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="160px" height="160px">
  <rect x="5" y="5" width="150" height="150" fill="rgb(127, 127, 127)" stroke-width="5" stroke="rgb(0, 0, 0)" />
  <circle cx="80" cy="80" r="50" stroke="rgb(0,0,0)" stroke-width="1" fill="rgb(127,127,255)" />
</svg>
```

![SVG Example](http://sebspain.co.uk/files/2014/08/07/example.svg)

#####Advantages
- open standard resulting in high uptake
- can be viewed with [most web browsers](http://en.wikipedia.org/wiki/Scalable_Vector_Graphics#SVG_on_the_web)
- supports transparency etc

#####Disadvantages
- not commonly accepted by publishers
- some compatibility issues when opening files created in different software
- no "real" layers
- poor software support*

####WMF/EWF (.wmf/.emf)
Windows/Enhanced Metafiles are Microsoft's own vector format.

#####Advantages
- good software support
- easily created without specialist software (MS Office will do)

#####Disadvantages
- not widely accepted
- basic 

---

\* A quick explanation of what I mean by software support using PDF as an example. There are many bits of software that will happily read and write PDF files, most "scientific" software (e.g. ChemDraw, Prism, Origin) can produce them directly, so in that sense software support is good. However, a large number of users still use Microsoft Word for writing papers (due to collaborators, this includes me) which has poor support for inserting vector graphics except Microsoft's own metafile formats (it's a bit more complicated than that but I'll cover that later). In that sense software support is poor.

