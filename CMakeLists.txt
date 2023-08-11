cmake_minimum_required(VERSION 3.24)
set(CMAKE_MODULE_PATH ${EAO_CMAKE_MODULE_PATH} ${CMAKE_MODULE_PATH})

set(PROJECT_NAME "outcome")

project(${PROJECT_NAME} VERSION 0.0.1
  DESCRIPTION "${PROJECT_NAME}")

set(CMAKE_POLICY_DEFAULT_CMP0135 NEW)
set(CMAKE_POLICY_DEFAULT_CMP0048 NEW)
set(CMAKE_POLICY_DEFAULT_CMP0077 NEW)

add_library(outcome 
  include/Outcome/outcome_093f364aa6832c39d54d95da8fd0d7ca16fa4a08_experimental.hpp
)

set_property(TARGET outcome PROPERTY CXX_STANDARD 23)
target_compile_features(outcome INTERFACE cxx_std_23)

target_include_directories(
  outcome
  PUBLIC
  $<BUILD_INTERFACE:${${PROJECT_NAME}_SOURCE_DIR}/include>
)
