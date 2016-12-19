cmake_minimum_required(VERSION 3.5.1)
project(cmake_project_name)


# add the binary tree to the search path for include files
# so that we will find Config.h
include_directories("${PROJECT_BINARY_DIR}")

# compile and include Logger Library
#include_directories("${PROJECT_SOURCE_DIR}/src/logger")
#add_library(Logger "${PROJECT_SOURCE_DIR}/src/logger/logger.cpp")

# configure a header file to pass some of the CMake settings
# to the source code
configure_file("${PROJECT_SOURCE_DIR}/Config.h.in" "${PROJECT_BINARY_DIR}/Config.h")

add_executable(cmake_project_name "${PROJECT_SOURCE_DIR}/main.cpp")
#target_link_libraries(my_cmake_project Logger)

# install Logger library
#install(TARGETS Logger DESTINATION lib)
#install(FILES "${PROJECT_SOURCE_DIR}/src/logger/logger.h" DESTINATION include)

# install executable file
install(TARGETS cmake_project_name DESTINATION bin)
#install(FILES "${PROJECT_BINARY_DIR}/Config.h" DESTINATION include)

