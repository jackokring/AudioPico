# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/jacko/pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(AudioPico C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(AudioPico AudioPico.c )

pico_set_program_name(AudioPico "AudioPico")
pico_set_program_version(AudioPico "0.1")

pico_enable_stdio_uart(AudioPico 1)
pico_enable_stdio_usb(AudioPico 1)

# Add the standard library to the build
target_link_libraries(AudioPico pico_stdlib)

# Add any user requested libraries
target_link_libraries(AudioPico
        hardware_spi
        hardware_i2c
        hardware_dma
        hardware_pio
        hardware_interp
        hardware_timer
        hardware_watchdog
        hardware_clocks
        )

pico_add_extra_outputs(AudioPico)

