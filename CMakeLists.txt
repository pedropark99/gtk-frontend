cmake_minimum_required(VERSION 3.5)
project(gtktest CXX)


find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK REQUIRED gtk+-3.0>=3.24.3)
pkg_check_modules(GTKMM REQUIRED gtkmm-3.0>=3.24)


add_executable(gtktest src/main.cpp)
target_link_libraries(gtktest PRIVATE ${GTKMM_LIBRARIES})

# Add other flags to the compiler
target_include_directories(gtktest PRIVATE ${GTKMM_INCLUDE_DIRS})
target_link_directories(gtktest PRIVATE ${GTKMM_LIBRARY_DIRS})

