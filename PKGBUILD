# vim:set ts=2 sw=2 et:
# Maintainer boogieeeee <boogiepop AT gmx DOT com>
#
_codename=Omega
_gitname=xbmc
_ff_branch="6.0"

pkgname=kodi-mpp-git
pkgver=r175775.6186114acf
pkgrel=1
arch=('armv7h' 'aarch64')
url="https://kodi.tv"
license=('GPL2')
pkgdesc="Kodi ${_codename} with rockchip MPP based VPU decoding support (${_codename})"
makedepends=(
  'afpfs-ng' 'bluez-libs' 'cmake' 'curl' 'dav1d' 'doxygen' 'git' 'glew'
  'gperf' 'hicolor-icon-theme' 'java-runtime<21' 'fmt' 'libaacs' 'libass'
  'libbluray' 'libcdio' 'libcec' 'libgl' 'mariadb-libs' 'libmicrohttpd'
  'libmodplug' 'libmpeg2' 'libnfs' 'libplist' 'libpulse' 'libva'
  'libva-vdpau-driver' 'libxrandr' 'libxslt' 'lirc' 'lzo' 'mesa' 'nasm'
  'pipewire' 'python-pycryptodomex' 'python-pillow' 'python-pybluez'
  'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'taglib'
  'tinyxml' 'swig' 'upower' 'giflib' 'rapidjson' 'ghostscript' 'meson' 'gtest'
  'graphviz' 'pcre' 'tinyxml2' 'libdisplay-info'
  # cmake/scripts/linux/Install.cmake calls distutils
  # python 3.12 does no longer come with distutils on board
  'python-setuptools'
  # wayland
  'wayland-protocols' 'waylandpp' 'libxkbcommon'
  # gbm
  'libinput'
  'mpp'
)

depends=(
  'bluez-libs' 'curl' 'dav1d' 'desktop-file-utils' 'hicolor-icon-theme' 'fmt'
  'lcms2' 'libass' 'libbluray' 'libcdio' 'libcec' 'libmicrohttpd' 'libnfs'
  'libplist' 'libpulse' 'libva' 'libvdpau' 'libxslt' 'lirc' 'lzo'
  'mariadb-libs' 'mesa' 'libpipewire' 'python-pillow' 'python-pycryptodomex'
  'python-simplejson' 'shairplay' 'smbclient' 'sndio' 'spdlog' 'sqlite'
  'taglib' 'tinyxml' 'libxrandr' 'libxkbcommon' 'waylandpp' 'libinput'
  'pcre' 'tinyxml2' 'libdisplay-info'
  'mpp'
)

optdepends=(
  'afpfs-ng: Apple shares support'
  'bluez: Blutooth support'
  'python-pybluez: Bluetooth support'
  'pulseaudio: PulseAudio support'
  'pipewire: PipeWire support'
  'upower: Display battery level'
)

provides=('kodi' 'kodi-omega' 'kodi-mpp' 'kodi-omega-mpp' 'kodi-dev' 'kodi-omega-dev')
conflicts=('kodi' 'kodi-dev' 'kodi-eventclients' 'kodi-tools-texturepacker')
options=(!distcc !lto strip)

_libdvdcss_version="1.4.3-Next-Nexus-Alpha2-2"
_libdvdnav_version="6.1.1-Next-Nexus-Alpha2-2"
_libdvdread_version="6.1.3-Next-Nexus-Alpha2-2"
_crossguid_version="ca1bf4b810e2d188d04cb6286f957008ee1b7681"
_fstrcmp_version="0.7.D001"
_flatbuffers_version="23.3.3"
_libudfread_version="1.1.2"

_cmake_release_type=Release

# checkout individual binary addons and ffmpeg
source=(
  "git+https://github.com/xbmc/xbmc.git#branch=${_codename}"
  "git+https://github.com/nyanmisaka/ffmpeg-rockchip.git#branch=${_ff_branch}"
  "kodi-libdvdcss-$_libdvdcss_version.tar.gz::https://github.com/xbmc/libdvdcss/archive/$_libdvdcss_version.tar.gz"
  "kodi-libdvdnav-$_libdvdnav_version.tar.gz::https://github.com/xbmc/libdvdnav/archive/$_libdvdnav_version.tar.gz"
  "kodi-libdvdread-$_libdvdread_version.tar.gz::https://github.com/xbmc/libdvdread/archive/$_libdvdread_version.tar.gz"
  "kodi-crossguid-$_crossguid_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/crossguid-$_crossguid_version.tar.gz"
  "kodi-fstrcmp-$_fstrcmp_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/fstrcmp-$_fstrcmp_version.tar.gz"
  "kodi-flatbuffers-$_flatbuffers_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/flatbuffers-$_flatbuffers_version.tar.gz"
  "kodi-libudfread-$_libudfread_version.tar.gz::https://mirrors.kodi.tv/build-deps/sources/libudfread-$_libudfread_version.tar.gz"
  "0001-ffmpeg-buildsys.patch"
  "0002-groovy-wildcard.patch"
  "0003-PR24431.patch"
  "0004-distutils.patch"
)

noextract=(
  "kodi-libdvdcss-$_libdvdcss_version.tar.gz"
  "kodi-libdvdnav-$_libdvdnav_version.tar.gz"
  "kodi-libdvdread-$_libdvdread_version.tar.gz"
  "kodi-ffmpeg-$_ffmpeg_version.tar.gz"
  "kodi-crossguid-$_crossguid_version.tar.gz"
  "kodi-fstrcmp-$_fstrcmp_version.tar.gz"
  "kodi-flatbuffers-$_flatbuffers_version.tar.gz"
  "kodi-libudfread-$_libudfread_version.tar.gz"
)

b2sums=('SKIP' 'SKIP'
        '2f503d3ab767094958f7ec10b4ad11ffd02665deee571c8f3c739bef5fc7e2ff84babc5a3fdee638dc095f896b72fe3ce65e6b688674cb5f7b7b77190992688c'
        'db4d05836d8fbb3637ae50bdbfc0e4b612ee6b3be24addfea94ce772c3bf28d58b63a3f252d6f9f016f72f8cbb841cc1820b091226b136f4c4664385a32da73c'
        'c94feb5a03a12efa5b7767965118d2500a088299ea36f3b82e46d157e45893e6b04503cb50f179ca681bac914457607fab26acfa6e304752b355c407578572d1'
        '0f78a8ab5a420297f666b3b8156d499a9141ec25c049d4d2bb2ba594dc585abe211a149b83c605cce4f5530207231a065d5f3a87a0c969781de8c6381afa2527'
        'a8b68fcb8613f0d30e5ff7b862b37408472162585ca71cdff328e3299ff50476fd265467bbd77b352b22bb88c590969044f74d91c5468475504568fd269fa69e'
        'be5e3c8ea81ce4b6f2e2c1b2f22e1172434c435f096fa7dade060578c506cff0310e3e2ef0627e26ce2be44f740652eb9a8e1b63578c18f430f7925820f04e66'
        '1801d84a0ca38410a78f23e7d44f37e6d53346753c853df2e7380d259ce1ae7f0c712825b95a5753ad0bc6360cfffe1888b9e7bc30da8b84549e0f1198248f61'
        'fbfdab0ec7aaa056c900c5cdd4652a165ea22585923a01ae132ff306f2203d8a18b5472fc56d53706aaaccae1e6e613e886c6ed5400a64a34e333547b732032e'
        '0cfc1f92a7e7bee838a101d0ab1dc51c08fd06289ef812bfada99fce5688bf5238b9a8023ffff24067ca68c2eb1c567596c0da8e19edf746cf5512bdadbff044'
        '3d24d8a9d8ab047a97140f19bbbac6be2afc71ef087d92ed073a2fcc5065b9d583ea02dbd482532bcf5a65683da70b4c6c737715e98f7a81a1315ad61cf66095'
        '67a1265dba5f3f44f62423a13123da8259ae631c81598360f6f7d5ee3f6faaab10baf39864de405c3fe09504b0c6c92cf6dffa587cce9fe35b9c45bf131e7ca7')

pkgver() {
  local _revnum=0
  local _fcommits=0
  local _kcommits=0

  cd "${srcdir}/ffmpeg-rockchip"
  _fcommits="$(git rev-list --count HEAD)"
  
  cd "${srcdir}/${_gitname}"
  _kcommits="$(git rev-list --count HEAD)"

  _revnum=$(($_kcommits + $_fcommits))
  printf "r%s.%s" $_revnum "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p "$srcdir/kodi-build"
  mkdir -p "$srcdir/tmp"

  cd "$_gitname"
  rm -rf system/certs # remove not needed cacert
  patch -p1 -N -i ../0001-ffmpeg-buildsys.patch
  # https://github.com/xbmc/xbmc/commit/d6bc920e056baad7782f47b86cba85d1336bb134
  patch -p1 -N -i ../0002-groovy-wildcard.patch
  patch -p1 -N -i ../0003-PR24431.patch
  patch -p1 -N -i ../0004-distutils.patch
}

build() {
  cd "$srcdir/kodi-build"
  
  # disable https://rfc.archlinux.page/0023-pack-relative-relocs/
  export LDFLAGS=${LDFLAGS/-Wl,-z,pack-relative-relocs}

  _args=(
    -DCMAKE_BUILD_TYPE=$_cmake_release_type
    -DENABLE_DEBUGFISSION=OFF
    -DCMAKE_INSTALL_PREFIX=/usr
    -DCMAKE_INSTALL_LIBDIR=/usr/lib
    -DUSE_LTO=$(nproc)
    -DVERBOSE=ON
    -DENABLE_LDGOLD=ON
    -DENABLE_AIRTUNES=ON
    -DENABLE_AVAHI=ON
    -DENABLE_BLURAY=ON
    -DENABLE_CEC=ON
    -DENABLE_DBUS=ON
    -DENABLE_DVDCSS=ON
    -DENABLE_EGL=ON
    -DENABLE_EVENTCLIENTS=ON
    -DENABLE_MICROHTTPD=ON
    -DENABLE_MYSQLCLIENT=ON
    -DENABLE_NFS=ON
    -DENABLE_OPTICAL=ON
    -DENABLE_SMBCLIENT=ON
    -DENABLE_UDEV=ON
    -DENABLE_UPNP=ON
    -DENABLE_VAAPI=ON
    -DENABLE_VDPAU=ON
    -DENABLE_XSLT=ON
    -DENABLE_LIRCCLIENT=ON
    -DENABLE_INTERNAL_RapidJSON=OFF
    -DENABLE_INTERNAL_FFMPEG=ON
    -DENABLE_INTERNAL_CROSSGUID=ON
    -DENABLE_INTERNAL_FSTRCMP=ON
    -DENABLE_INTERNAL_FLATBUFFERS=ON
    -DENABLE_INTERNAL_UDFREAD=ON
    -Dlibdvdcss_URL="$srcdir/kodi-libdvdcss-$_libdvdcss_version.tar.gz"
    -Dlibdvdnav_URL="$srcdir/kodi-libdvdnav-$_libdvdnav_version.tar.gz"
    -Dlibdvdread_URL="$srcdir/kodi-libdvdread-$_libdvdread_version.tar.gz"
    -DCROSSGUID_URL="$srcdir/kodi-crossguid-$_crossguid_version.tar.gz"
    -DFSTRCMP_URL="$srcdir/kodi-fstrcmp-$_fstrcmp_version.tar.gz"
    -DFLATBUFFERS_URL="$srcdir/kodi-flatbuffers-$_flatbuffers_version.tar.gz"
    -DUDFREAD_URL="$srcdir/kodi-libudfread-$_libudfread_version.tar.gz"
    -DFFMPEG_URL="${srcdir}/ffmpeg-rockchip"
    -DAPP_RENDER_SYSTEM=gles
  )

  # https://github.com/google/flatbuffers/issues/7404
  CXXFLAGS+=' -Wno-error=restrict -g3'

  echo "building kodi"
  cmake "${_args[@]}" ../"$_gitname"
  TMPDIR="$srcdir/tmp" make ${MAKEFLAGS}  
}

package() {
  _components=(
    'kodi'
    'kodi-bin'
    'kodi-eventclients-common'
    'kodi-eventclients-ps3'
    'kodi-eventclients-kodi-send'
    'kodi-tools-texturepacker'
    'kodi-addon-dev'
    'kodi-eventclients-dev'
  )

  echo "Installing Kodi"
  cd kodi-build
  for _cmp in ${_components[@]}; do
  DESTDIR="$pkgdir" /usr/bin/cmake \
    -DCMAKE_INSTALL_COMPONENT="$_cmp" \
     -P cmake_install.cmake
  done
}
