INCLUDES = -I../include -I../ctaocrypt/include -I../include/openssl

lib_LTLIBRARIES = libcyassl.la
libcyassl_la_SOURCES = \
    cyassl_int.c cyassl_io.c keys.c ssl.c tls.c  \
    ../ctaocrypt/src/asn.c ../ctaocrypt/src/coding.c ../ctaocrypt/src/des3.c \
    ../ctaocrypt/src/hmac.c ../ctaocrypt/src/md5.c ../ctaocrypt/src/md4.c  \
    ../ctaocrypt/src/random.c ../ctaocrypt/src/rsa.c ../ctaocrypt/src/sha.c \
    ../ctaocrypt/src/aes.c ../ctaocrypt/src/sha256.c ../ctaocrypt/src/dh.c \
    ../ctaocrypt/src/dsa.c ../ctaocrypt/src/arc4.c ../ctaocrypt/src/rabbit.c \
    ../ctaocrypt/src/pwdbased.c
libcyassl_la_LDFLAGS = -no-undefined -version-info 0:0:0
EXTRA_DIST = ../include/*.h ../include/openssl/*.h ../include/*.rc

if BUILD_AESNI
libcyassl_la_SOURCES += ../ctaocrypt/src/aes_asm.s
endif

if BUILD_RIPEMD
libcyassl_la_SOURCES += ../ctaocrypt/src/ripemd.c
endif

if BUILD_SHA512
libcyassl_la_SOURCES += ../ctaocrypt/src/sha512.c
endif

if BUILD_SNIFFER
libcyassl_la_SOURCES += sniffer.c
endif

if BUILD_HC128
libcyassl_la_SOURCES += ../ctaocrypt/src/hc128.c
endif

if BUILD_FASTMATH
libcyassl_la_SOURCES += ../ctaocrypt/src/tfm.c
else
libcyassl_la_SOURCES += ../ctaocrypt/src/integer.c
endif

if BUILD_ECC
libcyassl_la_SOURCES += ../ctaocrypt/src/ecc.c
endif
