# SmoothWall Build system.
#
# (c) SmoothWall Ltd 2005
#
# This code is distributed under the terms of the GPL v2.

include ../Makefile.conf

PACKAGE = bash
VERSION = 4.3.30
BASE_URL = https://ftp.gnu.org/gnu/bash

PATCH_FILE1 = bash-4.3.30-upstream_fixes-3.patch
PATCH_URL1 = http://www.linuxfromscratch.org/patches/downloads/$(PACKAGE)/$(PATCH_FILE1)

ifeq ($(BUILD_PHASE), Stage_3)
BUILD = --build=$(SWE_TGT)

CONFIG_OPTS += --prefix=${TOOLS_DIR} --without-bash-malloc

INSTALL = yes
install: compile
	@make -C $(DIR) DESTDIR=$(PKG_ROOT) install
	@(cd $(PKG_ROOT)$(PKG_DIR)/bin; ln -s bash sh);
endif

ifeq ($(BUILD_PHASE), Final)
CONFIG_OPTS += --bindir=/bin $(BUILD) \
		--docdir=/usr/share/doc/bash-4.3.30 \
		--with-installed-readline
#		--without-bash-malloc \

INSTALL = yes

install: compile
	@mkdir -p $(PKG_ROOT)
	@make -C $(DIR) DESTDIR=$(PKG_ROOT) install
	@(cd $(PKG_ROOT)/bin; ln -s bash sh);
endif

include ../Makefile.rules
