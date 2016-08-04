VS2015 & Qt4
============

# source

Download modified source that can be build with vs2015: <http://whudoc.qiniudn.com/2016/qt-src-4.8.7-vs2015.7z> (41.5 MB).
This is based on qt official release 4.8.7 (last qt4 release), and patched necessary modifications so that it can be
successfully compiled by vc14 (vs2015). The patch is offerred by [sandym/qt-patches](https://github.com/sandym/qt-patches).

# demo build

Download the demo build: <http://whudoc.qiniudn.com/2016/vs2015-qt4-playground.zip> (14 MB).

14 MB = 13.6 MB of qt4 prebuild (release version only, a tiny qt4!) + 1 demo qt project.

Guide to `vs2015-qt4-playground.zip`                                    | `vs2015-qt4-playground.zip` 的使用指南
----------------------------------------------------------------------- | ------------------------------------
unzip `vs2015-qt4-playground.zip`                                       | 解压 `vs2015-qt4-playground.zip`
unzip `qt4-vs2015x64.7z`                                                | 解压 `qt4-vs2015x64.7z`
prepend to %PATH%: `path\to\vs2015-qt4-playground\qt4-vs2015x64\bin;`   | 把 `path\to\vs2015-qt4-playground\qt4-vs2015x64\bin;` 目录添加到环境变量 %PATH% 前面
use cmake-gui to build vs2015 project                                   | 用 cmake 生成 vs2015 工程
use vs2015 to open, build (release!), run                               | 用 vs2015 打开、编译（只能编译 release 版本）、运行

# make a build

1) <kbd>win</kbd>; 2) search "prompt x64"; 3) open "VS2015 x64 Native Tools Command Prompt".

```
# download source code at <http://whudoc.qiniudn.com/2016/qt-src-4.8.7-vs2015.7z> (41.5 MB).
mkdir qt-build-4.8.7
cd qt-build-4.8.7
..\qt-src-4.8.7\configure.exe -prefix C:\Qt\VS2015x64\qt-4.8.7 -developer-build -opensource -confirm-license -debug-and-release -no-qt3support -no-multimedia -no-audio-backend -no-phonon -no-phonon-backend -no-libtiff -no-libmng -no-dbus -no-nis -no-webkit -nomake doc -nomake examples -nomake demos -no-gtkstyle -platform win32-msvc2015
nmake
```

**remember to copy `src\corelib\global\qconfig.h` to `include\QtCore\qconfig.h`.**

For details, check out sandym's [qt-patches/windows/qt-4.8.7 at master · sandym/qt-patches](https://github.com/sandym/qt-patches/tree/master/windows/qt-4.8.7).

# credits

-   Qt team
-   [sandym/qt-patches: Patches to some release versioin of Qt I use](https://github.com/sandym/qt-patches)

---

# my builds

some builds are small (like the 14 MB `vs2015-qt4-playground.zip` demo build), some builds are big, like the following ones.

## build #1

**configure**

```
..\qt-src-4.8.7\configure.exe -prefix C:\Qt\VS2015x64\qt-4.8.7 -opensource -confirm-license -developer-build -debug-and-release -nomake doc -nomake examples -nomake demos -platform win32-msvc2015 -no-qt3support -no-phonon -no-phonon-backend -no-dbus -no-nis -qt-libpng -qt-libjpeg -qt-libmng -no-openssl
```

**build**

<http://whudoc.qiniudn.com/2016/qt-4.8.7-vs2015-build1.7z> (108 MB).

## how to use these builds

1.  download a build, let's see [`qt-4.8.7-vs2015-build1.7z`](http://whudoc.qiniudn.com/2016/qt-4.8.7-vs2015-build1.7z) (zipped 108 MB, unzipped: about 951 MB).
2.  unzip it to a dir, let's see `c:\vs2015x64`, so the `<build dir>` is `c:\vs2015x64\qt-4.8.7`
3.  add `<build dir>\bin` to %PATH%
4.  use cmake to build vs2015 project, then vs2015 to build & run, that's it.
