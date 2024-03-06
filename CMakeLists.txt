cmake_minimum_required(VERSION 3.5)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)

add_compile_options(-fdiagnostics-color=always)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(EXTRA_COMPONENT_DIRS
    # "${IDF_PATH}/examples/common_components"
)
list(APPEND EXTRA_COMPONENT_DIRS "${CMAKE_CURRENT_LIST_DIR}/components")
idf_build_set_property(COMPILE_OPTIONS "-fpermissive" APPEND)
idf_build_set_property(COMPILE_OPTIONS "-w" APPEND)

message ("###232232" ${EXTRA_COMPONENT_DIRS})

# The following line can be removed after LVGL update to v8.3.5.
add_compile_options(-Wno-format -Wno-unused-value)

project(image_display)