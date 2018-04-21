# Script generated with Bloom
pkgdesc="ROS - eband_local_planner implements a plugin to the base_local_planner. It implements the Elastic Band method on the SE2 manifold."
url='http://ros.org/wiki/eband_local_planner'

pkgname='ros-kinetic-eband-local-planner'
pkgver='0.3.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-base-local-planner'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-control-toolbox'
'ros-kinetic-costmap-2d'
'ros-kinetic-geometry-msgs'
'ros-kinetic-nav-core'
'ros-kinetic-nav-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-tf-conversions'
)

depends=('ros-kinetic-base-local-planner'
'ros-kinetic-control-toolbox'
'ros-kinetic-costmap-2d'
'ros-kinetic-geometry-msgs'
'ros-kinetic-nav-core'
'ros-kinetic-nav-msgs'
'ros-kinetic-pluginlib'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-tf-conversions'
)

conflicts=()
replaces=()

_dir=eband_local_planner
source=()
md5sums=()

prepare() {
    cp -R $startdir/eband_local_planner $srcdir/eband_local_planner
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

