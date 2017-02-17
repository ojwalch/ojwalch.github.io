---
layout: post
title: Cool warps
categories: code art
---

When I was first learning complex analysis, I thought conformal mappings were too cool not to mess around with. In doing so, I ended up writing code to make some sweet conformal mapping art, as well as some sick warping GIFs. The Matlab code to make the GIFs is on [my GitHub page](https://github.com/ojwalch/cool-warps), and some sample outputs are below. 


But first, a little more detail: 

Conformal mappings are mappings that preserve angles locally. If I map an image in a conformal way, then if you zoom in enough on a spot in the output, it will eventually look like a zoomed in version of the original (albeit likely rotated). This code generates warping GIFs by interpolating between (i.e. blending) conformal mappings of the complex plane. 

In all of the following, I assume that I tile the complex plane with the given image. Then I iterate over all the pixels in the output to assign a value to each one. The values come from mapping the pixel positions in the output by the inverse function of the conformal map we’re trying to achieve and then modding by the dimensions of the image (hence, the tiling assumption). 

For each GIF, I randomly generate an order for my pre-coded set of mappings, which should be conformal in the first quadrant. Then I interpolate from one to the next to create the cool space zoom effects; this often, but not always, preserves the assumption that things will be conformal, so it’s fun to look out for points in the GIFs where the map’s no longer conformal and the outputs look weird. 

{% include conformal_gallery.html %}




