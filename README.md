# Statically Linked FFMPEG for FreeBSD

Patches are made from [these](https://www.freshports.org/multimedia/ffmpeg/)

Build hints from [here](https://github.com/zimbatm/ffmpeg-static) and [here](https://github.com/markus-perl/ffmpeg-build-script)

# WHY?! Statically Linking is generally a Bad Idea(tm)!
Yes, but node packages *REALLY* like statically linked FFMPEG and FreeBSD is pretty decent with symbol versioning so we can have this.

## Build settings and library versions (5.1) (FreeBSD 12.2 AMD64)
--enable-static --disable-shared --disable-ffplay --enable-gpl --enable-libfreetype --enable-libx264 --enable-libx265 --enable-libass --enable-libmp3lame --enable-libopus --enable-libvpx --enable-libsoxr --enable-libvidstab --enable-libopenjpeg --enable-libzimg --enable-libwebp --enable-libvorbis --enable-libspeex --enable-libxvid --enable-libvmaf --enable-libzmq --enable-libaom --enable-libzvbi --enable-libdav1d --enable-libsnappy --enable-libmodplug --enable-libtheora --enable-libtwolame --enable-libmysofa --enable-libbluray --enable-libgme --enable-libgsm --enable-librubberband --enable-fontconfig --enable-runtime-cpudetect  --enable-version3 --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libopenh264 

other libraries:

| library | version |
| --- | --- |
| libavutil   |   57. 28.100 / 57. 28.100 |
| libavcodec   |  59. 37.100 / 59. 37.100
| libavformat   | 59. 27.100 / 59. 27.100
| libavdevice   | 59.7.100 / 59.7.100
| libavfilter   |  8. 44.100 /  8. 44.100
| libswscale    |  6.  7.100 /  6.  7.100
| libswresample |  4.  7.100 /  4.  7.100
| libpostproc   | 56.  6.100 / 56.  6.100

not used:
--enable-libvo-amrwbenc (very old, opencore likely better)

## Build settings and library versions (5.1.1) (FreeBSD 13.1 AMD64) (EXPERIMENTAL Please test)
--enable-gpl --enable-libdav1d --enable-libsvtav1 --enable-librav1e --enable-libx264 --enable-libx265 --enable-libxvid --enable-libvidstab --enable-libaom --enable-libzimg --enable-libopencore_amrnb --enable-libopencore_amrwb --enable-libmp3lame --enable-libopus --enable-libvorbis --enable-lv2 --enable-libtheora --enable-libwebp --enable-libsrt --cc=cc --cxx=cpp --disable-debug --disable-doc --disable-shared --enable-pthreads --enable-static --enable-small --enable-version3 --extra-cflags='-static -I/root/ffmpeg-build-script/workspace/include -I/root/ffmpeg-build-script/workspace/include/lilv-0' --extra-ldexeflags=-static --extra-ldflags=-L/root/ffmpeg-build-script/workspace/lib --extra-libs='-static -ldl -lpthread -lm -lmd -lz' --pkgconfigdir=/root/ffmpeg-build-script/workspace/lib/pkgconfig --pkg-config-flags=--static --prefix=/root/ffmpeg-build-script/workspace --extra-version=5.1.1

This has TEST FAILURES!
```
--- ./tests/ref/fate/source     2022-08-31 10:10:03.000000000 -0600
+++ tests/data/fate/source      2022-09-13 21:29:26.489491438 -0600
@@ -1,26 +1,4 @@
 Files without standard license headers:
-libavcodec/file_open.c
-libavcodec/ilbcdata.h
-libavcodec/ilbcdec.c
-libavcodec/interplayacm.c
-libavcodec/log2_tab.c
-libavcodec/reverse.c
-libavdevice/file_open.c
-libavdevice/reverse.c
-libavfilter/af_arnndn.c
-libavfilter/file_open.c
-libavfilter/log2_tab.c
-libavformat/file_open.c
-libavformat/golomb_tab.c
-libavformat/log2_tab.c
-libswresample/log2_tab.c
-libswscale/log2_tab.c
-tools/uncoded_frame.c
-tools/yuvcmp.c
 Headers without standard inclusion guards:
-compat/djgpp/math.h
-compat/float/float.h
-compat/float/limits.h
-tools/decode_simple.h
 Use of av_clip() where av_clip_uintp2() could be used:
 Use of av_clip() where av_clip_intp2() could be used:
Test source failed. Look at tests/data/fate/source.err for details.
```

# Updates

This binary requires a large number of patches and rebuilds of components to function so it will lag behind any other FFMPEG-static binaries by quite a bit. If you want updates please **OPEN A TICKET** but keep in mind this is a rather low priority to me.

# TODO

 - Make this less painful to build if possible
 
# Bugs

 - It passes FATE but that does not mean it actually works

# License(s)

 - FFMPEG and components fall under GPLv3 AFAIK 

