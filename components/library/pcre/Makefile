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
# Copyright (c) 2011, 2013, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2019, Michal Nowak
# Copyright (c) 2022, Daniel Chan
#

BUILD_BITS= 32_and_64
USE_DEFAULT_TEST_TRANSFORMS= yes
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=         pcre
COMPONENT_VERSION=      8.45
COMPONENT_REVISION=     3
COMPONENT_SUMMARY=      Perl-Compatible Regular Expressions
COMPONENT_SRC=          $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=      $(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH= sha256:4dae6fdcd2bb0bb6c37b5f97c33c2be954da743985369cddac3546e3218bffb8
COMPONENT_ARCHIVE_URL=  https://downloads.sourceforge.net/project/$(COMPONENT_NAME)/$(COMPONENT_NAME)/$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL=  http://pcre.org/
COMPONENT_FMRI=         library/pcre
COMPONENT_CLASSIFICATION=Development/C
COMPONENT_LICENSE=      BSD
COMPONENT_LICENSE_FILE= LICENCE

include $(WS_MAKE_RULES)/common.mk

# pick up -std=c99 in CFLAGS
CFLAGS += -std=c99

# turn on largefile support
CFLAGS += $(CPP_LARGEFILES)

CXXFLAGS += $(CC_PIC)

# turn on support for large files
CXXFLAGS+= $(CPP_LARGEFILES)

CONFIGURE_ENV += "CPP=$(CC) $(CPPFLAGS) $(CFLAGS) -E"
CONFIGURE_ENV += "CXXCPP=$(CXX) $(CPPFLAGS) $(CXXFLAGS) -E"
CONFIGURE_ENV += "CXXLDFLAGS=$(LDFLAGS)"
CONFIGURE_ENV += "CXXLD=$(CXX) $(CXXFLAGS) $(LDFLAGS)"
CONFIGURE_ENV += "INSTALL=$(INSTALL)"
CONFIGURE_ENV += "MAKE=$(GMAKE)"

CONFIGURE_ENV.64 += "CXXLINKLIB=$(CXX) $(CCFLAGS) $(LDFLAGS)"
CONFIGURE_ENV.64 += "MACH64=$(MACH64)"

CONFIGURE_OPTIONS += --includedir=$(CONFIGURE_INCLUDEDIR)/pcre
CONFIGURE_OPTIONS += --localstatedir=/var
CONFIGURE_OPTIONS += --disable-static
CONFIGURE_OPTIONS += --enable-cpp
CONFIGURE_OPTIONS += --enable-jit
CONFIGURE_OPTIONS += --enable-rebuild-chartables
CONFIGURE_OPTIONS += --enable-utf8
CONFIGURE_OPTIONS += --enable-unicode-properties
CONFIGURE_OPTIONS += --enable-newline-is-any
CONFIGURE_OPTIONS += --disable-stack-for-recursion
CONFIGURE_OPTIONS += --enable-pcregrep-libz
CONFIGURE_OPTIONS += --enable-pcregrep-libbz2
CONFIGURE_OPTIONS += --with-posix-malloc-threshold=20
CONFIGURE_OPTIONS += --with-link-size=4
CONFIGURE_OPTIONS += --with-match-limit=10000000
CONFIGURE_OPTIONS += --with-pic

CONFIGURE_OPTIONS.64 += --libexecdir=$(CONFIGURE_PREFIX)/libexec/$(MACH64)

# Without this 64-bit libraries get /usr/lib/$(MACH64) RPATH
CONFIGURE_ENV.64 += LT_SYS_LIBRARY_PATH="/lib/$(MACH64):/usr/lib/$(MACH64)"

COMPONENT_BUILD_ENV += "LDFLAGS=$(LDFLAGS)"
COMPONENT_BUILD_ENV += "INSTALL=$(INSTALL)"
COMPONENT_BUILD_ENV += "MAKE=$(GMAKE)"

COMPONENT_BUILD_ARGS += -e

ASLR_MODE= $(ASLR_ENABLE)

COMPONENT_INSTALL_ARGS += "INSTALL=$(INSTALL)"
COMPONENT_INSTALL_ARGS += "MAKE=$(GMAKE)"

# Auto-generated dependencies
REQUIRED_PACKAGES += $(GCC_RUNTIME_PKG)
REQUIRED_PACKAGES += $(GXX_RUNTIME_PKG)
REQUIRED_PACKAGES += compress/bzip2
REQUIRED_PACKAGES += library/zlib
REQUIRED_PACKAGES += shell/ksh93
REQUIRED_PACKAGES += system/library
