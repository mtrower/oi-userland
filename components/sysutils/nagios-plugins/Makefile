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
# Copyright 2023 Marcel Telka
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		nagios-plugins
COMPONENT_VERSION =		2.4.8
COMPONENT_SUMMARY =		Nagios Plugins
COMPONENT_PROJECT_URL =		https://github.com/nagios-plugins/nagios-plugins
COMPONENT_FMRI =		system/management/nagios/plugins
COMPONENT_CLASSIFICATION =	System/Enterprise Management
COMPONENT_SRC =			$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE =		$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_URL =		\
	$(COMPONENT_PROJECT_URL)/releases/download/$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_ARCHIVE_HASH =	\
	sha256:8e09e9ec1676ecead7e7c7d41d5ea48d5c4bfdfaddfc756d0dd732df7c8f85e4
COMPONENT_LICENSE =		GPL-3.0-only
COMPONENT_LICENSE_FILE =	COPYING

include $(WS_MAKE_RULES)/common.mk

# force needed rpath
LD_OPTIONS += -R$(PG_LIBDIR)
LD_OPTIONS += -R$(MYSQL_LIBDIR)

CONFIGURE_OPTIONS +=	--libexecdir=$(CONFIGURE_PREFIX)/libexec/nagios-plugins
CONFIGURE_OPTIONS +=	--enable-libtap
CONFIGURE_OPTIONS +=	--with-pgsql=$(PG_HOME)
CONFIGURE_OPTIONS +=	--with-mysql=$(MYSQL_HOME)
CONFIGURE_OPTIONS +=	--without-dbi
CONFIGURE_OPTIONS +=	--without-radius
CONFIGURE_OPTIONS +=	--without-smbclient-command
CONFIGURE_OPTIONS +=	--without-qmail-qstat-command
CONFIGURE_OPTIONS +=	--without-smtpctl-command

# pst3 needs to be manually installed
COMPONENT_POST_INSTALL_ACTION += $(CP) $(@D)/plugins-root/pst3 $(PROTOUSRDIR)/libexec/nagios-plugins ;

# Testing needs internet access and site specific setup
COMPONENT_TEST_TARGETS = test

# Manually added dependencies
REQUIRED_PACKAGES += $(MYSQL_CLIENT_PKG)
REQUIRED_PACKAGES += $(PG_DEVELOPER_PKG)
REQUIRED_PACKAGES += diagnostic/fping
TEST_REQUIRED_PACKAGES += library/perl-5/crypt-x509
TEST_REQUIRED_PACKAGES += library/perl-5/libwww-perl
TEST_REQUIRED_PACKAGES += library/perl-5/text-glob
TEST_REQUIRED_PACKAGES += library/perl-5/timedate

# Auto-generated dependencies
REQUIRED_PACKAGES += $(MYSQL_LIBRARY_PKG)
REQUIRED_PACKAGES += $(PG_LIBRARY_PKG)
REQUIRED_PACKAGES += library/security/openssl
REQUIRED_PACKAGES += runtime/perl
REQUIRED_PACKAGES += shell/ksh93
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/math
