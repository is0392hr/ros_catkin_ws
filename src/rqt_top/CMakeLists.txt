cmake_minimum_required(VERSION 3.0.2)
project(rqt_top)
# Load catkin and all dependencies required for this package
#find_package(catkin REQUIRED COMPONENTS python-psutil)
find_package(catkin REQUIRED)
catkin_package()
catkin_python_setup()

install(FILES plugin.xml
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(PROGRAMS scripts/rqt_top
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
