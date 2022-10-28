---
id: gcs443bkq3air9kdnx6k5bh
title: Pixel versus Point Coord
desc: ''
updated: 1658816691420
created: 1658816564123
---

The DjVu technology relies on the accurate superposition of images at different resolutions.
Such an accuracy cannot be reached with the usual assumption
that pixels are small enough to be considered infinitesimally small.
We must distinguish very precisely "points" and "pixels".
This distinction is essential for performing scaling operations.

The pixels of an image are identified by "pixel coordinates".
The bottom-left corner pixel has coordinates `(0,0)`
and the top-right corner pixel has coordinates `(w-1,h-1)`
where `w` and `h` are the image size.
Pixel coordinates are necessarily integers since pixels never overlap.

An infinitesimally small point is identified by its "point coordinates".
There may be fractional point coordinates, although this library does not
make use of them.
Points with integer coordinates are located **on the corners of each pixel**.
They are not located on the pixel centers.
The center of the pixel with pixel coordinates `(i,j)`
is located at point coordinates `(i+1/2,j+1/2)`.
In other words, the pixel `(i,j)` extends from point `(i,j)` to point `(i+1,j+1)`.

Therefore, the point located on the bottom left corner of an image has coordinates `(0,0)`.
This point is in fact the bottom left corner of the bottom left pixel of the image.
The point located on the top right corner of an image has coordinates `(w,h)`
where `w` and `h` are the image size.
This is in fact the top right corner of pixel `(w-1,h-1)`
which is the image pixel with the highest coordinates.
