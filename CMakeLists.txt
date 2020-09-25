cmake_minimum_required(VERSION 3.0.0)
project(MY_CODE VERSION 0.1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include(CTest)
enable_testing()

include_directories(
${PROJECT_SOURCE_DIR}/include
)
add_library(myLib SHARED
src/Test.cpp
)
add_executable(main main.cpp)
target_link_libraries(main myLib)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
