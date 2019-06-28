# @titanium/imagefactory

![https://www.npmjs.com/package/@titanium/imagefactory](https://img.shields.io/npm/v/@titanium/imagefactory.png)


> Titanium native mobile image transformation functions including the ability to scale, crop, and compress images.

- [📝 Description](#-Description)
- [🚀 Getting Started](#-Getting-Started)
- [Accessing the Ti.ImageFactory Module](#Accessing-the-TiImageFactory-Module)
	- [Methods](#Methods)
		- [imageWithRotation(blob, options)](#imageWithRotationblob-options)
			- [Arguments](#Arguments)
		- [imageWithAlpha(blob, options)](#imageWithAlphablob-options)
			- [Arguments](#Arguments-1)
		- [imageWithTransparentBorder(blob, options)](#imageWithTransparentBorderblob-options)
			- [Arguments](#Arguments-2)
		- [imageWithRoundedCorner(blob, options)](#imageWithRoundedCornerblob-options)
			- [Arguments](#Arguments-3)
		- [imageAsThumbnail(blob, options)](#imageAsThumbnailblob-options)
			- [Arguments](#Arguments-4)
		- [imageAsResized(blob, options)](#imageAsResizedblob-options)
			- [Arguments](#Arguments-5)
		- [imageAsCropped(blob, options)](#imageAsCroppedblob-options)
			- [Arguments](#Arguments-6)
		- [imageTransform(blob, options)](#imageTransformblob-options)
			- [Arguments](#Arguments-7)
		- [compress(blob, quality)](#compressblob-quality)
			- [Arguments](#Arguments-8)
- [✨Features](#Features)
- [📚Learn More](#Learn-More)
- [📣 Feedback](#-Feedback)
- [©️ Legal](#️-Legal)


## 📝 Description

Ti.ImageFactory provides a set of image transformation functions including the ability to scale, crop, and compress images. Additionally, this module offers the functionality of adding alpha channels and transparent borders.  This is a repackaging of the compiled iOS and Android modules for [Ti.ImageFactory](https://github.com/appcelerator-modules/ti.imagefactory) to allow for installation via npm.

## 🚀 Getting Started

1. Install `@titanium/imagefactory` in root of project

```
npm install @titanium/imagefactory
```

## Accessing the Ti.ImageFactory Module

To access this module from JavaScript, you would do the following:

```js
var ImageFactory = require('ti.imagefactory');
```

### Methods

#### imageWithRotation(blob, options)

Creates a new image by creating a copy of the given image that is rotated.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * degrees[int]: The degrees to rotate the image

#### imageWithAlpha(blob, options)

Creates a new image by creating a copy of the given image, adding an alpha channel if it doesn't already have one.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * iOS: Currently there are no properties for this method -- specify an empty dictionary
    * Android: format [int]: The output format of the image: either ImageFactory.PNG or ImageFactory.JPEG (default: ImageFactory.JPEG)
    * Android: quality[float]: The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 0.7)

#### imageWithTransparentBorder(blob, options)

Creates a new image by creating a copy of the given image, adding a transparent border of the given size around its edges. The size of the image will be expanded by the specified border size.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * borderSize[int]: The size of the border (default: 1)
    * Android: format [int]: The output format of the image: either ImageFactory.PNG or ImageFactory.JPEG (default: ImageFactory.JPEG)
    * Android: quality[float]: The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 0.7)

#### imageWithRoundedCorner(blob, options)

Creates a new image by creating a copy of the given image with rounded corners.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
   * borderSize[int]: The size of the border (default: 1)
   * cornerRadius[int]: The radius of the corner edges (default: 0)
   * Android: format [int]: The output format of the image: either ImageFactory.PNG or ImageFactory.JPEG (default: ImageFactory.JPEG).
   * Android: quality[float]: The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 0.7).

#### imageAsThumbnail(blob, options)

Creates a new image by creating a copy of the given image that is squared to the thumbnail size.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * size[int]: The size of the thumbnail (default: 48)
    * borderSize[int]: The size of the border (default: 1)
    * cornerRadius[int]: The radius of the corner edges (default:0)
    * iOS: quality[int]: The interpolation quality. One of the following constants (default: imagefactory.QUALITY\_HIGH)
        * imagefactory.QUALITY\_DEFAULT
        * imagefactory.QUALITY\_NONE
        * imagefactory.QUALITY\_LOW
        * imagefactory.QUALITY\_MEDIUM
        * imagefactory.QUALITY\_HIGH
    * Android: quality[float]: The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 0.7)
    * Android: dither[boolean]: Indicates if dithering should be applied while scaling. May provide better quality (default: true)
    * Android: format [int]: The output format of the image: either ImageFactory.PNG or ImageFactory.JPEG (default: ImageFactory.JPEG)

#### imageAsResized(blob, options)

Creates a new image by creating a copy of the given image that is rescaled to the specified size.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * width[int]: The width of the new image (default: image width)
    * height[int]: The height of the new image (default: image height)
    * iOS: hires[boolean]: Create a hires image (for Retina displays only)
    * iOS: quality[int]: The interpolation quality. One of the following constants (default: imagefactory.QUALITY\_HIGH)
        * imagefactory.QUALITY\_DEFAULT
        * imagefactory.QUALITY\_NONE
        * imagefactory.QUALITY\_LOW
        * imagefactory.QUALITY\_MEDIUM
        * imagefactory.QUALITY\_HIGH
    * Android. format [int]: The output format of the image: either ImageFactory.PNG or ImageFactory.JPEG (default: ImageFactory.JPEG)
    * quality[float]: The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 0.7)

#### imageAsCropped(blob, options)

Creates a new image by creating a copy of the given image that is cropped to the specified bounds.

##### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * width[int]: The width of the new image (default: image width)
    * height[int]: The height of the new image (default: image height)
    * x[int]: The x-coordinate of the upper-left corner of the bounds (default: image center - width / 2)
    * y[int]: The y-coordinate of the upper-left corner of the bounds (default: image center - height / 2)
    * Android: format [int]: The output format of the image: either ImageFactory.PNG or ImageFactory.JPEG (default: ImageFactory.JPEG)
    * Android: quality[float]: The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 0.7)

#### imageTransform(blob, options)

Creates a new image by applying a sequence of transformations to the image.

##### Arguments

* Image blob[blob]: Image to transform
* Transform[dictionary]: A sequence of transform specifications. Transforms are listed as additional parameters to the function and are applied in the order specified. Each transform is a dictionary with the options described above for each transform along with an additional 'type' property included with each dictionary of transform options.
    * type[int]: The identifier of the transform to apply. One of the following constants
        * imagefactory.TRANSFORM\_CROP
        * imagefactory.TRANSFORM\_RESIZE
        * imagefactory.TRANSFORM\_THUMBNAIL
        * imagefactory.TRANSFORM\_ROUNDEDCORNER
        * imagefactory.TRANSFORM\_TRANSPARENTBORDER
        * imagefactory.TRANSFORM\_ALPHA
    * options as described in the above transforms

#### compress(blob, quality)

Creates a new image by creating a copy of the given image and applying the specified compression quality.

##### Arguments

* Image blob[blob]: Image to compress
* Compression Quality[float]; The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 1.0)




## ✨Features

iOS: `ti.imagefactory 1.3.0`
Android: `ti.imagefactory 4.0.0`

* [x] Scale images
* [x] Crop images
* [x] Compress images
* [x] Add alpha channel to images
* [x] Add transparent borders to images


## 📚Learn More

- [Ti.Identity GitHub Repo](https://github.com/appcelerator-modules/titanium-imagefactory)

## 📣 Feedback

Have an idea or a comment?  [Join in the conversation here](https://github.com/brentonhouse/titanium-imagefactory/issues)! 

## ©️ Legal

Modules are licensed under Apache 2.0 from https://github.com/appcelerator-modules/titanium-identity

Alloy is developed by Appcelerator and the community and is Copyright © 2012-Present by Appcelerator, Inc. All Rights Reserved.

Alloy is made available under the Apache Public License, version 2. See their license file for more information.

Appcelerator is a registered trademark of Appcelerator, Inc. Titanium is a registered trademark of Appcelerator, Inc. Please see the LEGAL information about using trademarks, privacy policy, terms of usage and other legal information at http://www.appcelerator.com/legal.