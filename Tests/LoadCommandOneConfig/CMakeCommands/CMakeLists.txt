cmake_minimum_required (VERSION 2.6)
PROJECT(CMAKE_LOADED_COMMANDS)

IF (MUDSLIDE_TYPE MATCHES MUCHO)
  ADD_DEFINITIONS(-DMUCHO_MUDSLIDE)
ENDIF (MUDSLIDE_TYPE MATCHES MUCHO)

IF(WATCOM)
  SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS}")
ENDIF(WATCOM)
INCLUDE_DIRECTORIES(${CMAKE_ROOT}/include ${CMAKE_ROOT}/Source)

ADD_LIBRARY(cmCMAKE_TEST_COMMAND MODULE cmTestCommand.c)

IF(WATCOM)
  TARGET_LINK_LIBRARIES(cmCMAKE_TEST_COMMAND clbsdll.lib)
ENDIF(WATCOM)
