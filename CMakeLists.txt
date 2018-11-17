
cmake_minimum_required(VERSION 3.12)
project(bencode)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

add_subdirectory(boost-cmake)

enable_testing()

add_executable(test_encode test/test_encode.cpp src/bencode.hpp)
add_executable(test_decode test/test_decode.cpp src/bencode.hpp)

target_include_directories(test_encode PUBLIC D:/SDK/mettle/include)
target_include_directories(test_decode PUBLIC D:/SDK/mettle/include)

#target_link_libraries(bencode Boost::boost stdc++)
target_link_libraries(test_encode Boost::boost)
target_link_libraries(test_decode Boost::boost)

add_test(test_encode test_encode)
add_test(test_decode test_decode)