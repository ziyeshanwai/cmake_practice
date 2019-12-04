cmake_minimum_required(VERSION 3.0)
# INCLUDE_DIRECTORIES([AFTER|BEFORE] [SYSTEM] dir1 dir2 ...) 
# 这条指令可以用来向工程添加多个特定的头文件搜索路径，路径之间用空格分割，如果路径
# 中包含了空格，可以使用双引号将它括起来，默认的行为是追加到当前的头文件搜索路径的
# 后面，你可以通过两种方式来进行控制搜索路径添加的方式：
# １，CMAKE_INCLUDE_DIRECTORIES_BEFORE，通过SET这个cmake变量为on，可以
# 将添加的头文件搜索路径放在已有路径的前面。
# ２，通过AFTER或者BEFORE参数，也可以控制是追加还是置前。

# LINK_DIRECTORIES(directory1 directory2 ...)
# 这个指令非常简单，添加非标准的共享库搜索路径，比如，在工程内部同时存在共享库和可
# 执行二进制，在编译时就需要指定一下这些共享库的路径。这个例子中我们没有用到这个指
# 令。
# TARGET_LINK_LIBRARIES(target library1 <debug | optimized> library2 ...) 这个指令可以用来为target添加需要链接的共享库，本例中是一个可执行文件，但是同样可以用于为自己编写的共享库添加共享库链接。

# include_directories(${CMAKE_SOURCE_DIR}/inc)
# link_directories(${CMAKE_SOURCE_DIR}/lib)
# 
# add_executable(foo ${FOO_SRCS})
#target_link_libraries(foo bar) # libbar.so is found in ${CMAKE_SOURCE_DIR}/lib

include_directories(E:/camke_practice/t3/lib)  # 主要使用反斜杠
# find_library(hellolib "hello.lib" E:/camke_practice/t3/build/bin NO_DEFAULT_PATH)  # 没有找到库的话helllib就是NO_DEFAULT_PATH
# message(STATUS "path is "${hellolib})
# link_directories(${hellolib})


link_directories(E:/camke_practice/t3/build/bin/MinSizeRel)  # 先添加link目录 再添加可执行文件 最后添加链接库文件
add_executable(main main.c)
# target_link_directories(main E:/camke_practice/t3/build/lib/MinSizeRel)
target_link_libraries(main hello.lib)