# Copyright (c) 2007 Intel Corporation. All Rights Reserved.
#
# Permission is hereby granted, free of charge, to any person obtaining a
# copy of this software and associated documentation files (the
# "Software"), to deal in the Software without restriction, including
# without limitation the rights to use, copy, modify, merge, publish,
# distribute, sub license, and/or sell copies of the Software, and to
# permit persons to whom the Software is furnished to do so, subject to
# the following conditions:
#
# The above copyright notice and this permission notice (including the
# next paragraph) shall be included in all copies or substantial portions
# of the Software.
# 
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
# OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
# MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NON-INFRINGEMENT.
# IN NO EVENT SHALL PRECISION INSIGHT AND/OR ITS SUPPLIERS BE LIABLE FOR
# ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
# TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
# SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

bin_PROGRAMS = avcenc mpeg2vaenc h264encode jpegenc vp9enc vp8enc hevcencode av1encode
noinst_PROGRAMS = svctenc

AM_CPPFLAGS = \
	-Wall				\
	$(LIBVA_CFLAGS) 		\
	$(NULL)

if USE_SSP
AM_CPPFLAGS += -fstack-protector
endif

h264encode_SOURCES	= h264encode.c
h264encode_CFLAGS	= -I$(top_srcdir)/common -g
h264encode_LDADD	= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread -lm

hevcencode_SOURCES	= hevcencode.c
hevcencode_CFLAGS	= -I$(top_srcdir)/common -g
hevcencode_LDADD	= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread -lm


avcenc_SOURCES		= avcenc.c
avcenc_CFLAGS		= -I$(top_srcdir)/common -g
avcenc_LDADD		= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread

mpeg2vaenc_SOURCES	= mpeg2vaenc.c
mpeg2vaenc_CFLAGS	= -I$(top_srcdir)/common
mpeg2vaenc_LDADD	= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread

jpegenc_SOURCES		= jpegenc.c
jpegenc_CFLAGS		= -I$(top_srcdir)/common -g
jpegenc_LDADD		= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread

svctenc_SOURCES		= svctenc.c
svctenc_CFLAGS		= -I$(top_srcdir)/common -g
svctenc_LDADD		= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread -lm

vp9enc_SOURCES     = vp9enc.c
vp9enc_CFLAGS      = -I$(top_srcdir)/common -g
vp9enc_LDADD       = \
	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread -lm

vp8enc_SOURCES     = vp8enc.c
vp8enc_CFLAGS      = -I$(top_srcdir)/common -g
vp8enc_LDADD       = \
	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread -lm

av1encode_SOURCES	= av1encode.c
av1encode_CFLAGS	= -I$(top_srcdir)/common -g
av1encode_LDADD	= \
       	$(LIBVA_LIBS) \
	$(top_builddir)/common/libva-display.la \
	-lpthread -lm

valgrind:	$(bin_PROGRAMS) $(noinst_PROGRAMS)
	for a in $(bin_PROGRAMS) $(noinst_PROGRAMS); do \
		valgrind --leak-check=full --show-reachable=yes .libs/$$a; \
	done

EXTRA_DIST = 		\
	jpegenc_utils.h \
	$(NULL)
