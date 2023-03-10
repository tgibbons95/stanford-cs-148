cmake_minimum_required(VERSION 3.16)

# Set project name
project(TGraphicsLib)

# Gather all cpp files
file(GLOB_RECURSE SOURCES "*.cpp" "*h")

# Build static library from sources
add_library(${PROJECT_NAME} STATIC ${SOURCES})

# Add Options
enable_code_coverage(${PROJECT_NAME})

# Include header files
target_include_directories(${PROJECT_NAME} PUBLIC "${TGraphics_SOURCE_DIR}/include")
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})

# Use C++20 features
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)

# Link libraries

# Output destination for library
install(TARGETS ${PROJECT_NAME} DESTINATION lib)