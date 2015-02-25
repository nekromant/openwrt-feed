#
# Copyright (C) 2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pl2303ctl
PKG_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/nekromant/pl2303gpio.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk


define Package/pl2303ctl
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libusb-compat
  TITLE:=PL2303/CP210x GPIO tool
  URL:=
endef

define Package/pl2303ctl/description
   pl2303 gpio control tool and scripts
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)"
endef

define Build/Configure
endef


define Package/pl2303ctl/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/init.d/	
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/pl2303gpio          $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/cp2103gpio          $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/extra/serverctl     $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/extra/serverd.lua   $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/etc/init.d/serverd  $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,pl2303ctl))