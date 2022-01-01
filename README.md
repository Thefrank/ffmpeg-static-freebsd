# Statically Linked FFMPEG for FreeBSD

Patches are made from [these](https://www.freshports.org/multimedia/ffmpeg/)

Build hints from [here](https://github.com/zimbatm/ffmpeg-static) and [here](https://github.com/markus-perl/ffmpeg-build-script)

# WHY?! Statically Linking is generally a Bad Idea(tm)!
node packages *REALLY* like statically linked FFMPEG so here we are

## Build settings and library versions (4.4.1)
--enable-static --disable-shared --disable-ffplay --enable-gpl --enable-libfreetype --enable-libx264 --enable-libx265 --enable-libass --enable-libmp3lame --enable-libopus --enable-libvpx --enable-libsoxr --enable-libvidstab --enable-libopenjpeg --enable-libzimg --enable-libwebp --enable-libvorbis --enable-libspeex --enable-libxvid --enable-libvmaf --enable-libzmq --enable-libaom --enable-libzvbi --enable-libdav1d --enable-libsnappy --enable-libmodplug --enable-libtheora --enable-libtwolame --enable-libmysofa --enable-libbluray --enable-libgme --enable-libgsm --enable-librubberband --enable-fontconfig --enable-runtime-cpudetect  --enable-version3 --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libopenh264 

other libraries:

| library | version |
| --- | --- |
| libavutil   |   56. 70.100 / 56. 70.100 |
| libavcodec   |  58.134.100 / 58.134.100
| libavformat   | 58. 76.100 / 58. 76.100
| libavdevice   | 58. 13.100 / 58. 13.100
| libavfilter   |  7.110.100 /  7.110.100
| libswscale    |  5.  9.100 /  5.  9.100
| libswresample |  5.  9.100 /  5.  9.100
| libpostproc   | 55.  9.100 / 55.  9.100

not used:
--enable-libvo-amrwbenc (very old, opencore likely better)

# Updates

This binary requires a large number of patches and rebuilds of components to function so it will lag behind any other FFMPEG-static binaries by quite a bit. If you want updates please **OPEN A TICKET** but keep in mind this is a rather low priority to me.

# TODO

 - Make this less painful to build
 
# Bugs

 - It passes FATE but that does not mean it actually works

# License(s)

 - FFMPEG and components fall under GPLv3 AFAIK 

