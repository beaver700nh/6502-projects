cmake_minimum_required(VERSION 3.13)

set(PROJECT_NAME ror)

set(CMAKE_SYSTEM_NAME Generic)
set(CMAKE_CROSSCOMPILING 1)

set(CMAKE_ASM_COMPILER cl65)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY bin)

set(COMPILE_OPTIONS --cpu 65C02 -t none)
set(LINK_OPTIONS -C ${CMAKE_CURRENT_SOURCE_DIR}/memory.cfg)

project(${PROJECT_NAME} ASM)

add_executable(
  ${PROJECT_NAME}
  src/main.s
)

target_compile_options(
  ${PROJECT_NAME}
  PUBLIC
  ${COMPILE_OPTIONS}
)

target_link_options(
  ${PROJECT_NAME}
  PUBLIC
  ${LINK_OPTIONS}
)

set(CMAKE_VERBOSE_MAKEFILE 1)
