SPK_NAME = salt-master
SPK_VERS = 2015.5.11
SPK_REV = 9
SPK_ICON = src/salt-master.png

DEPENDS =
WHEELS = src/requirements.txt
SPK_DEPENDS = "python>2.7.8-10"

MAINTAINER = SynoCommunity
DESCRIPTION = Salt, a new approach to infrastructure management, is easy enough to get running in minutes, scalable enough to manage tens of thousands of servers, and fast enough to communicate with those servers in seconds.
RELOAD_UI = yes
DISPLAY_NAME = Salt Master
CHANGELOG = "1. Update to 2015.5.11<br/>2. Fix salt-api<br/>3. Update dependencies"

HOMEPAGE   = https://www.saltstack.com/
LICENSE    = Apache v2

INSTALLER_SCRIPT = src/installer.sh
SSS_SCRIPT       = src/dsm-control.sh
FWPORTS          = src/${SPK_NAME}.sc

POST_STRIP_TARGET = salt-master_extra_install

# Pure Python package, make sure ARCH is not defined
override ARCH=

include ../../mk/spksrc.spk.mk

.PHONY: salt-master_extra_install
salt-master_extra_install:
	install -m 755 -d $(STAGING_DIR)/var
	install -m 755 -d $(STAGING_DIR)/etc
	install -m 644 src/master $(STAGING_DIR)/etc/master
	install -m 755 -d $(STAGING_DIR)/share/extensions
	install -m 755 -d $(STAGING_DIR)/share/extensions/auth
	install -m 644 src/synology.py $(STAGING_DIR)/share/extensions/auth/synology.py

