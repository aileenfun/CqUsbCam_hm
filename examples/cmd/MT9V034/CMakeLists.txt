
project(usbCamConsole)

cmake_minimum_required(VERSION 2.8)

#if(CMAKE_COMPILER_IS_GNUCXX)
#    set(CMAKE_CXX_FLAGS "-std=c++11 -O3 -Wall -Wno-unused-result -g ${CMAKE_CXX_FLAGS}")
#    message(STATUS "optional:-std=c++11 -O3 -Wall -g")   
#endif(CMAKE_COMPILER_IS_GNUCXX)
add_compile_options(-std=c++11 -g)

aux_source_directory(. DIR_SRCS)
set(CMAKE_BUILD_TYPE Debug)
link_directories("../../../../CqUsbCam/build")
link_libraries(CqUsbCam)
link_directories("/usr/local/lib")
link_libraries(opencv_core  opencv_highgui usb-1.0 pthread)
#link_libraries(opencv_core  opencv_highgui)
add_executable(usbCamConsole ${DIR_SRCS})
#target_link_libraries (usbCamconsole  cyusb CqUsbCam)


