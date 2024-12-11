cmake_minimum_required(VERSION 3.5)
project(oatpp_demo)

set(CMAKE_CXX_STANDARD 20)

set(SOURCE_FILES main.cpp handler.h)

# 查找 oatpp 依赖
find_package(oatpp REQUIRED)

message(STATUS "oatpp_DIR: ${oatpp_DIR}")
message(STATUS "oatpp_INCLUDE_DIRS: ${oatpp_INCLUDE_DIRS}")
message(STATUS "oatpp_LIBRARIES: ${oatpp_LIBRARIES}")
message(STATUS "oatpp_VERSION: ${oatpp_VERSION}")

include_directories(${oatpp_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} ${SOURCE_FILES})

# 将目标文件与库文件进行链接
target_link_libraries(${PROJECT_NAME} oatpp::oatpp)
