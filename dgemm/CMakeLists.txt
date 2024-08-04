cmake_minimum_required(VERSION 3.10)

project(DGEMM VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 包含头文件目录
include_directories(${PROJECT_SOURCE_DIR}/include)

message(${PROJECT_SOURCE_DIR})
message(${PROJECT_BINARY_DIR})

# 添加可执行文件
add_executable(DGEMM src/main.cpp)

if (CMAKE_SYSTEM_NAME STREQUAL "Darwin")
    # macOS-specific options
    target_compile_options(DGEMM PRIVATE -Wall -Wextra)
elseif (CMAKE_SYSTEM_NAME STREQUAL "Linux")
    # Ubuntu-specific options
    target_compile_options(DGEMM PRIVATE -Wall -Wextra)
endif()

# find_package(SomeLibrary REQUIRED)
# target_link_libraries(MyProject PRIVATE SomeLibrary)