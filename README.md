# How to customize Qt locale on Debian 10

```
$ apt install wget unzip python2
$ apt-get build-dep libqt5core5a
$ apt-get source libqt5core5a
$ wget https://unicode.org/Public/cldr/31.0.1/core.zip
$ unzip core.zip
$ cd qtbase-opensource-src-5.11.3+dfsg1
$ util/local_database/cldr2qlocalexml.py ../common/main > qlocale.xml
$ vi qlocale.xml
$ util/local_database/qlocalexml2cpp.py qlocale.xml .
$ dpkg-buildpackage -b -us -uc
$ sudo dpkg -i ../libqt5core5a_5.11.3+dfsg1-1+deb10u3_amd64.deb
```
