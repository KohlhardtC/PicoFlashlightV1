# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# initalize pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
#set(PICO_SDK_PATH "/usr/share/pico-sdk")

# Pull in Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(PicoFlashlightV1 C CXX ASM)

set(PICO_CXX_ENABLE_EXCEPTIONS 1)

set(PICO_CXX_ENABLE_RTTI 1)

# Initialise the Pico SDK
pico_sdk_init()

include("PicoLed/PicoLed.cmake")

# Add executable. Default name is the project name, version 0.1

add_executable(PicoFlashlightV1 PicoFlashlightV1.cpp )

pico_set_program_name(PicoFlashlightV1 "PicoFlashlightV1")
pico_set_program_version(PicoFlashlightV1 "0.1")

pico_enable_stdio_uart(PicoFlashlightV1 1)
pico_enable_stdio_usb(PicoFlashlightV1 1)

# Add the standard library to the build
target_link_libraries(PicoFlashlightV1 pico_stdlib PicoLed)

pico_add_extra_outputs(PicoFlashlightV1)

