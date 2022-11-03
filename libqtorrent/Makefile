include $(TOPDIR)/rules.mk

PKG_NAME:=libqtorrent
PKG_VERSION:=1.2.18
PKG_RELEASE=2022-10-24

PKG_SOURCE_PROTO:=git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/arvidn/libtorrent.git
PKG_SOURCE_DATE:=2022-10-24
PKG_SOURCE_VERSION:=cd05e947f6654e0a46f0385ab12c5bf446cce671

PKG_MAINTAINER:=David Yang <mmyangfl@gmail.com>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/libqtorrent/Default
	TITLE:=C++ library implementing the BitTorrent protocol
	URL:=https://libtorrent.org/
endef

define Package/libqtorrent
	$(call Package/libqtorrent/Default)
	SECTION:=libs
	CATEGORY:=Libraries
	DEPENDS:=+boost-system +libopenssl +libatomic +libstdcpp
endef

define Package/libqtorrent/description
    libtorrent is an open source C++ library implementing the BitTorrent protocol
endef

define Download/try_signal
	VERSION:=751a7e5a5be14892bcfdff1e63c653bcbf71cf39
	SUBDIR:=deps/try_signal
	FILE:=$(PKG_NAME)-try_signal-$$(VERSION).tar.xz
	URL:=https://github.com/arvidn/try_signal.git
	MIRROR_HASH:=32a432e35e81c79f21c49744f00696c112e0deab45d15d91c61ceb63fe25a5f8
	PROTO:=git
endef
$(eval $(call Download,try_signal))

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Build/Prepare
	$(Build/Prepare/Default)
	$(eval $(Download/try_signal))
	xzcat $(DL_DIR)/$(FILE) | tar -C $(PKG_BUILD_DIR) $(TAR_OPTIONS)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/libtorrent $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtorrent-rasterbar.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/libtorrent-rasterbar.pc $(1)/usr/lib/pkgconfig/
endef

define Package/libqtorrent/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtorrent-rasterbar.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libqtorrent))
