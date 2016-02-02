project(try_openslide)
cmake_minimum_required(VERSION 3.0)

# OpenSlide required
LIST(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}")
find_package(OpenSlide REQUIRED)

mark_as_advanced(OPENSLIDE_INCLUDE_DIR OPENSLIDE_LIBRARY)

set(OPENSLIDE_SRCS vtkOpenSlideReader.cxx)

include_directories(${OPENSLIDE_INCLUDE_DIRS})
add_executable(openslide_test "read-region.c")
target_link_libraries(openslide_test ${OPENSLIDE_LIBRARY})
