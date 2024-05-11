cmake_minimum_required(VERSION 3.5)

project(GSPUI)

# Set C standard to C99
set(CMAKE_C_STANDARD 99)


message("\nBuilding GSPUI")

set(GSPUI_SRC
    src/GSPUI.c
)

add_library(GSPUI STATIC ${GSPUI_SRC})
target_include_directories(GSPUI PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)


# test executable

add_executable(UiTest ${CMAKE_CURRENT_SOURCE_DIR}/testing/main.c)
target_link_libraries(UiTest PRIVATE GSPUI)
target_include_directories(UiTest PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
