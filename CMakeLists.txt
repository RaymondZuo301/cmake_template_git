cmake_minimum_required(VERSION 3.5 FATAL_ERROR)

project(code03)

# 添加自定义cmake文件目录
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

# 使用Utility.cmake
include(Utility)

# 获取当前的GIT_HASH
set(GIT_HASH "unknown")
get_git_hash(GIT_HASH)
message(STATUS "Git hash is ${GIT_HASH}")

# 获取当前的分支
set(GIT_BRANCH "unknown")
get_git_branch(GIT_BRANCH)
message(STATUS "Git branch is ${GIT_BRANCH}")

configure_file(
  ${CMAKE_CURRENT_SOURCE_DIR}/include/git_version.h.in
  ${CMAKE_BINARY_DIR}/generate/git_version.h
  @ONLY
  )
