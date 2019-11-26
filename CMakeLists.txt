cmake_minimum_required(VERSION 2.6)
project(unifuzzer)

set(CMAKE_CXX_FLAGS "-fsanitize=fuzzer")
set(CMAKE_C_FLAGS "-fsanitize=fuzzer")

add_subdirectory(${PROJECT_SOURCE_DIR}/uniFuzzer/elfLoader)

include_directories(
    ${PROJECT_SOURCE_DIR}/uniFuzzer
    ${PROJECT_SOURCE_DIR}/uniFuzzer/elfLoader
)

add_executable(uf
    ${PROJECT_SOURCE_DIR}/callback/demo-callback.c
    ${PROJECT_SOURCE_DIR}/uniFuzzer/uniFuzzer.c
    ${PROJECT_SOURCE_DIR}/uniFuzzer/uniFuzzer.c
    ${PROJECT_SOURCE_DIR}/uniFuzzer/utils.c
    ${PROJECT_SOURCE_DIR}/uniFuzzer/utils.h
)

target_link_libraries(uf elfLoader -fsanitize=fuzzer -lunicorn -pthread)