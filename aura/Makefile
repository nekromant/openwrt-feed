#
# Copyright (C) 2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=aura
PKG_VERSION:=master
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/nekromant/aura.git
PKG_SOURCE:=$(PKG_NAME).tar.gz
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk


define Package/aura
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libusb-1.0 +liblua
  TITLE:=PL2303/CP210x GPIO tool
  URL:=
endef

define Package/aura/description
	AURA universal RPC system
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)"
endef

define Build/Configure
endef


define Package/aura/install
endef

$(eval $(call BuildPackage,aura))