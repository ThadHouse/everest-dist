# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

include_directories(../include)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D__STDC_FORMAT_MACROS /FI../include/CommonInclude.h")

add_library(quiccrypto STATIC quic_provider.c)

target_compile_options(quiccrypto PRIVATE ${QUIC_C_FLAGS})
target_compile_options(quiccrypto PRIVATE "-D__STDC_FORMAT_MACROS /FI../include/CommonInclude.h")

add_dependencies(quiccrypto mitls)
