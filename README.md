# QtWinExtras

The QtWinExtras module has been deprecated by The Qt Company and is no longer part of Qt's official release, this is a fork of the original QtWinExtras module to make it be able to build and use in Qt 6.

A part of the functionality of the QtWinExtras module has been incorporated into other parts of Qt (see also: [QTBUG-89564](https://bugreports.qt.io/browse/QTBUG-89564)), but there are still some other part are not, thus this module can still be helpful.

## Before Using This Module

Please read [Qt 6 porting guide](https://doc.qt.io/qt-6/portingguide.html), especially [Changes to Qt Windows Extras](https://doc.qt.io/qt-6/extras-changes-qt6.html#changes-to-qt-windows-extras) and [Obsolete Members for QtWin](https://doc.qt.io/qt-5/qtwin-obsolete.html). If Qt 6 have the functionality in other module, consider use that instead.

The known missing important functionalities that not provided as a part of Qt 6's official release are:

- `QWinJumpList` [QTBUG-94007](https://bugreports.qt.io/browse/QTBUG-94007)
- `QWinTaskbarButton` [QTBUG-94009](https://bugreports.qt.io/browse/QTBUG-94009)
- `QWinTaskbarProgress` [QTBUG-94008](https://bugreports.qt.io/browse/QTBUG-94008)
- `QWinThumbnailToolBar` No known bug report for this feature in Qt 6

## Usage

To build, simply use CMake (QMake is NOT supported):

```shell
> cmake -Bbuild .
> cmake --build build --config RelWithDebInfo
```

Then you can use CMake to find the module as usual, for example, something like:

```cmake
find_package(Qt6WinExtras REQUIRED)
# ..or..
find_package(Qt6 REQUIRED COMPONENTS Core Gui Widgets WinExtras)
```

To make CMake be able to find Qt6WinExtras module while building **your application**, you need "install" the module to the "correct" location (your `%QTDIR%`), which is likely the thing you don't want to do.

As an alternative solution, you can define the `Qt6WinExtras_DIR` CMake variable, something like:

```shell
> cmake . -Bbuild -DQt6WinExtras_DIR='C:/path/to/your/qtwinextras/build/lib/cmake/Qt6WinExtras'
```

If you choose this approach, to make `windeployqt` working, you might still need to "install" the DLL to the correct location. Simply copy `Qt6WinExtras.dll` to `%QTDIR%/bin` would be fine.

Versions older than `6.7.2` are not tested and I have no plan to test this module on older Qt versions.

You can also enable the `QT_BUILD_EXAMPLES` option to build the existing examples.
