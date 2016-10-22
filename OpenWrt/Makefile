#
# Copyright (C) 2016 Jean-Christophe Rona <jc@rona.fr>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=home-rf
PKG_VERSION:=0.6
PKG_RELEASE:=1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/home-rf
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Home-RF Web UI
  DEPENDS:=+rf-ctrl +uhttpd
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/home-rf/install
	$(INSTALL_DIR) $(1)/www/cgi-bin
	$(INSTALL_BIN) ./files/www/cgi-bin/home-rf $(1)/www/cgi-bin/
	$(INSTALL_DIR) $(1)/www/home-rf
	$(INSTALL_BIN) ./files/www/home-rf/favicon.ico $(1)/www/home-rf/
	$(INSTALL_BIN) ./files/www/home-rf/favicon.png $(1)/www/home-rf/
	$(INSTALL_BIN) ./files/www/home-rf/presets.conf $(1)/www/home-rf/
	$(INSTALL_BIN) ./files/www/home-rf/background.png $(1)/www/home-rf/
	$(INSTALL_BIN) ./files/www/home-rf/index.html $(1)/www/home-rf/
endef

$(eval $(call BuildPackage,home-rf))
