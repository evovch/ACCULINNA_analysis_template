# =============================================================================

cmake_minimum_required(VERSION 3.5)

# Give your project a name
project(TestAnalysis)

# Switch it on for more verbose make output
# set(CMAKE_VERBOSE_MAKEFILE ON)

# =============================================================================
# External packages

# See: https://root.cern.ch/how/integrate-root-my-project-cmake

# ROOT
list(APPEND CMAKE_PREFIX_PATH $ENV{ROOTSYS})
find_package(ROOT REQUIRED)

# Define useful ROOT functions and macros (e.g. ROOT_GENERATE_DICTIONARY)
include(${ROOT_USE_FILE})

include_directories(/home/evovch/Documents/ACCULINNA_go4_user_library/install/include/)
include_directories(/home/evovch/Documents/ACCULINNA_go4_user_library/install/include/data/)

# =============================================================================

if (CMAKE_COMPILER_IS_GNUCXX)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -Wall -Wextra -Wno-unused-parameter")
    # -std=c++11 -g -Wall -Wextra -Wpedantic
endif()

# =============================================================================

add_subdirectory(testanalysis)
