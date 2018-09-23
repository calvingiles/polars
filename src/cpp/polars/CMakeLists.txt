# add dependencies
add_subdirectory(${DEPENDENCIES_DIR}/date)
add_subdirectory(${DEPENDENCIES_DIR}/armadillo-code)

# Set source directory
set(CPP_SOURCE_DIR "src/cpp/polars")

# Build sources list
set(
        CPP_SOURCES
        "${CPP_SOURCE_DIR}/numc.h"
        "${CPP_SOURCE_DIR}/numc.cpp"
        "${CPP_SOURCE_DIR}/TimeSeries.cpp"
        "${CPP_SOURCE_DIR}/TimeSeries.h"
        "${CPP_SOURCE_DIR}/TimeSeriesMask.cpp"
        "${CPP_SOURCE_DIR}/TimeSeriesMask.h"
)

add_library(polars_cpp ${CPP_SOURCES})
target_include_directories(polars_cpp PUBLIC ${Polars_SOURCE_DIR}/src/cpp)
target_link_libraries(polars_cpp armadillo date_interface)