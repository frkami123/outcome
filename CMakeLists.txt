cmake_minimum_required(VERSION 3.24)
set(CMAKE_MODULE_PATH ${EAO_CMAKE_MODULE_PATH} ${CMAKE_MODULE_PATH})

set(PROJECT_NAME "outcome")

project(${PROJECT_NAME} LANGUAGES CXX VERSION 0.0.1
  DESCRIPTION "${PROJECT_NAME}")

set(CMAKE_POLICY_DEFAULT_CMP0135 NEW)
set(CMAKE_POLICY_DEFAULT_CMP0048 NEW)
set(CMAKE_POLICY_DEFAULT_CMP0077 NEW)

add_library(outcome INTERFACE
  include/Outcome/outcome_018620768577911c9b259275a5957525d55ad09a_experimental.hpp
)

set_property(TARGET outcome PROPERTY CXX_STANDARD 23)
target_compile_features(outcome INTERFACE cxx_std_23)

target_include_directories(
  outcome
  INTERFACE
  $<BUILD_INTERFACE:${${PROJECT_NAME}_SOURCE_DIR}/include>
)
