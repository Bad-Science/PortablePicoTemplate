# (Modified) Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

# Set C/C++ Versions
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
# You may need to change this!
set(PICO_SDK_PATH "/usr/share/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

# Declare Project
project(my_project C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1
add_executable(my_project my_project.c)

# Set Project Name and Version
pico_set_program_name(my_project "My Project")
pico_set_program_version(my_project "0.1")

# Pull in Project and Library Dependencies
# At a minimum you want your project, and the pico_stdlib
# Add additional libraries as needed
target_link_libraries(my_project pico_stdlib)

# Enable USB and/or Serial Output
pico_enable_stdio_usb(my_project 1)
pico_enable_stdio_uart(my_project 0)

# Create map/bin/hex files etc.
pico_add_extra_outputs(my_project)
