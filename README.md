# neon-fictx5-qt
neon-fictx5-qt



This repo holds rebuilt packages to fix plasma-desktop crash [issue](https://bugs.kde.org/show_bug.cgi?id=485494).

Download the packages in the [deb](./deb) directory and install these packages 

```
sudo dpkg -i *.deb
```



You may also need to uninstall fcitx4 packages as it also crashes plasma-desktop.

``` 
sudo apt-get purge \
 fcitx \
 fcitx-bin \
 fcitx-data \
 fcitx-config-common \
 fcitx-frontend-all \
 fcitx-frontend-gtk3 \
 fcitx-imlist \
 fcitx-module-kimpanel \
 fcitx-module-quickphrase-editor5  \
 fcitx-module-x11 \
 fcitx-ui-light \
 fcitx-config-gtk \
 fcitx-frontend-gtk2 \
 fcitx-frontend-qt5 \
 fcitx-frontend-qt6 \
 fcitx-module-dbus \
 fcitx-module-lua \
 fcitx-modules \
 fcitx-ui-classic \
 fcitx-frontend-gtk2 \
 libfcitx-config4 \
 libfcitx-core0 \
 libfcitx-gclient1 \
 libfcitx-qt5-1 \
 libfcitx-qt5-data \
 libfcitx-utils0
```



Install fcitx5

```
sudo apt-get install fcitx5-chinese-addons-bin \
fcitx5-chinese-addons-data \
fcitx5-chinese-addons \
fcitx5-config-qt \
fcitx5-data \
fcitx5-frontend-gtk2 \
fcitx5-frontend-gtk3 \
fcitx5-frontend-gtk4 \
fcitx5-frontend-qt5 \
fcitx5-frontend-qt6 \
fcitx5-module-chttrans \
fcitx5-module-cloudpinyin \
fcitx5-module-fullwidth \
fcitx5-module-lua-common \
fcitx5-module-lua \
fcitx5-module-pinyinhelper \
fcitx5-module-punctuation \
fcitx5-modules \
fcitx5-pinyin-gui \
fcitx5-pinyin \
fcitx5-table \
fcitx5-theme-breeze \
fcitx5 \
kde-config-fcitx5 \
libfcitx5-qt-data \
libfcitx5-qt1 \
libfcitx5-qt6-1 \
libfcitx5config6 \
libfcitx5core7 \
libfcitx5gclient2 \
libfcitx5utils2
```

Switch to fcitx5 for plasma-desktop x11

```
im-config -n fcitx5
```

Prevent apt upgrade from overriding these self-built packages before neon officially rebuilds these packages.

```
sudo apt-mark hold fcitx5-frontend-qt5 fcitx5-frontend-qt6 libfcitx5-qt1 libfcitx5-qt6-1

## unhold packages when neon officially fixes the crash issue in the future new version.
sudo apt-mark unhold fcitx5-frontend-qt5 fcitx5-frontend-qt6 libfcitx5-qt1 libfcitx5-qt6-1
```

