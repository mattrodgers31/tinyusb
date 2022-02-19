cmake_minimum_required(VERSION 3.21)
project(target-tinyusb LANGUAGES C CXX ASM)

# Suppress warnings if required
add_compile_options(
    -Wno-conversion
    -Wno-sign-conversion
)

add_library(tinyusb OBJECT
    ${PROJECT_SOURCE_DIR}/src/tusb.c
    ${PROJECT_SOURCE_DIR}/src/class/cdc/cdc_device.c
    ${PROJECT_SOURCE_DIR}/src/common/tusb_fifo.c
    ${PROJECT_SOURCE_DIR}/src/device/usbd_control.c
    ${PROJECT_SOURCE_DIR}/src/device/usbd.c
    ${PROJECT_SOURCE_DIR}/src/portable/st/synopsys/dcd_synopsys.c
)

target_include_directories(tinyusb PUBLIC
    ${PROJECT_SOURCE_DIR}/src
)