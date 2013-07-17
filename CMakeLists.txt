PROJECT(pvr.demo)

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

ENABLE_LANGUAGE(CXX)

FIND_PACKAGE(xbmc REQUIRED)
addon_version(pvr.demo PVRDEMO)

FIND_PACKAGE(xbmcplatform REQUIRED)
INCLUDE_DIRECTORIES(${xbmcplatform_INCLUDE_DIRS}
                    ${XBMC_INCLUDE_DIR})

SET(DEPLIBS ${xbmcplatform_LIBRARIES})

SET(SOURCES src/client.cpp
            src/PVRDemoData.cpp)

build_addon(pvr.demo SOURCES DEPLIBS PVRDEMO_VERSION)
install_addon(pvr.demo ${PVRDEMO_VERSION})
