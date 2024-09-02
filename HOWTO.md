# FOSS-2024-1-final

## How to build GIMP?
- 시간 관계상 여러 환경에서 테스트 해볼 수가 없어 다음 환경에서만 테스트를 진행하였습니다.
- Ubuntu 22.04 LTS (with WSL2 in Windows 11)

### 0. Getting Started
```
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get dist-upgrade -y
sudo apt-get autoremove -y
```

### 1. Installing dependencies
- 설치해야 하는 dependency들이 많고, 용량이 1GB를 넘어갈 것입니다.
- 가급적 원활한 인터넷 환경과 넉넉한 저장 공간을 확보한 후 진행해 주세요.
- \ 는 가독성과 쉬운 복붙을 위해 삽입하였으니 신경쓰지 않으셔도 됩니다.
```
sudo apt install -y git build-essential meson ninja-build pkg-config \
python3-dev python3-gi python3-cairo python3-venv \
libglib2.0-dev libgtk2.0-dev libgtk-3-dev libexiv2-dev \
libgexiv2-dev libgirepository1.0-dev gir1.2-gexiv2-0.10 libmypaint-dev \
mypaint-brushes librsvg2-dev glib-networking libpango1.0-dev libcairo2-dev \
libgdk-pixbuf2.0-dev liblcms2-dev libjpeg-dev libtiff5-dev libexif-dev \
libexiv2-dev libgexiv2-dev libpoppler-glib-dev libpoppler-private-dev \
libopenexr-dev libraw-dev libjson-glib-dev iso-codes gettext ghostscript graphviz \
gobject-introspection asciidoc libheif-dev libwebp-dev libxpm-dev libxmu-dev \
libgirepository1.0-dev libappstream-glib-dev libbz2-dev libmypaint-dev libgegl-dev
```
### 2. Cloning Repositories
- GIMP를 빌드하기 위해서는 BABL, GEGL을 먼저 빌드해야 합니다.
```
git clone https://github.com/GNOME/babl.git
git clone https://github.com/GNOME/gegl.git
git clone --recursive https://github.com/GNOME/gimp.git
```
- GIMP는 submodule을 받아주지 않으면 빌드할 때 에러가 발생합니다. 
- 만약 위의 `--recursive` 옵션을 까먹으신 경우,
  `git submodule update --init --recursive`을 통해 submodule을 직접 update해 주세요.

- gimp의 submodule update 과정이 종종 느리게 진행되는 경우가 있습니다.
  
  마지막에 checkout이 제대로 되지 않을 경우 적용이 안된 것이니
  gimp를 처음부터 다시 받아주거나, submodule update를 다시 진행해주시면 됩니다.

### 3. Building and Installing
- 모든 repository는 meson을 통해 build합니다.
- clone한 디렉토리 내부로 들어가면 'meson.build'가 들어 있을 것이며, meson은 이 파일을 통해 빌드를 하게 됩니다.
- 이후 바이너리를 컴파일하고 시스템에 설치하는 것은 meson으로 진행해도 되고, ninja로 진행해도 됩니다.
- 용량이 큰 경우 대체적으로 ninja가 더 빠르게 빌드됩니다. (babl, gegl은 큰 차이가 없으나 gimp는 속도에 차이가 있습니다.)
```
cd {repo_name}
meson setup _build --prefix=/usr/local

#1. meson으로 compile, install 진행
meson compile -C _build
sudo meson install -C _build 

#2. ninja로 compile, install 진행
ninja -C _build
sudo ninja -C _build install

```

### 4. Execute
- install을 통해 (대체적으로) symbolic link를 자동으로 생성해주어,
- 별도의 절차 없이 `gimp-2.99`를 입력하는 것으로 실행이 됩니다. 

### 5. Setting to Korean
- 4번까지 아무 문제 없이 왔다면, 영문판이 설치되어 있을 것입니다.
- 처음 GIMP를 실행하면 뜨는 창에 preferences 항목이 있습니다. 거기에서 언어를 한국어로 바꿔줍니다.
- 아마 폰트가 설치되어 있다면 괜찮으나, 그렇지 않은 경우에는 폰트를 `sudo apt install fonts-nanum`과 같이 설치해줍시다.