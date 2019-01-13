---
title: "Tesseract OCR"
date: "2019-01-07 9:24 PM"
summary: "Using Tesseract OCR and ImageMagick I made a little elisp script to convert images into text."
tags: ["programming", "emacs"]
---

I came across [tesseract](https://github.com/tesseract-ocr/tesseract) today, and found it quite useful.

Though I didn't have much success with JPEGs it did convert text from PNGs files without issue. This is because
the [lossy compression vs lossless compression](https://optimus.keycdn.com/support/lossy-vs-lossless) with JPEGs vs PNG files.

After googling a bit I found: https://gist.github.com/henrik/1967035 which goes through the steps of installing both
ImageMagick and Tesseract for MacOS:

### Install

`brew install imagemagick`

`brew install tesseract --with-all-languages`

This will get you what you need to convert images into text on the command line.

First you'll need to convert files into TIF (Tagged Image Format File) format to be able to feed into Tesseract.
This is meant to be a high quality image to be scanned by Tesseract ocr.

### Convert to TIF

`convert image.png -resize 400% -type Grayscale image.png.tif`

### Convert to text

`tesseract -l eng image.png.tif image.png`

Vola! The text in the image is stored in the output file `image.png.txt`.

## Emacs

With this, I'd like to build an emacs plugin that runs `tesseract` on any images I have open in a buffer. (images in emacs buffer render as an image).
So that, a new buffer window would either replace or open side-by-side with the text extracted from that image,

So far:

    (defun image-to-text ()
      (interactive)
      (if buffer-file-name
        (progn
          ;; Convert the file to a tif file for tesseract consumption.
          (shell-command (concat "convert " buffer-file-name " -resize 400% -type Grayscale " buffer-file-name ".tif"))
          ;; Convert the file from tif to txt using tesseract.
          (shell-command (concat "tesseract -l eng " buffer-file-name ".tif " buffer-file-name))
          ;; Delete the tif file artifact.
          (shell-command (concat "rm " buffer-file-name ".tif"))
          ;; Open the text file in buffer, this should be the text found in the image converted.
          (find-file (concat buffer-file-name ".txt")))))

And the working prototype in action:

![](http://g.recordit.co/cRLuAJfkA6.gif)
