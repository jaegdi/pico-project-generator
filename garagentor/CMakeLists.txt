# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "C:/Users/dirkj/Documents/Pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(garagentor C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(garagentor garagentor.c )

pico_set_program_name(garagentor "garagentor")
pico_set_program_version(garagentor "0.1")

pico_enable_stdio_uart(garagentor 1)
pico_enable_stdio_usb(garagentor 0)

# Add the standard library to the build
target_link_libraries(garagentor pico_stdlib)

# Add any user requested libraries
target_link_libraries(garagentor
        hardware_pio
        hardware_timer
        hardware_watchdog
        hardware_clocks
        )

pico_add_extra_outputs(garagentor)

