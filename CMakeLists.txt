project(ExtendedKF)

cmake_minimum_required (VERSION 3.5)

add_definitions(-std=c++11)

set(sources 
	src/main.cpp 
	src/tools.cpp 
	src/FusionEKF.cpp 
	src/kalman_filter.cpp)

include_directories(/usr/local/include)
include_directories(/usr/local/opt/openssl/include)
link_directories(/usr/local/lib)
link_directories(/usr/local/opt/openssl/lib)
link_directories(/usr/local/Cellar/libuv/1*/lib)

add_executable(ExtendedKF ${sources})

target_link_libraries(ExtendedKF z ssl uv uWS)
