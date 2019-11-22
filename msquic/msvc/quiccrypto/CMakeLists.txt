# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

include_directories(../include)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${QUIC_C_FLAGS} -D__STDC_FORMAT_MACROS /FI../include/CommonInclude.h")

add_library(quiccrypto STATIC quic_provider.c)

add_dependencies(quiccrypto mitls)
