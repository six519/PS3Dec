# mbedTLS
if (NOT TARGET MbedTLS::Crypto)
    find_package(MbedTLS REQUIRED)
endif()

# OpenMP
find_package(OpenMP REQUIRED)

add_executable(ps3dec PS3Dec.c)

set_target_properties(ps3dec PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/${CMAKE_BUILD_TYPE}"
)

target_link_libraries(ps3dec PRIVATE
    MbedTLS::Crypto
    OpenMP::OpenMP_C
)
