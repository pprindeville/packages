
include $(TOPDIR)/rules.mk

PKG_NAME:=tmux
PKG_VERSION:=3.2a
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/tmux/tmux/tar.gz/$(PKG_VERSION)?
PKG_HASH:=497bc4ee16f10b53b161bf0253b6f9e20cd0f86c5d0104f149212cb0778ae13a
PKG_MAINTAINER:=Maxim Storchak <m.storchak@gmail.com>

PKG_LICENSE:=ISC
PKG_LICENSE_FILES:=COPYING
PKG_CPE_ID:=cpe:/a:nicholas_marriott:tmux

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/tmux
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Terminal
  TITLE:=Terminal multiplexer
  DEPENDS:=+libncurses +libevent2-core +libpthread +librt
  URL:=http://tmux.github.io/
endef

define Package/tmux/description
  tmux is a modern, BSD-licensed alternative to GNU screen.
endef

define Package/tmux/conffiles
/etc/tmux.conf
endef

define Package/tmux/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/tmux $(1)/usr/bin/
endef

$(eval $(call BuildPackage,tmux))
