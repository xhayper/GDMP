cmake_minimum_required(VERSION 3.12)
project(GDMP)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_C_STANDARD 11)

set(PROJECT_NAME_CLIENT ${PROJECT_NAME}_client)
set(PROJECT_NAME_SERVER ${PROJECT_NAME}_server)

add_subdirectory(external/cocos-headers)
add_subdirectory(external/enet)
add_subdirectory(external/fmt)

include_directories(external/enet/include)

add_subdirectory(server)
add_subdirectory(client)