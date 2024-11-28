#
# CMakeLists.txt
#
# Copyright (c) 2024 Mateusz Stadnik <matgla@live.com>
#
# Distributed under the terms of the MIT License.
#

add_library(piosim SHARED)

target_sources(piosim
  PUBLIC
    opcode.hpp
    pio_renode_glue.hpp
    pio_registers.hpp
    pio_statemachine.hpp
    pio.hpp
    fifo.hpp
  PRIVATE 
    pio_renode_glue.cpp
    pio_statemachine.cpp
    pio.cpp
    fifo.cpp
)

target_include_directories(piosim 
  PUBLIC 
    ${PROJECT_SOURCE_DIR}
)