# SPDX-License-Identifier: GPL-2.0

# Kbuild doesn't recognize that we want overlays, since there aren't any in
# this directory. But we're going to build and apply those from other trees, so
# force __symbols__ generation.
DTC_FLAGS += -@

gs201_dtbs := \
	gs201-a0.dtb \
	gs201-b0.dtb \
	gs201-b0_v2-ipop.dtb

gs201_overlays_a0 := \
	gs201-cloudripper-dev.dtbo \
	gs201-ravenclaw-dev1_0.dtbo \
	gs201-ravenclaw-dev1_1.dtbo \
	gs201-cheetah-proto1.dtbo \
	gs201-cheetah-proto1_1.dtbo \
	gs201-cheetah-proto1_1-wingboard.dtbo \
	gs201-cheetah-evt1.dtbo \
	gs201-cheetah-evt1-wingboard.dtbo \
	gs201-cheetah-evt1-nfc.dtbo \
	gs201-cheetah-evt1_1.dtbo \
	gs201-cheetah-evt1_1-wingboard.dtbo \
	gs201-cheetah-dvt1.dtbo \
	gs201-cheetah-pvt1.dtbo \
	gs201-cheetah-mp.dtbo \
	gs201-panther-proto1.dtbo \
	gs201-panther-proto1_1.dtbo \
	gs201-panther-proto1_1-wingboard.dtbo \
	gs201-panther-evt1.dtbo \
	gs201-panther-evt1-wingboard.dtbo \
	gs201-panther-evt1_1.dtbo \
	gs201-panther-evt1_1-wingboard.dtbo \
	gs201-panther-dvt1.dtbo \
	gs201-panther-pvt1.dtbo \
	gs201-panther-mp.dtbo \
	gs201-lynx-dev1_0.dtbo \
	gs201-lynx-proto1_0.dtbo

gs201_overlays_b0_v2 := \
	gs201-lynx-proto1_1.dtbo \
	gs201-lynx-evt1_0.dtbo \
	gs201-lynx-evt1_0-wingboard.dtbo \
	gs201-lynx-evt1_1.dtbo \
	gs201-lynx-dvt1_0.dtbo \
	gs201-lynx-dvt1_0-gain1.dtbo \
	gs201-lynx-pvt1_0.dtbo \
	gs201-lynx-mp1_0.dtbo

dtb-y += $(gs201_dtbs)
dtbo-y += $(gs201_overlays_a0) $(gs201_overlays_b0_v2)

define multi_dtbs_overlay
	$(foreach base, $1, \
		$(foreach overlay, $2, \
			$(eval $(overlay)-base := $(base))))
endef

$(call multi_dtbs_overlay, gs201-a0.dtb, $(gs201_overlays_a0))
$(call multi_dtbs_overlay, gs201-b0_v2-ipop.dtb, $(gs201_overlays_b0_v2))

MKDTIMG_FLAGS += --page_size=4096  --id=/:board_id --rev=/:board_rev
