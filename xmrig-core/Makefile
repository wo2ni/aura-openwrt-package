include $(TOPDIR)/rules.mk

PKG_NAME:=xmrig
PKG_VERSION:=6.20.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
#PKG_SOURCE_URL:=file:///../../my_package/xmrig-core/
PKG_SOURCE_URL:=http://192.168.222.111:8001/
PKG_HASH:=c531b45238ace21cf4cbae44955cfd40

PKG_MAINTAINER:=unknown
PKG_LICENSE:=GPL-3.0-only
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/xmrig
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=XMRig - Monero Miner
  URL:=https://github.com/xmrig/xmrig
  DEPENDS:=+libpthread +libstdcpp +libopenssl
endef

define Package/xmrig/description
   XMRig is a high-performance Monero (XMR) CPU miner.
endef

define Build/Prepare
	$(CP) /path/to/local/source/directory/$(PKG_SOURCE) $(DL_DIR)/$(PKG_SOURCE)
	$(PKG_UNPACK)
	$(SED) 's/^cmake_minimum_required/#cmake_minimum_required/' $(PKG_BUILD_DIR)/CMakeLists.txt
endef

define Build/Configure
	$(MKDIR) $(PKG_BUILD_DIR)/build
	(cd $(PKG_BUILD_DIR)/build; cmake .. \
	-DCMAKE_TOOLCHAIN_FILE=$(TOPDIR)/toolchain.cmake \
	-DCMAKE_INSTALL_PREFIX=/usr \
	-DWITH_HTTPD=OFF \
	-DWITH_TLS=OFF \
	-DWITH_HWLOC=OFF \
	-DWITH_ASM=OFF \
	-DWITH_AVX2=OFF \
	)
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)/build
endef

define Package/xmrig/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/xmrig $(1)/usr/bin/
endef

$(eval $(call BuildPackage,xmrig))
