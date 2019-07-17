# course-markdown-slides-template

This repo contains two versions of my implementation of [gnab](https://github.com/gnab)'s markdown-driven slideshow tool, [remark.js](https://remarkjs.com/), for a college course. 

## Version 1: HTML + Markdown File

This version uses a largely unmodified version of the remark.js repo files, with fonts and other assets for convenient use offline. See [Aldebert](https://galdebert.github.io/posts/remark-1/) for more info.

Parts of the repo needed for this version:
- _assets_ folder
- _images_ folder
- _index1.html_ file (you should rename this to "index.html" and you may delete _index1.html_ if you decide on this version).

Version 1 can be opened locally in your browser or it can be hosted online.

## Version 2: HTML File + Multiple or Single Markdown File(s)

This version builds on the original code, but builds on modfications suggested by [eljefe6a](https://github.com/eljefe6a) to combine multiple markdown files from a specified folder. 

Parts of the repo needed for this version:
- _assets_ folder
- _images_ folder
- _index2.html_ file (you should rename this to "index.html" and you may delete _index1.html_ if you decide on this version).
- Files in the _slides_ folder 

Version 2 can be hosted online, but requires some extra steps to open it locally in your browser. These are the steps:

(Requires Python):

Input the following command into terminal/commandline at the directory where your _index.html_ file is stored
```
python3 -m http.server
```

You can then access your slideshow locally in your browser at:
```
http://localhost:8000/
```

### Using the ```---```
I provide an assortment of example slides in the _slides_ folder for illustration. Following the remark documentation, ```---``` is used to indicate the start of a new slide. Because all of the .md files are merged using javascript into the html output, each .md file ends with, but does not begin with ```---```.

### Ordering slides

Often lecturers will need to change the order of slides. Markdown files should be prefixed with numbers indicating the order of desired appearance in the slideshow. The user must provide the full file names (including numbers) to the ```files``` variable in the javascript section of the _index.html_ file. The elements of ```files``` are sorted numerically using regex so quite a few variations are allowed, such as ```1intro.md```, ```2_nature_of_il.md```, or ```3-sources_of_il.md```, for example.

### Omitting slides
To omit slides, you may either:
    1. Erase the contents of the .md file (see _12judicial_dispute_resolution.md_)
    2. Remove reference to the file in the ```file``` variable. Simply removing slide files will produce an error when the file name is called by the javascript.


Helpful links:

- [Online and Offline Slides Using Markdown and Remark](https://galdebert.github.io/posts/remark-1/)
- [Remark documentation](https://github.com/gnab/remark)
- [Demo on my github.io](https://joshuascriven.github.io/democms)