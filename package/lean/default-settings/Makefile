#
# Copyright (C) 2016-2023 GitHub 
#
# This is free software, licensed under the GNU General Public License v3.
# See /LICENSE for more information.

include $(TOPDIR)/rules.mk

PKG_NAME:=default-settings
PKG_VERSION:=3
PKG_RELEASE:=8
PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/default-settings
  SECTION:=luci
  CATEGORY:=LuCI
  TITLE:=LuCI support for Default Settings
  PKGARCH:=all
  DEPENDS:=+luci-base +luci +@LUCI_LANG_zh-cn
endef

define Package/default-settings/description
	Language Support Packages.
endef

define Build/Compile
endef

define Package/default-settings/install
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/zzz-default-settings $(1)/etc/uci-defaults/99-default-settings
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	po2lmo ./po/zh-cn/default.po $(1)/usr/lib/lua/luci/i18n/default.zh-cn.lmo
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_BIN) ./files/adbyby3.famic $(1)/etc/config/adbyby3.famic
	$(INSTALL_BIN) ./files/smartdns.famic $(1)/etc/config/smartdns.famic
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) ./files/adg.tar.gz $(1)/usr/bin/adg.tar.gz
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_BIN) ./files/dnsmasq.famic $(1)/etc/dnsmasq.famic
endef

$(eval $(call BuildPackage,default-settings))
