#
# Copyright (C) 2006-2023 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=msd_lite
PKG_VERSION:=1.11
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2024-03-16
PKG_SOURCE_URL:=https://github.com/rozhuk-im/msd_lite.git
PKG_SOURCE_VERSION:=db583386ca47d803e44d9adc98b1ec6a4abb5d9a
PKG_MIRROR_HASH:=skip

PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/msd_lite
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Multi Stream daemon Lite
  URL:=https://github.com/rozhuk-im/msd_litea
  DEPENDS:= +libpthread
endef

define Package/msd_lite/description
Program for IP TV streaming on the network via HTTP
endef

define Package/msd_lite/conffiles
/etc/msd_lite/msd_lite.conf
endef

CMAKE_OPTIONS += \
	-DCONFDIR=/etc/msd_lite

define Package/msd_lite/install
	$(INSTALL_DIR) $(1)/etc/msd_lite $(1)/usr/bin
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/conf/msd_lite.conf $(1)/etc/msd_lite/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/msd_lite $(1)/usr/bin/
endef

$(eval $(call BuildPackage,msd_lite))
