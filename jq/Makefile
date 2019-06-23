include $(TOPDIR)/rules.mk

PKG_NAME:=jq
PKG_VERSION:=1.5
PKG_RELEASE:=1

PKG_SOURCE:=jq-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/stedolan/jq/releases/download/jq-1.5/
PKG_MD5SUM:=0933532b086bd8b6a41c1b162b1731f9
PKG_CAT:=zcat

PKG_BUILD_DIR:=$(BUILD_DIR)/jq-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/jq
        SECTION:=utils
        CATEGORY:=Utilities
        TITLE:=jq
#       DEPENDS:=
        URL:=http://jq.org
endef

define Package/jq/description
        jq is a lightweight and flexible command-line JSON processor.
endef

define Build/Configure
        $(call Build/Configure/Default, \
                --prefix=/usr \
        )
endef

define Package/jq/install
        $(INSTALL_DIR) $(1)/usr/bin/
        $(INSTALL_BIN) $(PKG_BUILD_DIR)/jq $(1)/usr/bin/
endef

$(eval $(call BuildPackage,jq))
