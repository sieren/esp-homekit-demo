# The following five lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
set(CMAKE_CXX_STANDARD 14)
list(APPEND compile_definitions "ARDUINO=202000")


# Ignore warning in Azure IoT Library in esp32 Arduino
# pending PR: https://github.com/VSChina/ESP32_AzureIoT_Arduino/pull/15
list(APPEND compile_options "-Wno-maybe-uninitialized")

# set(COMPONENT_DIRS "components/common/"
#  "components/common/homekit"
#	 "components/common/esp32)"
# )

list(APPEND compile_definitions "ESP_IDF")
set(EXTRA_COMPONENT_DIRS
"components/common/"
"components/esp-32/http-parser"
)


project(homekittest)
