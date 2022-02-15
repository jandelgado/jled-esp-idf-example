cmake_minimum_required(VERSION 3.1.6)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)

project(jled-esp-idf-example)

idf_build_set_property(COMPILE_OPTIONS "-DLED_PIN=2" APPEND)

