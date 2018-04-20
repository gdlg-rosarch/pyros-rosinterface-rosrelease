# Script generated with Bloom
pkgdesc="ROS - Dynamic ROS interface for Pyros"


pkgname='ros-kinetic-pyros-interfaces-ros'
pkgver='0.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin-pip>=0.1.17'
'ros-kinetic-catkin>=0.6.18'
'ros-kinetic-message-generation>=0.2.10'
'ros-kinetic-pyros-common>=0.4.2'
'ros-kinetic-pyros-test>=0.0.6'
'ros-kinetic-pyros-utils>=0.1.3'
'ros-kinetic-roslint>=0.10.0'
'ros-kinetic-rospy>=1.11.19'
'ros-kinetic-rostest>=1.11.19'
'ros-kinetic-rostopic>=1.11.19'
'ros-kinetic-rosunit>=1.11.12'
'ros-kinetic-std-msgs>=0.5.9'
)

depends=('ros-kinetic-message-runtime>=0.4.12'
'ros-kinetic-pyros-common>=0.4.2'
'ros-kinetic-pyros-utils>=0.1.3'
'ros-kinetic-rospy>=1.11.19'
'ros-kinetic-std-msgs>=0.5.9'
)

conflicts=()
replaces=()

_dir=pyros_interfaces_ros
source=()
md5sums=()

prepare() {
    cp -R $startdir/pyros_interfaces_ros $srcdir/pyros_interfaces_ros
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

