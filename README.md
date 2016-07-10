VS2015 & Qt4
============

# source

Download modified source that can be build with vs2015: <http://whudoc.qiniudn.com/2016/qt-src-4.8.7-vs2015.7z> (41.5 MB).
This is based on qt official release 4.8.7 (last qt4 release), and patched necessary modifications so that it can be
successfully compiled by vc14 (vs2015). The patch is offerred by [sandym/qt-patches](https://github.com/sandym/qt-patches).

# build

checkout my demo: **<http://whudoc.qiniudn.com/2016/vs2015-qt4-playground.zip>** (14 MB).

14 MB = 13.6 MB of qt4 prebuild (release version only, a tiny qt4!) + 1 demo qt project.

# use my build

The README.txt inside is written in chinese, steps are:

-   unzip `qt4-vs2015x64.7z` in current dir;
-   open CMD: hold <kbd>Shift</kbd>, right click, then hit <kbd>w</kbd>, <kbd>Enter</kbd>;
-   set environment varible: type in CMD "`set PATH=%CD%\qt4-vs2015x64\bin;%PATH%`";
-   open cmake-gui: type in CMD "`cmake-gui demo`";
-   build vs2015 project: 1) set build dir; 2) set compilation option to `VS2015 WIN64`; 3) configure, build;
-   use vs2015 to open `.sln` file in build dir, build the **release** version (not debug!).

# make a build

```
# download source code at <http://whudoc.qiniudn.com/2016/qt-src-4.8.7-vs2015.7z> (41.5 MB).
mkdir qt-build-4.8.7
cd qt-build-4.8.7
..\qt-src-4.8.7\configure.exe -prefix C:\Qt\VS2015x64\qt-4.8.7 -developer-build -opensource -confirm-license -debug-and-release -no-qt3support -no-multimedia -no-audio-backend -no-phonon -no-phonon-backend -no-libtiff -no-libmng -no-dbus -no-nis -no-webkit -nomake doc -nomake examples -nomake demos -no-gtkstyle -platform win32-msvc2015
nmake
```

For details, check out sandym's [qt-patches/windows/qt-4.8.7 at master · sandym/qt-patches](https://github.com/sandym/qt-patches/tree/master/windows/qt-4.8.7).

# credits

-   Qt team
-   [sandym/qt-patches: Patches to some release versioin of Qt I use](https://github.com/sandym/qt-patches)

---

# more builds

some builds are small, some builds are big.

## build #1

**configure**

```
..\qt-src-4.8.7\configure.exe -prefix C:\Qt\VS2015x64\qt-4.8.7 -opensource -confirm-license -developer-build -debug-and-release -nomake doc -nomake examples -nomake demos -platform win32-msvc2015 -no-qt3support -no-phonon -no-phonon-backend -no-dbus -no-nis -qt-libpng -qt-libjpeg -qt-libmng -no-openssl
```

**build**
