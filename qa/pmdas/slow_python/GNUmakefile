#
# Copyright (c) 2014 Ken McDonell.  All Rights Reserved.
# 
# This program is free software; you can redistribute it and/or modify it
# under the terms of the GNU General Public License as published by the
# Free Software Foundation; either version 2 of the License, or (at your
# option) any later version.
# 
# This program is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
# or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License
# for more details.
#

TOPDIR = ../../..
include $(TOPDIR)/src/include/builddefs

IAM	= slow_python
TESTDIR = $(PCP_VAR_DIR)/testsuite/pmdas/$(IAM)
PYSCRIPT = pmda$(IAM).python

LDIRT	= domain.h $(IAM).log pmns.python

default default_pcp setup: check_domain

include $(BUILDRULES)

install_pcp install:	default 
	$(INSTALL) -m 755 -d $(TESTDIR)
	$(INSTALL) -m 755 -f Install Remove $(TESTDIR)
	$(INSTALL) -m 644 -f $(PYSCRIPT) $(TESTDIR)/$(PYSCRIPT)
	$(INSTALL) -m 644 -f GNUmakefile.install $(TESTDIR)/GNUmakefile

check_domain:	$(TOPDIR)/src/pmns/stdpmid
	$(DOMAIN_PYTHONRULE)
