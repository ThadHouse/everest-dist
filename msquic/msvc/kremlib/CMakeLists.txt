# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

set(SOURCES
    RegionAllocator.c
    c.c
    c_string.c
    fstar_bytes.c
    fstar_char.c
    fstar_date.c
    fstar_dyn.c
    fstar_hyperstack_io.c
    fstar_int16.c
    fstar_int32.c
    fstar_int64.c
    fstar_int8.c
    fstar_io.c
    fstar_string.c
#    fstar_uint128.c
    fstar_uint128_msvc.c
    fstar_uint16.c
    fstar_uint32.c
    fstar_uint64.c
    fstar_uint8.c
    prims.c
#    testlib.c
    FStar_UInt_8_16_32_64.c
)

include_directories(../include)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${QUIC_C_FLAGS} -D__STDC_FORMAT_MACROS /FI../include/CommonInclude.h")

add_library(kremlib STATIC ${SOURCES})
