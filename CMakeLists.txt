#
# CMakeLists.txt
# Copyright (C) 2021 Marius Greuel
#

cmake_minimum_required(VERSION 3.12)
project(libusb)

add_compile_definitions(_CRT_SECURE_NO_WARNINGS=1)
add_compile_definitions(LOG_APPNAME="avrdude")
add_compile_definitions(STRSAFE_NO_DEPRECATE)

add_library(libusb STATIC
    src/descriptors.c
    src/error.c
    src/registry.c
    src/usb.c
    src/windows.cpp
    )

target_include_directories(libusb
    PUBLIC
    include
    )

if(MSVC)
    target_compile_options(libusb PRIVATE /wd4996) # warning C4996: 'xxx': was declared deprecated
    target_compile_options(libusb PRIVATE /wd5105) # warning C5105: macro expansion producing 'xxx' has undefined behavior
endif()
