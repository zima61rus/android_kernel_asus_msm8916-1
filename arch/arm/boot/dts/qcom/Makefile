ifeq ($(CONFIG_OF),y)

dtb-$(CONFIG_ARCH_MSM8916) += msm8916-mtp-ze550kl.dtb \
        msm8929-cdp-ze550kl.dtb \
        msm8929-cdp-ze600kl.dtb \
        msm8939-cdp-ze550kl.dtb \
        msm8939-cdp-ze600kl.dtb \
        msm8939-cdp-zx550kl.dtb \
	msm8939-cdp-zd550kl.dtb


DTB_NAMES := $(subst $\",,$(CONFIG_BUILD_ARM_APPENDED_DTB_IMAGE_NAMES))
ifneq ($(DTB_NAMES),)
DTB_LIST := $(addsuffix .dtb,$(DTB_NAMES))
else
DTB_LIST := $(dtb-y)
endif

targets += dtbs
targets += $(addprefix ../, $(DTB_LIST))
endif

$(obj)/../%.dtb: $(src)/%.dts FORCE
	$(call if_changed_dep,dtc)

dtbs: $(addprefix $(obj)/../,$(DTB_LIST))

clean-files := *.dtb
