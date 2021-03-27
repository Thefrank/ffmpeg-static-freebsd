# ffmpeg-static-freebsd
static linked build of FFMPEG for FreeBSD

patches from: https://www.freshports.org/multimedia/ffmpeg/

patches from components also from ports tree where needed

build hints from: https://github.com/zimbatm/ffmpeg-static


built with:

--enable-gpl --enable-libfreetype --enable-libx264 --enable-libx265 --enable-libass --enable-libmp3lame --enable-libopus --enable-libvpx --enable-libsoxr --enable-libvidstab --enable-libopenjpeg --enable-libzimg --enable-libwebp --enable-libvorbis --enable-libspeex --enable-libxvid --enable-libvmaf --enable-libzmq --enable-libaom --enable-libzvbi --enable-libdav1d --enable-libsnappy --enable-libmodplug --enable-libtheora --enable-libtwolame --enable-libmysofa --enable-libbluray --enable-version3 --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libopenh264

not included but common in other static builds:
--enable-fontconfig  --enable-librubberband  --enable-libgsm --enable-gme

other libs:

libavutil      56. 72.100 / 56. 72.100

libavcodec     58.135.100 / 58.135.100

libavformat    58. 77.100 / 58. 77.100

libavdevice    58. 14.100 / 58. 14.100

libavfilter     7.111.100 /  7.111.100

libswscale      5. 10.100 /  5. 10.100

libswresample   3. 10.100 /  3. 10.100

libpostproc    55. 10.100 / 55. 10.100
