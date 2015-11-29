# Building Suricata from source

see https://redmine.openinfosecfoundation.org/projects/suricata/wiki/Installation_from_GIT

### Dependencies

```
sudo apt-get -y install \
libpcre3 \
libpcre3-dbg \
libpcre3-dev \
build-essential \
autoconf \
automake \
libtool \
libpcap-dev \
libnet1-dev \
libyaml-0-2 \
libyaml-dev \
pkg-config \
zlib1g \
zlib1g-dev \
libcap-ng-dev \
libcap-ng0 \
make \
libmagic-dev \
```


### get the source
```
git clone git://phalanx.openinfosecfoundation.org/oisf.git
```

```
cd oisf
git clone https://github.com/OISF/libhtp.git -b 0.5.x
```
### configure, make install

```
./autogen.sh
```

```
./configure
```

```
make
```

```
sudo make install
```

```
sudo ldconfig
```