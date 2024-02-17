#top

cmake_minimum_required(VERSION 3.10)


project(Tutorial VERSION 1.0)


set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

configure_file(TutorialConfig.h.in TutorialConfig.h)


add_subdirectory(MathFunctions)

#list(APPEND EXTRA_INCLUDES "${PROJECT_SOURCE_DIR}/MathFunctions")


add_executable(Tutorial tutorial.cxx)

#add_library(tutorial_compiler_flags INTERFACE)
#target_compile_features(tutorial_compiler_flags INTERFACE cxx_std_11)
#target_link_libraries(Tutorial PUBLIC tutorial_compiler_flags)


target_link_libraries(Tutorial PUBLIC MathFunctions)

 

 
target_include_directories(Tutorial PUBLIC
                           "${PROJECT_BINARY_DIR}"
                          )

 
