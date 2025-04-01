cmake_minimum_required(VERSION 3.1)

project(RISCV-Simulator)

# 设置默认构建类型（仅在未指定时生效）
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif()


set(CMAKE_CXX_STANDARD 11)
# set(CMAKE_CXX_FLAGS "-O2 -Wall")

include_directories(${CMAKE_SOURCE_DIR}/include)

add_executable(
    Simulator 
    src/MainCPU.cpp 
    src/MemoryManager.cpp 
    src/Simulator.cpp 
    src/BranchPredictor.cpp 
    src/Cache.cpp
)

add_executable(
    CacheSim 
    src/MainCache.cpp 
    src/MemoryManager.cpp 
    src/Cache.cpp
)

add_executable(
    CacheOptimized
    src/MainCacheOptimization.cpp
    src/MemoryManager.cpp
    src/Cache.cpp
)

add_executable(ToDirenoTrace src/ToDirenoTrace.cpp)