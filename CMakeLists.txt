cmake_minimum_required(VERSION 3.0)

project(c3dfile)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)

add_library(c3dfile STATIC src/c3dfile.cc src/c3dutils.cc)
target_include_directories(c3dfile PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src)

# Disable tests (for now)
# subdirs(tests)

add_executable(c3dexport src/c3dexport.cc)
target_link_libraries(c3dexport c3dfile)

add_executable(c3ddebug tests/debug.cc)
target_link_libraries(c3ddebug c3dfile)
