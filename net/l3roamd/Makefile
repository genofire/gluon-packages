include $(TOPDIR)/rules.mk

PKG_NAME:=l3roamd
PKG_SOURCE_DATE:=2019-09-19
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/christf/l3roamd.git
PKG_SOURCE_BRANCH:=emptyq
PKG_SOURCE_VERSION=3791ee189e741d69fb123a73b9d7e02c0942e76c

CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE:STRING=MINSIZEREL
#CMAKE_OPTIONS += -DCMAKE_BUILD_TYPE:STRING=Debug

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/l3roamd
  SECTION:=net
  CATEGORY:=Network
  TITLE:=The layer 3 roaming daemon
  DEPENDS:=+libnl-tiny +kmod-tun +librt +libjson-c
endef

define Package/l3roamd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/l3roamd $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,l3roamd))
