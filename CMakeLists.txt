# CMakeList.txt: ports 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
cmake_minimum_required (VERSION 3.8)
project (k1ee VERSION 1.0 LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
# 将源代码添加到此项目的可执行文件。
#add_executable (ports "ports.cpp" "ports.h")

# TODO: 如有需要，请添加测试并安装目标。


option(BUILD_K1EE_TESTS "Build Tests" ON)
include(GNUInstallDirs)

add_subdirectory(src)
add_subdirectory(include)
if(BUILD_K1EE_TESTS)
    enable_testing()
    add_subdirectory(test)
endif()