find_package(CompPhy PATHS CMAKE_PREFIX_PATH $ENV{HOME}/.local/cmake)

#add_executable(pippo main.c) # You may add other sources: add_executable(main main.c foo.c bar.c)
#                             # Do not list header files (no need to list them)

file(GLOB_RECURSE SRCS_FILES "${CMAKE_CURRENT_SOURCE_DIR}/*.c")
add_executable(pippo ${SRCS_FILES})

target_compile_options(pippo PRIVATE -Wall -O3 -march=native -ffast-math)
target_include_directories(pippo PUBLIC ${COMPPHY_INCLUDE_DIR})
target_link_libraries(pippo compphy-lib)
