# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# CMAKE
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

cmake_minimum_required( VERSION 3.16 )
message( STATUS "CMAKE_VERSION=${CMAKE_VERSION}" )

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# PROJECT
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Project Name
set( PROJECT_NAME "zChat" )

# Project Version
set( PROJECT_VERSION 0.1 )

# Configure Project
project( ${PROJECT_NAME} VERSION ${PROJECT_VERSION} LANGUAGES C CXX )

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# COMPILER
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# MODULES
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set( PROJECT_HEADERS "${CMAKE_SOURCE_DIR}/src/server/windows/public/main.hpp" )
set( PROJECT_SOURCES "${CMAKE_SOURCE_DIR}/src/server/windows/private/main.cpp" )

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# BUILD
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Add Executable Object
add_executable( server ${PROJECT_HEADERS} ${PROJECT_SOURCES} )

# Configure Executable-Object
set_target_properties( server PROPERTIES
    RUNTIME_OUTPUT_NAME "server_v${PROJECT_VERSION}"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_SOURCE_DIR}/bin" )

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
