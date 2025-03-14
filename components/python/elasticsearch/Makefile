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
# This file was automatically generated using the following command:
#   $WS_TOOLS/python-integrate-project elasticsearch
#

BUILD_STYLE = setup.py

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		elasticsearch
HUMAN_VERSION =			8.12.0
COMPONENT_SUMMARY =		elasticsearch - Python client for Elasticsearch
COMPONENT_PROJECT_URL =		https://github.com/elastic/elasticsearch-py
COMPONENT_ARCHIVE_URL =		\
	https://github.com/elastic/elasticsearch-py/archive/refs/tags/v$(HUMAN_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH =	\
	sha256:4618c879499f01b8b7e46932934bd840829e1d34c2647a496b7503682abe1122
COMPONENT_LICENSE =		Apache-2.0
COMPONENT_LICENSE_FILE =	LICENSE

TEST_STYLE = pytest

COMPONENT_SRC = elasticsearch-py-$(HUMAN_VERSION)

include $(WS_MAKE_RULES)/common.mk

# This project does not support tox so we need to provide test requirements
# manually.
TEST_REQUIREMENTS += dev-requirements.txt

# Auto-generated dependencies
PYTHON_REQUIRED_PACKAGES += library/python/elastic-transport
PYTHON_REQUIRED_PACKAGES += runtime/python
TEST_REQUIRED_PACKAGES.python += library/python/aiohttp
TEST_REQUIRED_PACKAGES.python += library/python/black
TEST_REQUIRED_PACKAGES.python += library/python/build
TEST_REQUIRED_PACKAGES.python += library/python/coverage
TEST_REQUIRED_PACKAGES.python += library/python/elastic-transport
TEST_REQUIRED_PACKAGES.python += library/python/isort
TEST_REQUIRED_PACKAGES.python += library/python/jinja2
TEST_REQUIRED_PACKAGES.python += library/python/nox
TEST_REQUIRED_PACKAGES.python += library/python/pytest
TEST_REQUIRED_PACKAGES.python += library/python/pytest-asyncio
TEST_REQUIRED_PACKAGES.python += library/python/pytest-cov
TEST_REQUIRED_PACKAGES.python += library/python/python-dateutil
TEST_REQUIRED_PACKAGES.python += library/python/pyyaml
TEST_REQUIRED_PACKAGES.python += library/python/requests
TEST_REQUIRED_PACKAGES.python += library/python/sphinx
TEST_REQUIRED_PACKAGES.python += library/python/sphinx-rtd-theme
TEST_REQUIRED_PACKAGES.python += library/python/twine
