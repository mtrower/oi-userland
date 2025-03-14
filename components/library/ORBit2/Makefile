#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL)". You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright (c) 2014 Alexander Pyhalov. All rights reserved
#

BUILD_STYLE=configure
BUILD_BITS=32_and_64
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=         ORBit2
COMPONENT_VERSION=      2.14.19
COMPONENT_REVISION=     5
COMPONENT_PROJECT_URL=  https://projects.gnome.org/ORBit2/
COMPONENT_SUMMARY=      High-performance CORBA Object Request Broker
COMPONENT_SRC=          $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=      $(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH= \
	sha256:55c900a905482992730f575f3eef34d50bda717c197c97c08fa5a6eafd857550
    
COMPONENT_ARCHIVE_URL=  https://download.gnome.org/sources/$(COMPONENT_NAME)/2.14/$(COMPONENT_ARCHIVE)

include $(WS_MAKE_RULES)/common.mk

PATH=$(PATH.gnu)

COMPONENT_PREP_ACTION =        ( cd $(@D) && \
                                        aclocal -I. && \
                                        autoheader && \
					PATH="$(PATH)" libtoolize --automake --copy --force && \
                                        automake -a -f -c &&\
                                        autoconf )

CONFIGURE_OPTIONS.32 += --sysconfdir=/etc
CONFIGURE_OPTIONS.64 += --sysconfdir=/etc/$(MACH64)

# Without this includes are rewritten with 64-bit files,
# and we don't want this
$(INSTALL_32):	$(INSTALL_64)

# Build dependencies
REQUIRED_PACKAGES+= developer/documentation-tool/gtk-doc

# Auto-generated dependencies
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += library/libidl
REQUIRED_PACKAGES += shell/ksh93
REQUIRED_PACKAGES += system/library
