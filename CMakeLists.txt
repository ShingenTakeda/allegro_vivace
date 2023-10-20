cmake_minimum_required(VERSION 3.15)
project(allegro_vivace)

set(CMAKE_CXX_STANDARD 17)

find_package(unofficial-allegro5 CONFIG REQUIRED)

include_directories(${PROJECT_NAME} ${PROJECT_SOURCE_DIR}/basics/)
include_directories(${PROJECT_NAME} ${PROJECT_SOURCE_DIR}/vivace/)
file(GLOB_RECURSE B_SRC "${PROJECT_SOURCE_DIR}/basics/*.cpp" "${PROJECT_SOURCE_DIR}/basics/*.hpp")

add_executable(basics ${B_SRC})
target_link_libraries(basics PRIVATE unofficial-allegro5::allegro unofficial-allegro5::allegro_ttf unofficial-allegro5::allegro_image unofficial-allegro5::allegro_primitives unofficial-allegro5::allegro_font unofficial-allegro5::allegro_main)

include_directories(${PROJECT_NAME} ${PROJECT_SOURCE_DIR}/basics/)
file(GLOB_RECURSE VIVACE_SRC "${PROJECT_SOURCE_DIR}/vivace/*.cpp" "${PROJECT_SOURCE_DIR}/vivace/*.hpp")

add_executable(${PROJECT_NAME} ${VIVACE_SRC})
target_link_libraries(${PROJECT_NAME} PRIVATE unofficial-allegro5::allegro unofficial-allegro5::allegro_ttf unofficial-allegro5::allegro_image unofficial-allegro5::allegro_primitives unofficial-allegro5::allegro_font unofficial-allegro5::allegro_main)
