cmake_minimum_required(VERSION 3.16)
project(TGraphics)

enable_testing()

add_subdirectory("cmake")
add_subdirectory("external_src")

add_subdirectory("src")
add_subdirectory("test")

install(DIRECTORY "include/"
        DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}")