# FFmpeg-7.1.1
编译FFmpeg所需要的操作及必要文件

1.安装依赖
```
sudo apt update && \
sudo apt upgrade -y && \
sudo apt install -y build-essential
```

2.安装依赖
```
sudo apt install -y gnutls-dev \
libass-dev \
libdrm-dev \
libopus-dev \
libpulse-dev \
libspeex-dev \
libtheora-dev \
libtwolame-dev \
libv4l-dev \
libvorbis-dev \
libvpx-dev \
libx264-dev \
libx265-dev \
libxvidcore-dev \
libopenal-dev \
libomxil-bellagio-dev \
libxcb1-dev \
libva-dev \
libvdpau-dev
```

3.安装依赖
```
tar -xvf fdk-aac-2.0.2.tar.gz && \
cd fdk-aac-2.0.2 && \
./configure --prefix=/usr --disable-static && \
make -j12 && \
sudo make install && \
cd .. && \
tar -xvf lame-3.99.5.tar.gz && \
cd lame-3.99.5 && \
./configure --prefix=/usr --disable-static && \
make -j12 && \
sudo make install && \
cd .. && \
tar -xvf opencore-amr-0.1.6.tar.gz && \
cd opencore-amr-0.1.6 && \
./configure --prefix=/usr --disable-static && \
make -j12 && \
sudo make install
```

4.编译安装
```
tar -xvf ffmpeg-7.1.1.tar.xz
```
```
cd ffmpeg-7.1.1
```
```
./configure --prefix=/usr/local \
--disable-debug \
--disable-doc \
--disable-static \
--enable-libdrm \
--enable-ffplay \
--enable-gnutls \
--enable-gpl \
--enable-libass \
--enable-libfdk-aac \
--enable-libfontconfig \
--enable-libfreetype \
--enable-libmp3lame \
--enable-libopencore_amrnb \
--enable-libopencore_amrwb \
--enable-libopus \
--enable-libspeex \
--enable-libtheora \
--enable-libtwolame \
--enable-libv4l2 \
--enable-libvorbis \
--enable-libvpx \
--enable-libx264 \
--enable-libx265 \
--enable-libxcb \
--enable-libxvid \
--enable-nonfree \
--enable-omx \
--enable-openal \
--enable-runtime-cpudetect \
--enable-shared \
--enable-vaapi \
--enable-vdpau \
--enable-version3 \
--libdir=/usr/local/lib \
--incdir=/usr/local/include \
--disable-asm \
--disable-x86asm \
--extra-cflags=-fPIC \
--toolchain=hardened \
--disable-stripping \
--extra-cflags=-I/usr/local/include/ffnvcodec
```
```
make -j $(nproc)
```
```
sudo make install
```

5.查看安装效果
重启后执行
```
ffmpeg -hwaccels
```
