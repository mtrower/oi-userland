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
# Copyright 2018 Josef 'Jeff' Sipek <jeffpc@josefsipek.net>
# Copyright 2018 Michal Nowak
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		lzip
COMPONENT_VERSION=	1.24
COMPONENT_SUMMARY=	Lzip - a lossless data compressor with a user interface similar to the one of gzip or bzip2
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_PROJECT_URL=	https://lzip.nongnu.org/
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	sha256:d42659229b10e066eeb6e81eb673cdd893b672e512d26719c2d95975556ca56c
COMPONENT_ARCHIVE_URL=	https://download.savannah.gnu.org/releases/lzip/$(COMPONENT_ARCHIVE)
# Signature verification fails
#COMPONENT_SIG_URL=	https://download.savannah.gnu.org/releases/lzip/$(COMPONENT_ARCHIVE).sig
COMPONENT_FMRI=		compress/lzip
COMPONENT_CLASSIFICATION= Applications/System Utilities
COMPONENT_LICENSE=	GPLv2+
COMPONENT_LICENSE_FILE=	COPYING

include $(WS_MAKE_RULES)/common.mk

COMPONENT_TEST_TRANSFORMER = $(NAWK)
COMPONENT_TEST_TRANSFORMS = "'/testing|tests/'"

# Auto-generated dependencies
REQUIRED_PACKAGES += $(GCC_RUNTIME_PKG)
REQUIRED_PACKAGES += $(GXX_RUNTIME_PKG)
REQUIRED_PACKAGES += system/library
