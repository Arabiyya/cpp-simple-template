cmake_minimum_required(VERSION 3.20)

project(MyCppProjectTemplate VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(EXECUTABLE_NAME ${PROJECT_NAME})

# --- vcpkg ---
# find_package(fmt CONFIG REQUIRED)

add_subdirectory(src)

# Add other subdirectories like tests later
# enable_testing()
# add_subdirectory(tests)

# --- Installation ---
include(GNUInstallDirs)
install(TARGETS ${EXECUTABLE_NAME}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)
