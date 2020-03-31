# Official Documentation:
# https://cmake.org/cmake/help/v3.9/module/FindProtobuf.html

# Locate and configure the Google Protocol Buffers library
include(FindProtobuf)
find_package(Protobuf REQUIRED)
include_directories(${PROTOBUF_INCLUDE_DIR})

# commands to process .proto files to C++
protobuf_generate_cpp(PROTO_SRC PROTO_HEADER message.proto)

# For Python
#protobuf_generate_python(PROTO_PY message.proto)

add_library(msg ${PROTO_HEADER} ${PROTO_SRC})