cmake_minimum_required(VERSION 3.0)

# For clang
set (CMAKE_CXX_FLAGS "-std=c++11 -stdlib=libstdc++")

# For gcc
# set (CMAKE_CXX_FLAGS "-std=c++11")

# For gcc, static binary
# set (CMAKE_CXX_FLAGS "-std=c++11 -g -static")

project (lab1)
set (lab1-src lab1.cpp program_options.cpp tac_node.cpp tic_node.cpp complex_bipartite_graph.cpp file_importer.cpp mwmcm.cpp)
add_executable (lab1 ${lab1-src})

find_package (Boost COMPONENTS program_options filesystem system REQUIRED)
include_directories (${Boost_INCLUDE_DIR})
target_link_libraries (lab1 ${Boost_LIBRARIES})