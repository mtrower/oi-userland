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
# Copyright 2014 Josef 'Jeff' Sipek <jeffpc@josefsipek.net>
# Copyright 2019 Nona Hansel
#

BUILD_STYLE = justmake
# To run tests we need real files, not symlinks
CLONEY_ARGS = CLONEY_MODE="hardlink"

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		sloccount
COMPONENT_VERSION=	2.26
COMPONENT_REVISION=	3
COMPONENT_PROJECT_URL=	http://www.dwheeler.com/sloccount/
COMPONENT_FMRI=		text/sloccount
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
	sha256:fa7fa2bbf2f627dd2d0fdb958bd8ec4527231254c120a8b4322405d8a4e3d12b
COMPONENT_ARCHIVE_URL=	http://www.dwheeler.com/sloccount/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE=	GPL-2.0-only
COMPONENT_LICENSE_FILE=	COPYING
COMPONENT_SUMMARY=	SLOCCount a set of tools for counting physical Source Lines of Code (SLOC)
COMPONENT_CLASSIFICATION=System/Text Tools

include $(WS_MAKE_RULES)/common.mk

COMPONENT_BUILD_ENV += CC=$(CC)

COMPONENT_INSTALL_ENV += INSTALL=$(INSTALL)
COMPONENT_INSTALL_ENV += PREFIX=$(PROTO_DIR)/usr

COMPONENT_TEST_TARGETS = test
COMPONENT_TEST_ENV += HOME=$(@D)
COMPONENT_TEST_TRANSFORMS += '-e "/^make\[/d"'			# delete make logs

# Auto-generated dependencies
REQUIRED_PACKAGES += runtime/perl
REQUIRED_PACKAGES += shell/ksh93
REQUIRED_PACKAGES += system/library
