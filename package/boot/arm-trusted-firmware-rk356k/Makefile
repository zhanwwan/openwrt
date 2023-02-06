#
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=arm-trusted-firmware-rk356x
PKG_RELEASE:=2.0
PKG_SOURCE_DATE:=2022-07-31
PKG_SOURCE_VERSION:=b0c100f1a260d807df450019774993c761beb79d
PKG_SOURCE_PROTO:=git
PKG_FLAGS:=nonshared
PKG_MIRROR_HASH:=103b2fd0dcdf6268050020bfa72bfa79e827b7b6800421e5f2536295444142e0
PKG_SOURCE_URL:=https://github.com/rockchip-linux/rkbin.git

include $(INCLUDE_DIR)/package.mk

define Package/arm-trusted-firmware-rk356x
    SECTION:=boot
    CATEGORY:=Boot Loaders
    TITLE:=ARM Trusted Firmware for RK356X
    DEPENDS:=@TARGET_rockchip_armv8
endef

define Build/Compile
endef

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR_IMAGE)
	$(CP) $(PKG_BUILD_DIR)/bin/rk35/rk3568_bl31_v1.34.elf $(PKG_BUILD_DIR)/bl31.elf
	$(CP) $(PKG_BUILD_DIR)/bl31.elf $(STAGING_DIR_IMAGE)/
	$(CP) $(PKG_BUILD_DIR)/bin/rk35/rk3568_ddr_1560MHz_v1.13.bin $(PKG_BUILD_DIR)/ram_init.bin
	$(CP) $(PKG_BUILD_DIR)/ram_init.bin $(STAGING_DIR_IMAGE)/
endef

define Package/arm-trusted-firmware-rk356x/install
endef

$(eval $(call BuildPackage,arm-trusted-firmware-rk356x))
