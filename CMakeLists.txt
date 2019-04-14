# requires minimum cmake version
cmake_minimum_required(VERSION 2.8.9)

# produce the cmake var PROJECT_NAME
project(tutorial_yarp-rpc)

# mandatory use of these packages
find_package(YARP 3.0 REQUIRED)
find_package(ICUBcontrib REQUIRED)

# extend the current search path used by cmake to load helpers
list(APPEND CMAKE_MODULE_PATH ${ICUBCONTRIB_MODULE_PATH})

# helpers defining certain macros
include(ICUBcontribHelpers)

# specify to install in $ICUBcontrib_DIR/bin
icubcontrib_set_default_prefix()

# building client
add_executable(tutorial_yarp-rpc-client ${CMAKE_SOURCE_DIR}/src/rpc-client.cpp)
target_link_libraries(tutorial_yarp-rpc-client ${YARP_LIBRARIES})
install(TARGETS tutorial_yarp-rpc-client DESTINATION bin)


# building server
add_executable(tutorial_yarp-rpc-server ${CMAKE_SOURCE_DIR/}src/rpc-server.cpp)
target_link_libraries(tutorial_yarp-rpc-server ${YARP_LIBRARIES})
install(TARGETS tutorial_yarp-rpc-server DESTINATION bin)

