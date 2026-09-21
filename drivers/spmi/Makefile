# SPDX-License-Identifier: GPL-2.0-only
#
# Makefile for kernel SPMI framework.
#
obj-$(CONFIG_SPMI)	+= spmi.o

obj-$(CONFIG_SPMI_HISI3670)	+= hisi-spmi-controller.o
obj-$(CONFIG_SPMI_MSM_PMIC_ARB)	+= spmi-pmic-arb.o
obj-$(CONFIG_SPMI_MTK_PMIF)	+= spmi-mtk-pmif.o

# --- merged from MiCode MTK_kernel_device_modules bsp-dali-v-oss ---
obj-$(CONFIG_SPMI_MTK_PMIF)	+= spmi-mtk-pmif.o spmi-mtk-mpu.o
