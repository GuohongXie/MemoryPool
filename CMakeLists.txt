# 指定使用 CMake 的最低版本号
cmake_minimum_required(VERSION 3.0)

# 设置项目名称
project(ryan_network C CXX)

#enable_testing()

# 添加搜索路径
include_directories(
    ${PROJECT_SOURCE_DIR}/src
    )


# 包含这些目录下的.cc文件
# 下面这两个会把目录及其子目录的所有.cc文件都包括
#aux_source_directory(${PROJECT_SOURCE_DIR}/ryan_network/logger SRC_LOGGER)
#aux_source_directory(${PROJECT_SOURCE_DIR}/ryan_network/logger SRC_LOGGER)
#如果想要不包含子目录下的文件，则使用file
file(GLOB SRC_MEMORY_POOL ${PROJECT_SOURCE_DIR}/src/memory_pool.cc)
file(GLOB MAIN_MEMORY_POOL_TEST ${PROJECT_SOURCE_DIR}/test/memory_pool_test.cc)

# 设置编译选项(没用上)
set(CXX_FLAGS
    -g
    -Wall
    -std=c++11
    -O0
    )

set(CMAKE_CXX_FLAGS_DEBUG "-O0 -g -std=c++17 -DDEBUG")
set(CMAKE_CXX_FLAGS_RELEASE "-O2 -std=c++17 -DNDEBUG")

# 找到并链接Google Test库
#find_package(GTest) #REQUIRED
#if(GTest_FOUND)
#  include_directories(${GTEST_INCLUDE_DIRS})
#endif()

# 设置生成动态库的路径，放在根目录的lib文件夹下面
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)

add_executable(memory_pool_test ${MAIN_MEMORY_POOL_TEST} ${SRC_MEMORY_POOL})


# 设置安装的默认路径

# 将目录安装到 include/ryan_network 下（只安装头文件）
#install(DIRECTORY ${PROJECT_SOURCE_DIR}/ryan_network/ DESTINATION build/include/ryan_network FILES_MATCHING PATTERN "*.h")

