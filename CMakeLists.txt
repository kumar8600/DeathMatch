cmake_minimum_required(VERSION 3.1)
project(DeathMatch VERSION 0.1.0)

aux_source_directory(src SRC_LIST)
add_executable(DeathMatchGame ${SRC_LIST})

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${DeathMatch_SOURCE_DIR}/cmake")

## dependencies
find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})
target_link_libraries(DeathMatchGame ${SDL2_LIBRARIES})

if(WIN32)
  include(CopyDlls)
endif()
