cmake_minimum_required(VERSION 3.21)

enable_language(CXX)

set(PAHO_MQTT_C_LIBRARIES ${CMAKE_CURRENT_LIST_DIR}/libs/paho-c/lib/libpaho-mqtt3a-static.a)
set(PAHO_MQTT_C_INCLUDE_DIRS ${CMAKE_CURRENT_LIST_DIR}/libs/paho-c/include)
list(APPEND CMAKE_PREFIX_PATH ${CMAKE_CURRENT_LIST_DIR}/libs/paho-cpp/lib/cmake/PahoMqttCpp)
find_package(PahoMqttCpp REQUIRED)

project(mqtt_test)

add_executable(mqtt_test main.cpp)
target_link_libraries(mqtt_test PRIVATE PahoMqttCpp::paho-mqttpp3-static)