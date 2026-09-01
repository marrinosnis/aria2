add_library(wslay STATIC)

# add_subdirectory(includes)

target_compile_options(wslay PRIVATE
    -Wall
)

message(WARNING "The source dir is ${CMAKE_CURRENT_SOURCE_DIR}")
message(WARNING "The build dir is ${CMAKE_CURRENT_BUILD_DIR}")

target_include_directories(wslay PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/includes
    ${CMAKE_CURRENT_BUILD_DIR}/includes
)

set_target_properties(wslay PROPERTIES
    VERSION 1.0
    SOVERSION 1
)

target_sources(wslay 
    PRIVATE
        wslay_frame.c 
        wslay_event.c
        wslay_queue.c
        wslay_net.c

        wslay/wslay.h
        wslay/wslayver.h

    PUBLIC:
        FILE_SET HEADERS
        BASE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}
        FILES
            wslay_frame.h
            wslay_event.h
	        wslay_queue.h
            wslay_net.h
            wslay_macro.h
)