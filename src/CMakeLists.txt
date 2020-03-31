include_directories(${CMAKE_CURRENT_BINARY_DIR})

# Server use pthread to accept several client
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")

add_executable(client client.cpp)
add_executable(server server.cpp)

target_link_libraries(client msg ${PROTOBUF_LIBRARY})
target_link_libraries(server msg ${PROTOBUF_LIBRARY})