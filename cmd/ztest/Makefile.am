include $(top_srcdir)/config/Rules.am

# Get rid of compiler warning for unchecked truncating snprintfs on gcc 7.1.1
AM_CFLAGS += $(NO_FORMAT_TRUNCATION)

# Includes kernel code, generate warnings for large stack frames
AM_CFLAGS += $(FRAME_LARGER_THAN)

# Unconditionally enable ASSERTs
AM_CPPFLAGS += -DDEBUG -UNDEBUG

DEFAULT_INCLUDES += \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/lib/libspl/include

sbin_PROGRAMS = ztest

ztest_SOURCES = \
	ztest.c

ztest_LDADD = \
	$(top_builddir)/lib/libnvpair/libnvpair.la \
	$(top_builddir)/lib/libzfs/libzfs.la \
	$(top_builddir)/lib/libzpool/libzpool.la

ztest_LDADD += -lm
ztest_LDFLAGS = -pthread
