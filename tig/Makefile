# $Id: Makefile 5624 2006-11-23 00:29:07Z nbd $

include $(TOPDIR)/rules.mk

PKG_NAME:=tig
PKG_VERSION:=0.18
PKG_RELEASE:=1

PKG_SOURCE:=tig-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://jonas.nitro.dk/tig/releases/
PKG_MD5SUM:=4fa9e33c5daa76b6fed11e068405356f
PKG_CAT:=zcat

PKG_BUILD_DIR:=$(BUILD_DIR)/tig-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/tig
	SECTION:=devel
	CATEGORY:=Development
	TITLE:=Console Git repository viewer
	DEPENDS:=+git +libncursesw
	URL:=http://jonas.nitro.dk/tig/releases/
endef

define Package/tig/description
	Tig is an ncurses-based text-mode interface for git.
	It functions mainly as a Git repository browser, but can also assist in staging changes for commit at chunk level and act as a pager for output from various Git commands.
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Package/tig/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tig $(1)/usr/bin/tig
endef

$(eval $(call BuildPackage,tig))
