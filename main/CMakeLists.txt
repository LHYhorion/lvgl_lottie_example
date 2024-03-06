idf_component_register(
    SRCS
        "image_display.c"
    INCLUDE_DIRS
        ""
    REQUIRES
        rlottie)

message ("######" ${COMPONENT_LIB})
target_compile_options(${COMPONENT_LIB} INTERFACE  -Wno-error=unused-value)
target_compile_options(${COMPONENT_LIB} PRIVATE -w)

spiffs_create_partition_image(storage ../spiffs FLASH_IN_PROJECT)
