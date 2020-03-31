# C-TCP-Socket-with-Protobuf
Showcasing how to use Google Protobuf with C++ POSIX TCP socket, including how to write a make file <br>
Exmaple code thanks to https://stackoverflow.com/questions/9496101/protocol-buffer-over-socket-in-c

# File structure
.
├── CMakeLists.txt
├── msg
│   └── message.proto
└── src
    ├── CMakeLists.txt
    ├── server.cpp
    └── client.cpp
        
# Build
This compiles the entire folder and generates executables in the bin folder.

	mkdir build
	cd build
	cmake ..
	make all

## Build Protobuf separately
	
	cd msg
	protoc --cpp_out=. message.proto

## Compile each executable

	c++ server.cc message.pb.cc `pkg-config --cflags --libs protobuf` -o server
	c++ client.cc message.pb.cc `pkg-config --cflags --libs protobuf` -o client

# Run
	./server
	./client

Client will repeatedly send a message to server. The content of the message will be printed in the terminal.


