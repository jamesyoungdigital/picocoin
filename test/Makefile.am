if ENABLE_VALGRIND
    TESTS_ENVIRONMENT=$(LIBTOOL) --mode=execute valgrind --leak-check=full \
                        --leak-resolution=high --num-callers=40 \
                        --error-exitcode=1
endif

SUBDIRS		= data

AM_CPPFLAGS	= -DTEST_SRCDIR=\"$(top_srcdir)/test\" \
		  -I$(top_srcdir)/include \
		  -I$(top_srcdir)/external/secp256k1/include

noinst_LIBRARIES= libtest.a

libtest_a_SOURCES= libtest.h libtest.c chisq.c randtest.c

noinst_PROGRAMS	= clist cstr coredefs hex hdkeys hashtab base58 fileio util \
		  crypto keystore keyset bloom mbr misc net sighash \
		  message parr prng script-parse tx block blockfile blkdb script \
		  tx-valid wallet wallet-basics chain-verf hash ctaes aes-util

TESTS		= clist cstr coredefs hex hdkeys hashtab base58 fileio util \
		  crypto keystore keyset bloom mbr misc net sighash \
		  message parr prng script-parse tx block blockfile blkdb script \
		  tx-valid wallet wallet-basics chain-verf hash ctaes aes-util

COMMON_LDADD	= libtest.a $(top_builddir)/lib/libccoin.la \
		  $(top_builddir)/external/secp256k1/libsecp256k1.la \
		  @GMP_LIBS@ @JANSSON_LIBS@ @MATH_LIBS@

base58_LDADD        = $(COMMON_LDADD)
blkdb_LDADD         = $(COMMON_LDADD)
block_LDADD         = $(COMMON_LDADD)
blockfile_LDADD 	= $(COMMON_LDADD)
bloom_LDADD         = $(COMMON_LDADD)
chain_verf_LDADD	= $(COMMON_LDADD)
clist_LDADD         = $(COMMON_LDADD)
cstr_LDADD		    = $(COMMON_LDADD)
coredefs_LDADD		    = $(COMMON_LDADD)
ctaes_LDADD         = $(COMMON_LDADD) $(top_builddir)/lib/libccoinaes.la
aes_util_LDADD		= $(COMMON_LDADD) $(top_builddir)/lib/libccoinaes.la
crypto_LDADD		= $(COMMON_LDADD)
fileio_LDADD		= $(COMMON_LDADD)
hash_LDADD		= $(COMMON_LDADD)
hex_LDADD           = $(COMMON_LDADD)
hashtab_LDADD		= $(COMMON_LDADD)
hdkeys_LDADD		= $(COMMON_LDADD)
keyset_LDADD		= $(COMMON_LDADD)
keystore_LDADD		= $(COMMON_LDADD)
mbr_LDADD		= $(COMMON_LDADD)
message_LDADD		= $(COMMON_LDADD)
misc_LDADD		= $(COMMON_LDADD)
net_LDADD		= $(COMMON_LDADD) $(top_builddir)/lib/libccoinnet.la
parr_LDADD		    = $(COMMON_LDADD)
prng_LDADD		    = $(COMMON_LDADD)
script_LDADD		= $(COMMON_LDADD)
script_parse_LDADD	= $(COMMON_LDADD)
sighash_LDADD		= $(COMMON_LDADD)
tx_LDADD		= $(COMMON_LDADD)
tx_valid_LDADD		= $(COMMON_LDADD)
util_LDADD		    = $(COMMON_LDADD) $(top_builddir)/lib/libccoinnet.la
wallet_LDADD		= $(COMMON_LDADD)
wallet_basics_LDADD	= $(COMMON_LDADD)
