project(Ackermann)

set(CMAKE_CXX_STANDARD 11)

add_executable(Ackermann main.cpp)

MATH(EXPR stack_size "16 * 1024 * 1024") # 16 Mb

set(CMAKE_EXE_LINKER_FLAGS "-static")
if(WIN32)
    set(CMAKE_EXE_LINKER_FLAGS "-Wl,--stack,${stack_size}")
endif()