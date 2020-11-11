# webp2img

![Default usage](/webp2img-default-usage.gif)

### Convert WebP files into JPG, JPEG or PNG

Watch a folder to automatically convert any _.webp_ files in it.

## Requirements

### ImageMagick

> Use ImageMagick® to create, edit, compose, or convert bitmap images. It can read and write images in a variety of formats (over 200) including PNG, JPEG, GIF, HEIC, TIFF, DPX, EXR, WebP, Postscript, PDF, and SVG. ImageMagick can resize, flip, mirror, rotate, distort, shear and transform images, adjust image colors, apply various special effects, or draw text, lines, polygons, ellipses and Bézier curves.
>
> [...]
>
> It runs on Linux, Windows, Mac Os X, iOS, Android OS, and others
>
> https://imagemagick.org/

**Why?** This script uses the [`convert` command](https://imagemagick.org/script/convert.php) from ImageMagick.

Following the official documentation for installation: https://imagemagick.org/script/download.php

If you're using **macOS** you may use [Homebrew](https://brew.sh/) to install it:

```
# ImageMagick dependency
$ brew install ghostscript

# ImageMagick itself
$ brew install imagemagick
```

## Install

```
# Copy the src to bin
$ cp /webp2img/src/webp2img /usr/local/bin/webp2img

# Or move it instead of creating a copy
$ mv /webp2img/src/webp2img /usr/local/bin/webp2img

# Then make it executable (to use it globally)
$ chmod +x /usr/local/bin/webp2img
```

## Usage

### Default

```
# Move into the folder which holds your ".webp" files, then:
$ webp2img
```

This will run the script using the default options (see below).

### Options

| Flag          | Description    | Default |
| :------------- |:-------------| :-----:|
| -e (_extension_) <(jpg/jpeg/png) string> | Define which extension the `.webp` files will be coverted to | jpg ||
| -l (_loop_) <(seconds) int> | Loop folder every _n_ seconds | 2 ||
| -r (_recursive_) <(depth) int> | Into how much depth should the script look for `.webp` files | 1 (_only current directory_) ||
| -k (_keep_) | Keep the file after converting it (do not delete it) | – ||
| -q (_quiet_) | Do not output any message nor info into the console | – ||
| -h (_help_) | Display usage | – ||

You can combine all these in a single command, like so:

```
$ webp2img -e png -l 5 -r 3 -k -q
```

**The command above will:**

- Convert any ".webp" to ".png"
- Loop the current directory every 5 seconds
- Look for files in the current directory and 2 subdirectories depth
- Keep the original ".webp" files
- Don't show any message in the terminal (quiet)
