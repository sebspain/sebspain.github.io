---
author: sspain
comments: true
layout: post
slug: graphics-for-scientists-part-3-raster-file-formats
title: Graphics for Scientists - Part 3 - Raster File Formats
categories:
- Graphics
- Graphics for Scientists
- Science
tags:
- science
- graphics
---

_This is part of a series of posts about producing publication quality graphics. [See here for the introduction and links to other parts](/2013/01/29/graphics-for-scientists-intro.html)._

In parts [one](/2013/01/29/graphics-for-scientists-part-1-raster-vs-vector-graphics.html) and [two](/2013/01/30/graphics-for-scientists-part-2-color-spaces-resolutions-and-compression.html) I introduced the main categories of image formats and some other basic concepts. Here I'll run through the most common raster ones and some advantages/disadvantages.

## Raster Formats

### TIFF (.tif/.tiff)
Tagged Image File Format (TIFF) is the "publication/print quality" raster format that you are most likely to come across. It's advanced format with some useful features including layers, transparency (aka alpha channels) and the ability to contain some vector information. This has made it the industry standard for raster images but there are some pitfalls that you need to avoid.

#### Advantages

- widely accepted industry standard
- can contain multiple layers, transparency, and vector components
- support for lossless compression

#### Disadvantages

- large size unless compressed
- support for lossy compression including JPEG
- poorly supported by software except specialist graphics programs

### PNG (.png)

Portable Network Graphics (PNG) is another common raster format that is being increasingly accepted by publishers.

#### Advantages

- often accepted for publication
- lossless compression is standard
- supports transparency
- widely read by non-specialist software (e.g. web browsers)
- small file sizes

#### Disadvantages

- no layer support

### JPEG (.jpg/.jpeg)

JPEG is the most common digital image format and is usually not accepted by publishers (in my experience).

#### Advantages
- easily read on by a very wide range of software/devices

#### Disadvantages
- rarely accepted by publishers
- lossy compression that can be varied in quality and can lead to very nasty artefacts


### GIF (.gif)

Graphics Interchange Format is commonly used for web-based graphics due to their small file sizes (a hangover from the days of 56 kbps modems). They are very limited apart from the ability to do animation.

#### Advantages
- you can make animations like this

![Under Construction GIF](http://www.textfiles.com/underconstruction/HeHeartlandEstates8832underconstruction.gif)

#### Disadvantages
- not accepted by publishers
- limited to 256 colors
- lossy compression
- everytime you use a gif for print publishing a graphic designer crys
- editors will assume you previously published you paper on geocities


### Bitmap (.bmp)

If you've used old (pre-Windows 95) version of Microsoft Paint you'll be familiar with bitmap graphics files. There's nothing really wrong with them but the files sizes are large unless you use compression. May as well use a TIFF.
