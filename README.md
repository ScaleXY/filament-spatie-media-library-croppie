# Filament Spatie Media Library Croppie Plugin

[![Latest Version on Packagist](https://img.shields.io/packagist/v/scalexy/filament-spatie-media-library-croppie.svg?style=flat-square)](https://packagist.org/packages/scalexy/filament-spatie-media-library-croppie)
[![Total Downloads](https://img.shields.io/packagist/dt/scalexy/filament-spatie-media-library-croppie.svg?style=flat-square)](https://packagist.org/packages/scalexy/filament-spatie-media-library-croppie)


## Installation

You can install the package via composer (no need to install croppie as well as its assets are bundled):

```bash
composer require scalexy/filament-spatie-media-library-croppie
```

To use outside filament (e.g. with just the forms package), add the js and css to your vite (or mix) config:
```html
@vite([
    'vendor/scalexy/filament-spatie-media-library-croppie/resources/dist/js/filament-spatie-media-library-croppie.js',
    'vendor/scalexy/filament-spatie-media-library-croppie/resources/dist/css/filament-spatie-media-library-croppie.css',
    ...
])
```

This field extends and therefore has all the functionality of the [Filament Spatie Media Library Plugin](https://filamentphp.com/docs/2.x/spatie-laravel-media-library-plugin/installation) field.

```php
SpatieMediaLibraryCroppie::make('image')
    ->boundaryWidth('100%')
    ->boundaryHeight('600'),
```
Use `boundaryWidth` and `boundaryHeight` to set width and height of the image area in the modal. The values above are the defaults.

```php
SpatieMediaLibraryCroppie::make('image')
    ->viewportWidth('400')
    ->viewportHeight('400'),
```
Use `viewportWidth` and `viewportHeight` to set width and height of the cropper itself. Values above are the defaults.

```php
SpatieMediaLibraryCroppie::make('image')
    ->showZoomer(),
```

`showZoomer` can be called to show the zoom bar below the image in the modal.

```php
SpatieMediaLibraryCroppie::make('avatar')
    ->avatar(),
```
We can make croppie circular using `avater` method.
```php
Croppie::make('background')
    ->modalSize('6xl')
    ->modalHeading("Crop Background Image")
```

Modal size can be customized using `modalSize` method.
For setting the heading use `modalHeading`.

### Set image quality and format
If your cropped images are very large (see: [https://github.com/Foliotek/Croppie/issues/444]), you can use the `imageFormat()` and `imageQuality()` methods to modify the resulting image.
```php
SpatieMediaLibraryCroppie::make('image')
    ->imageFormat('jpeg')
    ->imageQuality(0.7);
```
Defaults are:
* `imageQuality(0.9)`
* `imageFormat('png')`

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## Acknowldgements

This is a fork of [josefbehr/FilamentCroppie](https://github.com/josefbehr/FilamentCroppie), which in turn is a fork of of [nuhel/FilamentCroppie](https://github.com/nuhel/FilamentCroppie) that extended and adapted to use spatie/media-library and install croppie via npm.

## Changelog
v0.0.1
* fork `josefbehr/filament-croppie` and rename everything
