cmake_minimum_required(VERSION 3.15)
project(fromScratch C CXX ASM)

set(NRF_TARGET "nrf52")

# optional, won't be used if passing toolchain on command line (see below)
if (NOT DEFINED ARM_NONE_EABI_TOOLCHAIN_PATH)
  set(ARM_NONE_EABI_TOOLCHAIN_PATH "/usr/local/bin")
endif ()

set(ARM_NONE_EABI_TOOLCHAIN_PATH "/home/jf/nrf52/gcc-arm-none-eabi-8-2019-q3-update")
set(NRF5_SDK_PATH "/home/jf/nrf52/nRF5_SDK_15.3.0_59ac345")
set(NRFJPROG "${CMAKE_SOURCE_DIR}/toolchains/nRF5/nrfjprog/nrfjprog")

include("cmake-nRF5x/CMake_nRF5x.cmake")
add_subdirectory(src)
