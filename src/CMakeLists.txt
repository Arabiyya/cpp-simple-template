add_executable(${EXECUTABLE_NAME}
    main.cpp
)

target_include_directories(${EXECUTABLE_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
)

if(CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
    target_compile_definitions(${EXECUTABLE_NAME} PRIVATE COMPILER_ID="GCC")
elseif(CMAKE_CXX_COMPILER_ID STREQUAL "Clang")
    target_compile_definitions(${EXECUTABLE_NAME} PRIVATE COMPILER_ID="Clang")
elseif(CMAKE_CXX_COMPILER_ID STREQUAL "MSVC")
    target_compile_definitions(${EXECUTABLE_NAME} PRIVATE COMPILER_ID="MSVC")
else()
    target_compile_definitions(${EXECUTABLE_NAME} PRIVATE COMPILER_ID="Unknown")
endif()

# --- Link Dependencies ---
# target_link_libraries(${EXECUTABLE_NAME} PRIVATE fmt::fmt)
