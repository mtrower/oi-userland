#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2016-2020 Aurelien Larcher
#

X11_CATEGORY=APP
include ../../../make-rules/shared-macros.mk
include $(WS_MAKE_RULES)/x11.mk
BUILD_BITS=32_and_64

COMPONENT_NAME=     xkbcomp
COMPONENT_VERSION=  1.4.6
COMPONENT_SUMMARY=  xkbcomp - compile XKB keyboard description
COMPONENT_ARCHIVE_EXTENSION= .tar.xz
COMPONENT_ARCHIVE_HASH= sha256:fa50d611ef41e034487af7bd8d8c718df53dd18002f591cca16b0384afc58e98
COMPONENT_FMRI=     x11/keyboard/xkbcomp

include $(WS_MAKE_RULES)/common.mk

CPPFLAGS+= -DNO_ALLOCA 

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += x11/library/libx11
REQUIRED_PACKAGES += x11/library/libxkbfile
