cmake_minimum_required(VERSION 3.5)

# set the project name
project(Protobuf_example)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# set the executable folder
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)

#############################
#Dependencies
#############################

find_package(Protobuf REQUIRED)

#############################
#Build Executable
#############################

add_subdirectory(msg)
add_subdirectory(src)


