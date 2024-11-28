#
# CMakeLists.txt
#
# Copyright (c) 2024 Mateusz Stadnik <matgla@live.com>
#
# Distributed under the terms of the MIT License.
#

cmake_minimum_required(VERSION 3.28)

project (piosim C CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED)

set(CMAKE_OSX_ARCHITECTURES "x86_64")

if(CMAKE_HOST_WIN32)
  set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)
  add_link_options("-static")
endif()

if (MSVC)
  set(CMAKE_CXX_FLAGS "/W4 /WX")
  set(CMAKE_CXX_FLAGS_RELEASE "/O2")
  set(CMAKE_CXX_FLAGS_DEBUG "/Od")
else ()
  set(CMAKE_CXX_FLAGS "-Wall -Wextra -Werror")
  set(CMAKE_CXX_FLAGS_RELEASE "-O3")
  set(CMAKE_CXX_FLAGS_DEBUG "-Og -g")
endif ()

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_subdirectory(source)