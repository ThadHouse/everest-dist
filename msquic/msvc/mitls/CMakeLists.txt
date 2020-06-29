# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

set(SOURCES
    AEADProvider.c
    Alert.c
    buffer_bytes.c
    Cert.c
    CipherSuite.c
    CommonDH.c
    Connection.c
    Content.c
    Crypto_Plain.c
    Extensions.c
    FFI.c
    Flags.c
    Format.c
    HandshakeLog.c
    HandshakeMessages.c
    Hashing.c
    kremlinit.c
    LowParse.c
    Mem.c
    mitlsffi.c
    Negotiation.c
    Nonce.c
    Old_Handshake.c
    Parse.c
    Parsers.c
    PMS.c
    PSK.c
    QUIC.c
    Random.c
    Range.c
    Record.c
    StatefulLHAE.c
    StreamAE.c
    Ticket.c
    TLS.c
    TLSConstants.c
    TLSError.c
    TLSInfo.c
    Mitls_Kremlib.c
)

include_directories(../include)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -D__STDC_FORMAT_MACROS /FI../include/CommonInclude.h")

add_library(mitls STATIC ${SOURCES})

target_compile_options(mitls PRIVATE ${QUIC_C_FLAGS})

add_dependencies(mitls evercrypt)
