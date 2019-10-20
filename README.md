# nrf52-baseproject
This is a CMake project that configure everything needed to build applications for the NRF52 MCU. It configures the toolchain (arm-none-eabi) and the NRF52 SDK.

The CMake files are taken from https://github.com/Polidea/cmake-nRF5x

I tested this project (compile only) with the following versions:

  * gcc-arm-none-eabi-8-2019-q3-update (from https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads)
  * nRF5_SDK_15.3.0_59ac345 (from https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK)
  
**WARNING** as I don't have any NRF52-based dev board, I cannot test that the software built with this project actually works...

## How to use it

  * Download and unzip arm-none-eabi and NRF52 SDK
  * Clone this repo
  * Call CMake with the following command line argument
  
      - -DARM_NONE_EABI_TOOLCHAIN_PATH=[Path to the toolchain] 
      - -DNRF5_SDK_PATH=[Path to the SDK]
      - -DNRFJPROG=[Path to NRFJProg]
      
```
$ mkdir build
$ cd build
$ cmake -DCMAKE_BUILD_TYPE=Debug -DARM_NONE_EABI_TOOLCHAIN_PATH=... -DNRF5_SDK_PATH=... -DNRFJPROG=... ../
```

  * Make
```
$ make -j
```  