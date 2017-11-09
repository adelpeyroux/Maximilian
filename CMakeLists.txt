cmake_minimum_required(VERSION 3.2.0)

IF(NOT CMAKE_BUILD_TYPE)
  SET(CMAKE_BUILD_TYPE "Release" CACHE STRING "CMAKE_BUILD_TYPE: Choose the type of build, options are: None(CMAKE_CXX_FLAGS or CMAKE_C_FLAGS used) Debug Release RelWithDebInfo MinSizeRel." FORCE)
ENDIF(NOT CMAKE_BUILD_TYPE)


SET(TARGET "maximillian")

SET(SRC
  main.cpp
  RtAudio.cpp
  player.cpp
  maximilian.cpp)

ADD_DEFINITIONS(-Wall -D__LINUX_ALSA__)


ADD_EXECUTABLE(${TARGET} ${SRC})
TARGET_LINK_LIBRARIES(${TARGET}  -lasound -lpthread)
