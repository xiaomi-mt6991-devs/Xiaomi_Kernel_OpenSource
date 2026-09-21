# SPDX-License-Identifier: GPL-2.0

# The link order is important here. ufshcd-core must initialize
# before vendor drivers.
obj-$(CONFIG_SCSI_UFSHCD)	+= core/ host/

# --- merged from MiCode MTK_kernel_device_modules bsp-dali-v-oss ---
obj-$(CONFIG_SCSI_UFS_MEDIATEK_DBG) += ufs-mediatek-dbg.o
