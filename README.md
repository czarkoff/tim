**tim** - *tiny image manipulator*

**About**

The idea of a program came to me when I had to create 4:3 thumbs for a group of different orientation images. I had to do my cropping with GIMP which isn't so suitable for such kind of manipulations.

The program takes an image and applies a given set of filters. One of them - cropping - is done in graphical mode.

**Requirements**

 * python 2.x (http://www.python.org/)
 * Tkinter (included with python)
 * PIL (http://www.pythonware.com/products/pil/)
 * Any graphical UI capable of Tk (X11, Windows, MacOS X etc.)
 * Mouse

**Installation**

On UNIX-like system it is just as simple as:

	$ chmod +x tim
	$ cp tim ~/bin/tim

On Windows You should rename the file *tim* to *whatever-you-like-to-call-it.py* (I would prefer *tim.py*) and put it somewhere in Your *PATH*.

**Current State**

It works and seems to be in a fairly good shape. A test on my system has given the following results: tim is only about 3% slower then ImageMagick's convert on the same operations, which is fairly nice as tim ads an extra step of rotating images according to EXIF data, providing the correctly orientated PNGs, which convert doesn't.

For now I'm waiting for Python3-compatible PIL release. Until that happens, nothing is going to change in this repo, I believe.

**Documentation**

Currently the project contains a single useful file that can be chmodded and placed wherever one wants within the *PATH*, so I don't think adding a manpage is a great idea.

Instead calling *tim* (or whatever You rename executable to) without options will give some help. Calling *tim -h* will give more help and a usage example.

**Todo**

 * rethink output patterns (eg. *%4d.jpg*) *(blocker for version **3**)*;
 * resolve image scroll problems in CropPhoto UI *(blocker for version **4**)*;
 * rethink the CropPhoto UI *(blocker for version **4**)*;
 * make py3k-safe (depends on PIL);
 * (possibly) add more patterns to match (depends on my imagination ;-));
 * (possibly) extend EXIF support (version 5? or PIL update?);
 * (possibly) make CropPhoto a normal standalone widget (version 4?);
 * (possibly) rewrite the program to use another imaging library (unlikely).

**Known Bugs**

 * PIL seems to be silently spoiling some images. As I can't reliably reproduce it in current version, tim just checks for image sanity after each iteration and exist with the corresponding error message if image gets damaged.
