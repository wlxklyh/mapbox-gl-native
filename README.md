# Mapbox GL Native

[![Circle CI build status](https://circleci.com/gh/mapbox/mapbox-gl-native.svg?style=shield)](https://circleci.com/gh/mapbox/workflows/mapbox-gl-native/tree/master) [![Coverage Status](https://codecov.io/gh/mapbox/mapbox-gl-native/branch/master/graph/badge.svg)](https://codecov.io/gh/mapbox/mapbox-gl-native)

A C++ library that powers customizable vector maps in native applications on multiple platforms by taking stylesheets that conform to the [Mapbox Style Specification](https://docs.mapbox.com/mapbox-gl-js/style-spec/), applying them to vector tiles that conform to the [Mapbox Vector Tile Specification](https://github.com/mapbox/vector-tile-spec/), and rendering them using OpenGL or Metal.

To embed interactive maps into a native application using a platform-specific language, install the Mapbox Maps SDK:

* [Mapbox Maps SDK for Android](https://github.com/mapbox/mapbox-gl-native-android/) (Java, Kotlin)
* [Mapbox Maps SDK for iOS](https://github.com/mapbox/mapbox-gl-native-ios/blob/master/platform/ios/) (Objective-C, Swift, Interface Builder)
* [Mapbox Maps SDK for macOS](https://github.com/mapbox/mapbox-gl-native-ios/tree/master/platform/macos/) (Objective-C, Swift, Interface Builder, AppleScript)

[Mapbox GL JS](https://github.com/mapbox/mapbox-gl-js) is the WebGL-based counterpart to Mapbox GL Native that is designed for use on the Web.

## [Developing](DEVELOPING.md)

We use [CMake](https://cmake.org/cmake/help/latest/) to build Mapbox GL Native
for various platforms, including Linux, Android, iOS, macOS and Windows. The
following command, executed from the root of this repository tree, will build
Mapbox GL Native targeting your host architecture given that you have all the
dependencies installed and run the example app.

```
$ git submodule update --init --recursive
$ cmake . -B build
$ cmake --build build
$ MAPBOX_ACCESS_TOKEN=my_access_token_here ./build/platform/glfw/mbgl-glfw
```

## License

Mapbox GL Native is licensed under the [2-Clause BSD license](LICENSE.md). The licenses of its dependencies are tracked via [FOSSA](https://app.fossa.io/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fmapbox%2Fmapbox-gl-native):

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fmapbox%2Fmapbox-gl-native.svg?type=large)](https://app.fossa.io/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fmapbox%2Fmapbox-gl-native)



## Env

1. 安装qt
<http://mirrors.sjtug.sjtu.edu.cn/qt/archive/qt/5.12/5.12.12/qt-opensource-windows-x86-5.12.12.exe>
配置
Qt5Concurrent_DIR to D:\Qt\5.14\msvc2017_64\lib\cmake\Qt5Concurrent
Qt5Core_DIR to D:\Qt\5.14\msvc2017_64\lib\cmake\Qt5Core
Qt5Gui_DIR to D:\Qt\5.14\msvc2017_64\lib\cmake\Qt5Gui
Qt5Test_DIR to D:\Qt\5.14\msvc2017_64\lib\cmake\Qt5Test
Qt5Widgets_DIR to D:\Qt\5.14\msvc2017_64\lib\cmake\Qt5Widgets
Qt5OpenGL_DIR to D:\Qt\5.14\msvc2017_64\lib\cmake\Qt5OpenGL

2. CmakeList.txt修改
   1. 用QT option(MBGL_WITH_QT "Build Mapbox GL Qt bindings" ON)
   2. 命令行 error D8021: 无效的数值参数“/Wno-deprecated”
<https://blog.csdn.net/kh1445291129/article/details/39553929>
改成QT的博客
<https://blog.csdn.net/qq_38415161/article/details/117197582>

当前结论：
windows直接编译不来mapbox qt也不可以 MinG网友说可以