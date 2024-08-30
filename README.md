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
$ cmake -Bbuild .
$ cmake --build build --config RelWithDebInfo
```

Version older than `6.7.2` is not tested and I have no plan to test this module on older Qt version.

You can also enable the `QT_BUILD_EXAMPLES` option to build the existing examples.

To find this module in CMake, use `find_package(Qt6WinExtras REQUIRED)`. You'll need to update `CMAKE_PREFIX_PATH` or install the module to ensure CMake can find it.
