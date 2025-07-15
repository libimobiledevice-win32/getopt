cmake_minimum_required(VERSION 3.31)

project(getopt VERSION 1.0 LANGUAGES C)

include(GNUInstallDirs)

if(BUILD_SHARED_LIBS)
    add_definitions(-DEXPORTS_GETOPT)
else()
    add_definitions(-DSTATIC_GETOPT)
endif()

add_library(getopt getopt.c)

set_target_properties(getopt PROPERTIES PUBLIC_HEADER getopt.h)

install(TARGETS getopt)
