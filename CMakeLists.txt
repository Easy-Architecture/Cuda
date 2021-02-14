cmake_minimum_required(VERSION 3.17)
project(Cuda)
set(CMAKE_CXX_STANDARD 14)

include_directories(gloabl.h)

add_subdirectory( server )
add_subdirectory( threadPool  )
add_subdirectory( protocol )
add_subdirectory( workQueue )
add_subdirectory( sqlPaser )
# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)
add_executable(Cuda ${DIR_SRCS})
target_link_libraries(Cuda EpollServer ThreadPool Protocol WorkQueue SQLPaser)