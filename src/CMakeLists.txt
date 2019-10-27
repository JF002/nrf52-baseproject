cmake_minimum_required(VERSION 3.12)

project(application-example C CXX ASM)

# define some variables just for this example to determine file locations
set(NRF_PROJECT_NAME application-example)
set(NRF_BOARD pca10040)
#set(NRF_SOFTDEVICE s132)

nRF5x_toolchainSetup()
nRF5x_setup()

#nRF5x_addAppScheduler()
#nRF5x_addAppFIFO()
#nRF5x_addAppTimer()
#nRF5x_addAppUART()
nRF5x_addAppButton()
nRF5x_addBSP(FALSE FALSE FALSE)
#nRF5x_addBLEGATT()
#
#nRF5x_addBLEService(ble_lbs)

add_definitions(-DCONFIG_GPIO_AS_PINRESET)


include_directories(.)
list(APPEND SOURCE_FILES main.cpp)

nRF5x_addExecutable(application-example "${SOURCE_FILES}")