#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2009, 2012, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2018, Michal Nowak
# Copyright (c) 2020, 2022, Andreas Wacknitz
#

BUILD_BITS=			64
#USE_OPENSSL11=		yes
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		rsync
COMPONENT_VERSION=	3.2.7
COMPONENT_SUMMARY=	Utility that provides fast incremental file transfer and copy
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_PROJECT_URL=	https://rsync.samba.org/
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	sha256:4e7d9d3f6ed10878c58c5fb724a67dacf4b6aac7340b13e488fb2dc41346f2bb
COMPONENT_ARCHIVE_URL=	https://rsync.samba.org/ftp/rsync/src/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=	network/rsync
COMPONENT_CLASSIFICATION= Applications/System Utilities
COMPONENT_LICENSE=	GPLv3
COMPONENT_LICENSE_FILE=	COPYING

include $(WS_MAKE_RULES)/common.mk

CONFIGURE_BINDIR.64 = $(CONFIGURE_PREFIX)/bin

CONFIGURE_OPTIONS  +=	--with-included-popt
CONFIGURE_OPTIONS  +=	--enable-xattr-support
# disable xxHash until we provide a package for it (https://github.com/Cyan4973/xxHash)
CONFIGURE_OPTIONS  +=	--disable-xxhash

COMPONENT_TEST_TRANSFORMER = $(NAWK)
COMPONENT_TEST_TRANSFORMS = "'/^PASS|^SKIP|^FAIL|^XFAIL/'"

# Manually added; needed during tests
REQUIRED_PACKAGES += developer/fakeroot

# Auto-generated dependencies
REQUIRED_PACKAGES += SUNWcs
REQUIRED_PACKAGES += compress/zstd
REQUIRED_PACKAGES += library/lz4
REQUIRED_PACKAGES += library/security/openssl
REQUIRED_PACKAGES += system/library
