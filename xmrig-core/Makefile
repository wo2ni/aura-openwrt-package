include $(TOPDIR)/rules.mk

PKG_NAME:=xmrig
PKG_VERSION:=6.15.3
PKG_RELEASE:=1


PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/xmrig/xmrig.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/xmrig
	SECTION:=net
	CATEGORY:=Network
  	TITLE:=XMRig CPU miner
  	URL:=https://github.com/xmrig/xmrig
	DEPENDS:=+libstdcpp +libuv +libopenssl +libhwloc
endef

define Package/xmrig/description
	XMRig is a high performance Monero (XMR) CPU miner.
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/xmrig/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/xmrig $(1)/usr/bin/
endef

$(eval $(call BuildPackage,xmrig))
