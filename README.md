# qBittorrent для OpenWrt (mipsel)
Пакет qBittorrent и его зависимости для OpenWrt

## Обозначения папок
Расположение пакетов в конфигураторе такое:

Пакет `libqt5` (libqt5-core, libqt5-network, libqt5-sql, libqt5-xml) версия 5.15.5, по пути `Libraries --> Qt5`

Пакет `libqtorrent` версия из последних исходников https://github.com/arvidn/libtorrent/commits/RC_1_2, по пути `Libraries --> libqtorrent`

Пакет `qbittorrent` версия из последних исходников https://github.com/qbittorrent/qBittorrent/commits/master, по пути `Network --> BitTorrent --> qbittorrent`

## Как пользоваться
После устаноки qBittorrent. Перейдите в настройки веб интерфейса:
```
Адрес веб интерфейса: http://192.168.1.1:8080
Имя пользователя: openwrt
Пароль: openwrt
```

## Папка настроек
По умолчанию папка настроек qBittorrent создается по пути `/etc/qBittorrent`. Вы можете изменить путь создания папки, для этого откройте файл `/etc/init.d/qbittorrent` и измените строку `ARGS="--profile=/etc"`

## Протестировано
Протестировано на `Xiaomi Mi WiFi Router 3G v1` и `OpenWrt SNAPSHOT`

========================================================================
# qBittorrent for OpenWrt (mipsel)
OpenWrt package Makefiles for qBittorrent and its dependencies

## Folder designations
Package location in the configuration is:

Package `libqt5` (libqt5-core, libqt5-network, libqt5-sql, libqt5-xml) version 5.15.5, path `Libraries --> Qt5`

Package `libqtorrent` version of the last source https://github.com/arvidn/libtorrent/commits/RC_1_2, path `Libraries --> libqtorrent`

Package `qbittorrent` version of the last source https://github.com/qbittorrent/qBittorrent/commits/master, path `Network --> BitTorrent --> qbittorrent`

## How to open
After installing qBittorrent. Go to Web UI Settings 
```
Adress Web UI: http://192.168.1.1:8080
Username: openwrt
Password: openwrt
```

## Folder settings
By default, the qBittorrent settings folder is created on path `/etc/qBittorrent`. You can change the folder path, To do this, open the file `/etc/init.d/qbittorrent` and change the line `ARGS="--profile=/etc"`

## Tested
Tested on `Xiaomi Mi WiFi Router 3G v1` and `OpenWrt SNAPSHOT`
