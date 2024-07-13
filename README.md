# Setup environment to build google/cld3

## Getting started

### Prequiste

OS: Ubuntu 18.04.06 LTS

Source: Protobuf-2.5

Source: cld3

gcc/g++ compiler: 4.9.3 ( <5.0 )


### Download external source

#### Soure code google/Protobuf-2.5.0

[https://github.com/google/protobuf/releases/download/v2.5.0/protobuf-2.5.0.tar.gz](https://github.com/google/protobuf/releases/download/v2.5.0/protobuf-2.5.0.tar.gz)

#### Source code google/cld3

[https://github.com/google/cld3](https://github.com/google/cld3)

### Install gcc/g++ 4.9.3

ignore if your systems installed gcc/g++ version 4.9.3 or lower 5.0

For safety, you should remove '--no-check-certificate' and add https in url

#### download deb package

```bash
wget --no-check-certificate http://launchpadlibrarian.net/247707088/libmpfr4_3.1.4-1_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728424/libasan1_4.9.3-13ubuntu2_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728426/libgcc-4.9-dev_4.9.3-13ubuntu2_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728314/gcc-4.9-base_4.9.3-13ubuntu2_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728399/cpp-4.9_4.9.3-13ubuntu2_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728404/gcc-4.9_4.9.3-13ubuntu2_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728432/libstdc++-4.9-dev_4.9.3-13ubuntu2_amd64.deb &&
wget --no-check-certificate http://launchpadlibrarian.net/253728401/g++-4.9_4.9.3-13ubuntu2_amd64.deb
```

#### Install deb package

Please aware about the order of command

```bash
sudo dpkg -i gcc-4.9-base_4.9.3-13ubuntu2_amd64.deb &&
sudo dpkg -i libmpfr4_3.1.4-1_amd64.deb &&
sudo dpkg -i libasan1_4.9.3-13ubuntu2_amd64.deb &&
sudo dpkg -i libgcc-4.9-dev_4.9.3-13ubuntu2_amd64.deb &&
sudo dpkg -i cpp-4.9_4.9.3-13ubuntu2_amd64.deb &&
sudo dpkg -i gcc-4.9_4.9.3-13ubuntu2_amd64.deb &&
sudo dpkg -i libstdc++-4.9-dev_4.9.3-13ubuntu2_amd64.deb &&
sudo dpkg -i g++-4.9_4.9.3-13ubuntu2_amd64.deb
```


#### Check gcc/g++ in your systems is 4.9 or not

```bash
update-alternatives --query gcc
```

```bash
update-alternatives --query g++
```

#### Set gcc/g++ ver 4.9 to default

ignore if your gcc/g++ version is 4.9

Because gcc/g++ default in Ubuntu 18 is gcc/g++ version 7, so feel free to change command bellow by your gcc/g++ version installed

```bash
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.9 100
```

```bash
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 50
```

```bash
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-4.9 100
```

```bash
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-7 50
```

#### Check gcc/g++ default use version 4.9 after setup

```bash
update-alternatives --query gcc
```

```bash
update-alternatives --query g++
```

### Install protobuf-2.5.0 from source by step following

```bash
wget https://github.com/google/protobuf/releases/download/v2.5.0/protobuf-2.5.0.tar.gz
```

```bash
tar xvf protobuf-2.5.0.tar.gz
```

```bash
cd protobuf-2.5.0
```

```bash
./autogen.sh
```

```bash
./configure --prefix=/usr
```

```bash
make
```

```bash
sudo make install
```

```bash
protoc --version
```


### build google/cld3 to shared library

```bash
cd cld3-master
```

```bash
cmake -S .
```

```bash
make
```

## Build this project

Make sure you setup environment to build google/cld3 successful

do step bellow to build detector

```bash
cmake -S .
```

```bash
make
```
