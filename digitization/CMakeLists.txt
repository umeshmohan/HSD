cmake_minimum_required(VERSION 2.8)
project( HSD )
find_package( OpenCV REQUIRED )
find_package( Qt5Core REQUIRED )
find_package( Qt5Gui REQUIRED )
find_package( Qt5Widgets REQUIRED )
find_package( Qt5Test REQUIRED )
find_package( Qt5Concurrent REQUIRED )
find_package( Qt5OpenGL REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
add_library( BlobParam BlobParam.cpp BlobParam.hpp common.hpp)
add_library( AutoTrack AutoTrack.cpp AutoTrack.hpp BlobParam.hpp common.hpp)
add_executable( HSD main.cpp BlobParam.hpp AutoTrack.hpp )
target_link_libraries( HSD ${OpenCV_LIBS} BlobParam AutoTrack )
