#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"). You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2011, 2013, EveryCity Ltd. All rights reserved.
# Copyright 2016, Adam Stevko, All rights reserved.
# Copyright 2019, Michal Nowak
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		nasm
COMPONENT_VERSION=	2.16.1
HUMAN_VERSION=		2.16.01
COMPONENT_SUMMARY=	The Netwide Assembler
COMPONENT_PROJECT_URL=	https://www.nasm.us/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(HUMAN_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH= sha256:c77745f4802375efeee2ec5c0ad6b7f037ea9c87c92b149a9637ff099f162558
COMPONENT_ARCHIVE_URL=	https://www.nasm.us/pub/nasm/releasebuilds/$(HUMAN_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=		developer/assembler/nasm
COMPONENT_CLASSIFICATION=	Development/Other Languages
COMPONENT_LICENSE=	BSD

include $(WS_MAKE_RULES)/common.mk

CFLAGS  += "-I$(BUILD_DIR_$(BITS))"

COMPONENT_PRE_CONFIGURE_ACTION= ( $(CLONEY) $(SOURCE_DIR) $(@D) )

COMPONENT_POST_CONFIGURE_ACTION += ( mkdir -p $(BUILD_DIR_64)/lib )

COMPONENT_INSTALL_ENV += INSTALLROOT="$(PROTO_DIR)"

COMPONENT_TEST_TARGETS= golden test diff

COMPONENT_TEST_DIR= $(@D)/test

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
