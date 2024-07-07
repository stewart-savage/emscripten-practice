cmake_minimum_required(VERSION 3.28)
project(emscripten-practice)
set(CMAKE_CXX_STANDARD 26)

set(SRC main.cpp
)
# Handy way to not need to prefix all src files with the src/ directory
list(TRANSFORM SRC PREPEND "src/")

# Headers
set(INCLUDE ${PROJECT_SOURCE_DIR}/include)

# Generate executable, include headers
add_executable(emscripten-practice ${SRC})
target_include_directories(emscripten-practice PRIVATE ${INCLUDE})

# Sets the output path of the generated .js/.wasm files
set_target_properties(emscripten-practice PROPERTIES RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_CURRENT_SOURCE_DIR}/public)
