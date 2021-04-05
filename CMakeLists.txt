cmake_minimum_required(VERSION 3.0.0)
project(demo VERSION 0.1.0)


#cmake的demo，用于解释如何使用CMakeLists.txt构建工程
add_subdirectory(demo_cmake)

#Eigen库使用的demo，用于展示进行矩阵运算
add_subdirectory(demo_eigen)
