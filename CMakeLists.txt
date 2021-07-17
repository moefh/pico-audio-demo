cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(pico_audio_demo_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()

add_executable(pico_audio_demo
  main.c
  audio.c
)

target_link_libraries(pico_audio_demo
  pico_stdlib
  hardware_dma
  hardware_pwm
)

pico_enable_stdio_usb(pico_audio_demo 1)
pico_add_extra_outputs(pico_audio_demo)
