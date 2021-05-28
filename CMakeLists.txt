cmake_minimum_required(VERSION 3.12)

# Include the subsidiary .cmake file to get the SDK
include(pico_sdk_import.cmake)

project(mabos VERSION 0.0.0)

add_executable(mabos mabos.c)

# Pull in our pico_stdlib which aggregates commonly used features
target_link_libraries(mabos pico_stdlib)

# Initalise the SDK
pico_sdk_init()

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(mabos)

# enable usb output, disable uart output
pico_enable_stdio_usb(mabos 1)
pico_enable_stdio_uart(mabos 0)

# Enable extra outputs (SWD?)
pico_add_extra_outputs(mabos)