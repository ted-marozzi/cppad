cmake_minimum_required(VERSION 3.0.0)
project(cppad VERSION 0.1.0)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

include(CTest)
enable_testing()

# Main executable
add_executable(${PROJECT_NAME} main.cpp)

# Local directories list here
add_subdirectory(math)

# Include the above list in this call
target_include_directories(${PROJECT_NAME} PUBLIC math)

# Link the above list here
target_link_directories(${PROJECT_NAME} PUBLIC math)

# Link the libs here
target_link_libraries(${PROJECT_NAME} math)
