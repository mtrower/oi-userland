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
# Copyright 2021 Till Wegmueller
#

BUILD_BITS= 64
USE_DEFAULT_TEST_TRANSFORMS= yes
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=			oniguruma
COMPONENT_VERSION_BASE=		6.9.9
COMPONENT_VERSION=		$(COMPONENT_VERSION_BASE)
COMPONENT_SUMMARY=		oniguruma - regular expression library 
COMPONENT_PROJECT_URL=		https://github.com/kkos/oniguruma
COMPONENT_SRC=			onig-$(COMPONENT_VERSION_BASE)
COMPONENT_SRC2=			onig-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=		$(COMPONENT_SRC2).tar.gz
COMPONENT_ARCHIVE_URL=		https://github.com/kkos/$(COMPONENT_NAME)/releases/download/v$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_ARCHIVE_HASH=		sha256:60162bd3b9fc6f4886d4c7a07925ffd374167732f55dce8c491bfd9cd818a6cf
COMPONENT_FMRI=			text/oniguruma
COMPONENT_CLASSIFICATION=	Applications/System Utilities
COMPONENT_LICENSE=		BSD like
COMPONENT_LICENSE_FILE=		COPYING

include $(WS_MAKE_RULES)/common.mk

CONFIGURE_OPTIONS += --enable-static=no

unexport SHELLOPTS

# Auto-generated dependencies
REQUIRED_PACKAGES += shell/ksh93
REQUIRED_PACKAGES += system/library
