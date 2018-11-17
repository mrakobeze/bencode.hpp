
cmake_minimum_required(VERSION 3.12)
project(bencode)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)


find_package(
        Boost 1.68.0
        REQUIRED)

enable_testing()

add_executable(test_encode test/test_encode.cpp src/bencode.hpp)
add_executable(test_decode test/test_decode.cpp src/bencode.hpp)

target_include_directories(test_encode PUBLIC D:/SDK/mettle/include ${Boost_INCLUDE_DIRS})
target_include_directories(test_decode PUBLIC D:/SDK/mettle/include ${Boost_INCLUDE_DIRS})

add_test(test_encode test_encode)
add_test(test_decode test_decode)
