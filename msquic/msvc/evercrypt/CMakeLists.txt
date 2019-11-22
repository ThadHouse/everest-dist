# Copyright (c) Microsoft Corporation.
# Licensed under the MIT License.

set(SOURCES
    EverCrypt.c
    EverCrypt_AutoConfig2.c
    everCrypt_bcrypt.c
    EverCrypt_Chacha20Poly1305.c
    EverCrypt_Cipher.c
    EverCrypt_Curve25519.c
    EverCrypt_Hash.c
    EverCrypt_HKDF.c
    EverCrypt_HMAC.c
    EverCrypt_Poly1305.c
    EverCrypt_StaticConfig.c
    EverCrypt_Vale.c
    evercrypt_vale_stubs.c
    Hacl_Chacha20.c
    Hacl_Chacha20_Vec32.c
    Hacl_Chacha20_Vec128.c
    Hacl_Chacha20_Vec256.c
    Hacl_Chacha20Poly1305_32.c
    Hacl_Chacha20Poly1305_128.c
    Hacl_Chacha20Poly1305_256.c
    Hacl_Curve25519_51.c
    Hacl_Curve25519_64.c
    Hacl_Ed25519.c
    Hacl_Hash.c
    Hacl_AES.c
    Hacl_Kremlib.c
    Hacl_SHA3.c
    Hacl_Poly1305_32.c
    Hacl_Poly1305_128.c
    Hacl_Poly1305_256.c
    amd64/aesgcm-x86_64-msvc.asm
    amd64/aes-x86_64-msvc.asm
    amd64/cpuid-x86_64-msvc.asm
    amd64/curve25519-x86_64-msvc.asm
    amd64/oldaesgcm-x86_64-msvc.asm
    amd64/poly1305-x86_64-msvc.asm
    amd64/sha256-x86_64-msvc.asm
)

enable_language(ASM_MASM)

include_directories(../include)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${QUIC_C_FLAGS} -D__STDC_FORMAT_MACROS /FI../include/CommonInclude.h")

add_library(evercrypt STATIC ${SOURCES})

add_dependencies(evercrypt kremlib)
