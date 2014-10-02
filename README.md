pugpig-ad-template
==================

This repository includes source code for HTML ad templates created by [Kaldor Group](http://kaldorgroup.com).

### About

Our ad templates are designed and built to be 100% responsive and work across all platforms and devices. We support image based ad institials with the ability to add a link. The link is wrapped around the entire image however we plan to consider support for a template that allows more dynamic placement of the link area.


### Templates

We provide two templates:
* multiple-images
* single-image

Our multiple images template expects four image assets to best target all devices and orientations.
Our single image template can be used if only a single ad creative is supplied.

### Image Dimensions and Safe Zones 

For ad images in our multiple-images template we have specified dimensions below targeted for Apple iPhone and iPad devices. These are normally considered hero devices for ad creatives. On any other device or screen size including Android, Windows or Web the image will scale and letterbox appropriately.

* ‘tablet-landscape’ now referred as ‘large-landscape’ - 4:3 aspect ratio / 2048 x 1536 
* ‘tablet-portrait’ now referred as ‘large-portrait’ - 3:4 aspect ratio / 1536 x 2048 or 768

* ‘phone-landscape’ now referred as ‘small-landscape’ - 16:9 aspect ratio / 1136 x 640
* ‘phone-portrait’ now referred as ‘small-landscape’ - 9:16 aspect ratio / 640 x 1136

Every image above should have a 128px top unsafe zone to avoid important elements of the ad hidden by the iOS toolbar (which has some transparency).


![]( IMAGE URL HERE )

These unsafe zones are only relevant when the image is shown at actual size.
If the safe zones can’t be adhered in the ad creative then you can do the following:

* Open index.html and change:
body { padding-top: 0; } to body { padding-top: 64; } (line 13)
* Crop and adjust the image dimensions to account for the padding-top. We have provided image examples in alternative-assets/revised-for-64px-toolbar

This isn’t ideal however because top-padding will display across all devices including Android when it isn’t necessary.

For our single image ad template the image can be any size and aspect ratio.

If you want to use .jpgs over .pngs you will need to change image paths references in the following places:

* assets.manifest
* index.html
* style.css

### Manifest
Your ad should have a cache manifest file. 