#工程设置
cmake_minimum_required(VERSION 3.0.0)
project(demo_cmake)
set(CMAKE_BUILD_TYPE Release)
#所包含的头文件在生成动态库和可执行文件时都会用到
include_directories(include)

#动态库设置
add_library(hello SHARED  ${PROJECT_SOURCE_DIR}/src/hello.cpp)

#函数入口设置
set(SRC  ${PROJECT_SOURCE_DIR}/src/useHello.cpp)
add_executable(${PROJECT_SOURCE_DIR} ${SRC})
target_link_libraries(${PROJECT_SOURCE_DIR} hello)


#库和可执行文件的安装
set(CMAKE_INSTALL_PREFIX /usr/local)
install(TARGETS   hello
            DESTINATION  ${CMAKE_INSTALL_PREFIX}/lib)   
install(FILES  ${PROJECT_SOURCE_DIR}/include/hello.h
            DESTINATION ${CMAKE_INSTALL_PREFIX}/include )        
