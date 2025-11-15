#
# Copyright (C) 2007-2021 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=busybox-httpd-service
PKG_VERSION:=1.2.1
PKG_RELEASE:=1
PKG_MAINTAINER:=Sergey Ponomarev <stokito@gmail.com>
PKG_LICENSE:=ISC

include $(INCLUDE_DIR)/package.mk

define Package/busybox-httpd-service
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Web Servers/Proxies
  TITLE:=BusyBox HTTPd - basic HTTP server
  DEPENDS:=@BUSYBOX_CONFIG_HTTPD @CONFIG_BUSYBOX_CONFIG_FEATURE_HTTPD_CGI
  PKGARCH:=all
endef

define Package/busybox-httpd-service/description
  BusyBox HTTP daemon is a tiny single threaded HTTP server with support of basic features
endef

define Package/busybox-httpd-service/conffiles
/etc/httpd.conf
/etc/config/httpd
endef

define Build/Compile
endef

define Package/busybox-httpd-service/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/busybox-httpd $(1)/etc/init.d/busybox-httpd

	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/etc/config/httpd $(1)/etc/config/httpd

	$(INSTALL_DIR) $(1)/etc/
	$(INSTALL_CONF) ./files/etc/httpd.conf $(1)/etc/httpd.conf
endef

$(eval $(call BuildPackage,busybox-httpd-service))
