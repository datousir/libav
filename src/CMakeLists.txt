#  * Copyright (c) 2013-2015, datousir <datousir at gmail dot com>
#  * All rights reserved.

if(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
    add_definitions(-DHAVE_EPOLL)
elseif(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
    add_definitions(-D_WIN32)
elseif(${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
    add_definitions(-DHAVE_KQUEUE)
elseif(${CMAKE_SYSTEM_NAME} MATCHES "FreeBSD")
    add_definitions(-DHAVE_KQUEUE)
endif()

SET(SRC_LIST 
    adlist.h
    adlist.c
    ae.h
    ae.c
    anet.h
    anet.c
    zmalloc.h
    zmalloc.c
    )

ADD_LIBRARY(av ${SRC_LIST})
SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)
