cmake_minimum_required(VERSION 3.15)
PROJECT(HELLOLIB)  # 解决方案名称
# ADD_SUBDIRECTORY(source_dir [binary_dir] [EXCLUDE_FROM_ALL])
ADD_SUBDIRECTORY(lib kbin)  # 这个指令用于向当前工程添加存放源文件的子目录，并可以指定中间二进制和目标二进制存放的位置