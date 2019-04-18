cmake_minimum_required(VERSION 3.0)
project (gwavi)

set(INC_DIRS
	${PROJECT_SOURCE_DIR}/inc
)

set(SOURCES
    src/gwavi.c
    src/avi-utils.c
    src/fileio.c
)
set(HEADERS
    inc/gwavi.h
    src/gwavi_private.h
    src/avi-utils.h
    src/fileio.h
)

include_directories(${INC_DIRS})
link_directories(${LINK_DIRS})

add_library(gwavi STATIC ${SOURCES} ${HEADERS})