# SPDX-Identifier-License: GPL-3.0-only
#
# Copyright (C) 2021 ImmortalWrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=lux
PKG_VERSION:=0.24.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/iawia002/lux/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=3d69faf2e98f92df9984baf38bec02a88bf2db2113771e9567570d802d8fddde

PKG_MAINTAINER:=Tianling Shen <cnsztl@immortalwrt.org>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_BUILD_FLAGS:=no-mips16

GO_PKG:=github.com/iawia002/lux
GO_PKG_BUILD_PKG:=$$(GO_PKG)
GO_PKG_LDFLAGS:=-s -w

include $(INCLUDE_DIR)/package.mk
include ../../lang/golang/golang-package.mk

define Package/lux
  SECTION:=multimedia
  CATEGORY:=Multimedia
  TITLE:=A fast, simple and clean video downloader
  URL:=https://github.com/iawia002/lux
  DEPENDS:=$(GO_ARCH_DEPENDS) +ffmpeg
endef

$(eval $(call GoBinPackage,lux))
$(eval $(call BuildPackage,lux))
