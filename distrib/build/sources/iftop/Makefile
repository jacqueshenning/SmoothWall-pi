# SmoothWall Build system.
#
# (c) SmoothWall Ltd 2005
#
# This code is distributed under the terms of the GPL v2.

include ../Makefile.conf

PACKAGE = iftop
VERSION = 0.17

BASE_URL = http://www.ex-parrot.com/~pdw/iftop/download/

PRE_CONFIGURE = LIBS=-ltinfo

ifeq ($(mARCH), arm64)
ReConfigure = yes
endif

include ../Makefile.rules
