cmake_minimum_required(VERSION 3.0)
project( gwavi)

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

add_library(gwavi STATIC ${SOURCES} ${HEADERS})


set_target_properties( gwavi
    PROPERTIES
    PUBLIC_HEADER "inc/gwavi.h"
)

install (TARGETS gwavi
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    PUBLIC_HEADER DESTINATION include/gwavi
)


