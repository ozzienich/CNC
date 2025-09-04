# compile QT5 silicon


```shell
git clone   https://github.com/qt/qt5.git qt5-git

cd qt5
git checkout v5.15.17-lts-lgpl

./init-repository --module-subset=qtbase,qttools,qtsvg,qtxmlpatterns,qtdeclarative



cd ..
mkdir qt5-build
cd qt5-build

../qt5-git/configure -release -prefix /opt/qt5 -nomake examples -nomake tests QMAKE_APPLE_DEVICE_ARCHS=arm64 -opensource -confirm-license -skip qt3d -skip qtwebengine


make -j$(sysctl -n hw.ncpu)

make install

```
