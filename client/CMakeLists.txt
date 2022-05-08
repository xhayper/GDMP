project(${PROJECT_NAME_CLIENT})

set(MEGAHACK_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/../external/Mega-Hack-Extensions)
set(GDH_FOLDER ${CMAKE_CURRENT_SOURCE_DIR}/../external/gd.h)


include_directories(${GDH_FOLDER}/include)
include_directories(${GDH_FOLDER})

include_directories(${MEGAHACK_FOLDER}/include)
include_directories(${MEGAHACK_FOLDER}/extensions1)

file(GLOB_RECURSE SOURCE_FILES CONFIGURE_DEPENDS src/*.cpp src/*.hpp src/*.c src/*.h)

add_library(${PROJECT_NAME} SHARED ${SOURCE_FILES})

target_link_libraries(${PROJECT_NAME} enet fmt cocos2d ${MEGAHACK_FOLDER}/bin/hackpro.lib)