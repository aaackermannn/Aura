cmake_minimum_required(VERSION 3.16)
project(DiscordClone)

set(CMAKE_CXX_STANDARD 17)

find_package(PkgConfig REQUIRED)
pkg_check_modules(PQXX REQUIRED libpqxx)
pkg_check_modules(HTTPLIB REQUIRED cpp-httplib)
pkg_check_modules(JSON REQUIRED nlohmann_json)
pkg_check_modules(JWT REQUIRED jwt-cpp)
pkg_check_modules(UWS REQUIRED uwebsockets)

add_executable(DiscordClone main.cpp)

target_include_directories(DiscordClone PRIVATE ${PQXX_INCLUDE_DIRS} ${HTTPLIB_INCLUDE_DIRS} ${JSON_INCLUDE_DIRS} ${JWT_INCLUDE_DIRS} ${UWS_INCLUDE_DIRS})
target_link_libraries(DiscordClone PRIVATE ${PQXX_LIBRARIES} ${HTTPLIB_LIBRARIES} ${JSON_LIBRARIES} ${JWT_LIBRARIES} ${UWS_LIBRARIES})
