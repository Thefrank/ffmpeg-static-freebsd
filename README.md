## Statically Linked FFmpeg for FreeBSD

Patches are made from [these](https://www.freshports.org/multimedia/ffmpeg/)

Build hints from [here](https://github.com/zimbatm/ffmpeg-static) and [here](https://github.com/markus-perl/ffmpeg-build-script)

## Why? Statically Linking is generally a Bad Idea(tm)!
Yes, but node packages *really* like statically linked FFmpeg and FreeBSD is pretty decent with symbol versioning so we can have this.

## Updates

This binary requires a large number of patches and rebuilds of components to function so it will lag behind any other FFmpeg-static binaries by quite a bit. 
If you want updates please **OPEN A TICKET** but keep in mind this is a rather low priority to me.

## TODO

 - ~Add support for HW accel~ Not possible?
 
## Bugs

 - 5.1 passes FATE
 - 5.1.1 has test failures
 - 7.0 lacks `libbluray` because of [this](https://code.videolan.org/videolan/libbluray/-/issues/43)
 - Please see X.X.X_buildconf.md for more details

## License(s)

 - FFmpeg and components fall under LGPL 2.1 and/or GPL2/GPL3
 - This is the final authority however https://www.ffmpeg.org/legal.html
