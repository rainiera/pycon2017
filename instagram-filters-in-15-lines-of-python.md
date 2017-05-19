## Instagram Filters in 15 Lines of Python

speaker: Michele Pratusevich  
time: Friday 2:35 pm - 3:05 pm  
[description](https://us.pycon.org/2017/schedule/presentation/485/)  
[slides](http://www.practicepython.org/pycon2017slides)  

- computer vision researcher at Amazon
- maintainer of Practice Python blog

## Goal

- Gotham filter (in color)

## Image Basics

- Load image
- What is an image?
    - (R, G, B)
        - uint8 [0, 256]
        - convert image to floats
        - Map 0-255 to 0-1
    - We want to look at each channel (R, G, B) separately
    - Then we want to merge the channels back into an image
    - Image histograms - like those seen in Gimp/Photoshop - let us visualize how many of each pixel value exists in a  channel

## Basic building blocks of Instagram filters

**Components**

1. Sharpening and blurring
    - We use a gaussian blur, which replaces each pixel with a weighted sum of the neighboring pixels
    - To sharpen an image, subtract out the blurry bits - but make sure to add enough of the regular image back
        - skimage.filters.gaussian, then np.clip
2. Channel interpolation
    - take the histogram, stretch then squeeze it.

## The Gotham filter

- mid-tone contrast boost
- blacks -> bluer
- sharpening
- boost in blue channel for lower mid-tones
- decr in blue channel for upper mid-tones

## The code

- [slides](http://www.practicepython.org/pycon2017slides)  

