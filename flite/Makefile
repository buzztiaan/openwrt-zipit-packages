# 
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=flite
PKG_VERSION:=2.0.0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-release.tar.bz2
PKG_SOURCE_URL:=http://festvox.org/flite/packed/flite-2.0

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)-release
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/flite
  SECTION:=multimedia
  CATEGORY:=Multimedia
  TITLE:=festival-lite
  URL:=http://www.speech.cs.cmu.edu/flite/index.html
  DEPENDS:=+alsa-lib
endef

define Package/flite/description
  a small, fast run-time synthesis engine
endef

define Build/Prepare
	$(call Build/Prepare/Default)
	cp -f files/zipit.lv $(PKG_BUILD_DIR)/config
endef

#CONFIGURE_ARGS += --with-langvox=ben
#CONFIGURE_ARGS += --with-langvox="cmu_us_kal16" --with-audio="oss"
CONFIGURE_ARGS += --with-langvox="zipit" --with-audio="oss"

define Package/flite/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/flite $(1)/usr/bin/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include $(1)/usr/lib

	$(CP) $(PKG_BUILD_DIR)/include/*.h $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/build/arm-linux-gnu/lib/*.a \
		$(1)/usr/lib/
endef

$(eval $(call BuildPackage,flite))
