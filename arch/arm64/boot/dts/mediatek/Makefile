# SPDX-License-Identifier: GPL-2.0

dtb-$(CONFIG_ARCH_MEDIATEK) += mt2712-evb.dtb
dtb-$(CONFIG_ARCH_MEDIATEK) += mt6755-evb.dtb
dtb-$(CONFIG_ARCH_MEDIATEK) += mt6795-evb.dtb
dtb-$(CONFIG_ARCH_MEDIATEK) += mt6797-evb.dtb
dtb-$(CONFIG_ARCH_MEDIATEK) += mt7622-rfb1.dtb
dtb-$(CONFIG_ARCH_MEDIATEK) += mt8173-evb.dtb

ifeq ($(strip $(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE)), y)
dtb-y += $(addsuffix .dtb, $(notdir $(subst $\",,$(CONFIG_BUILD_ARM64_APPENDED_DTB_IMAGE_NAMES))))
endif

ifeq ($(strip $(CONFIG_BUILD_ARM64_DTB_OVERLAY_IMAGE)), y)
dtbo-y += $(addsuffix .dtbo, $(notdir $(subst $\",,$(CONFIG_BUILD_ARM64_DTB_OVERLAY_IMAGE_NAMES))))
endif

always		:= $(dtb-y) $(dtbo-y)
subdir-y	:= $(dts-dirs)
clean-files	:= *.dtb  *.dtbo

ifeq ($(CONFIG_BUILD_ARM64_DTBO_IMG),y)
dtbo-$(CONFIG_ARCH_MEDIATEK) += \
	oppo8786.dtbo \
	oppo8786_wlan.dtbo \
	oppo8786_21697.dtbo
oppo8786.dtbo-base := oppo8786.dtb mt6768.dtb
oppo8786_wlan.dtbo-base := oppo8786_wlan.dtb mt6768.dtb
oppo8786_21697.dtbo-base := oppo8786_21697.dtb mt6768.dtb
else
dtb-$(CONFIG_ARCH_MEDIATEK)	+= \
	mt6768.dtb \
	oppo8786.dtb \
	oppo8786_wlan.dtb \
	oppo8786_21697.dtb
endif
