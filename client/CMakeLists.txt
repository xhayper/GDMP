project(${PROJECT_NAME_CLIENT})

set(MEGAHACK_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/../external/Mega-Hack-Extensions)
set(COCOS_HEADERS_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/../external/cocos-headers)
set(GDH_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/../external/gd.h)

include_directories(${COCOS_HEADERS_FOLDER}/cocos2dx/include)

include_directories(${GDH_FOLDER}/include)

include_directories(${MEGAHACK_FOLDER}/include)
include_directories(${MEGAHACK_FOLDER}/extensions1)

file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp src/*.hpp src/*.c src/*.h)

add_executable(${PROJECT_NAME} ${SOURCE_FILES})

target_link_libraries(${PROJECT_NAME} enet)
target_link_libraries(${PROJECT_NAME} fmt)
target_link_libraries(${PROJECT_NAME} ${MEGAHACK_FOLDER}/bin/hackpro.lib)