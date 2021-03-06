# SPDX-License-Identifier: GPL-2.0+
#
# (C) Copyright 2000-2003
# Wolfgang Denk, DENX Software Engineering, wd@denx.de.
#
# Copyright (C) 2012-2017 Altera Corporation <www.altera.com>

obj-y	+= board.o
obj-y	+= clock_manager.o
obj-y	+= misc.o

ifdef CONFIG_TARGET_SOCFPGA_GEN5
obj-y	+= clock_manager_gen5.o
obj-y	+= misc_gen5.o
obj-y	+= reset_manager_gen5.o
obj-y	+= scan_manager.o
obj-y	+= system_manager_gen5.o
obj-y	+= timer.o
obj-y	+= wrap_pll_config.o
obj-y	+= fpga_manager.o
endif

ifdef CONFIG_TARGET_SOCFPGA_ARRIA10
obj-y	+= clock_manager_arria10.o
obj-y	+= misc_arria10.o
obj-y	+= pinmux_arria10.o
obj-y	+= reset_manager_arria10.o
endif

ifdef CONFIG_TARGET_SOCFPGA_STRATIX10
obj-y	+= clock_manager_s10.o
obj-y	+= mailbox_s10.o
obj-y	+= misc_s10.o
obj-y	+= mmu-arm64_s10.o
obj-y	+= psci.o
obj-y	+= exception_handler.o
obj-y	+= reset_manager_s10.o
ifndef CONFIG_SPL_BUILD
obj-y   += rsu.o
obj-y   += rsu_ll_qspi.o
obj-y   += rsu_misc.o
obj-y	+= rsu_s10.o
endif
obj-y	+= system_manager_s10.o
obj-y	+= timer_s10.o
obj-y	+= wrap_pinmux_config_s10.o
obj-y	+= wrap_pll_config_s10.o
obj-$(CONFIG_STRATIX10_FPGA_RECONFIG)	+= smc_fpga_reconfig_s10.o
obj-y	+= smc_registers_s10.o
obj-y	+= lowlevel_init.o
obj-y	+= smc_rsu_s10.o
obj-y	+= smmu_s10.o
obj-y	+= smc_ecc_dbe_s10.o
endif

ifdef CONFIG_TARGET_SOCFPGA_AGILEX
obj-y	+= clock_manager_agilex.o
obj-y	+= exception_handler.o
obj-y	+= lowlevel_init.o
obj-y	+= mailbox_s10.o
obj-y	+= misc_s10.o
obj-y	+= mmu-arm64_s10.o
obj-y	+= reset_manager_s10.o
obj-y	+= smc_registers_s10.o
obj-y	+= smc_rsu_s10.o
obj-y	+= smmu_s10.o
obj-y	+= system_manager_s10.o
obj-y	+= timer_s10.o
obj-y	+= wrap_pinmux_config_s10.o
obj-y	+= wrap_pll_config_s10.o
ifndef CONFIG_SPL_BUILD
obj-y	+= rsu.o
obj-y	+= rsu_ll_qspi.o
obj-y	+= rsu_misc.o
obj-y	+= rsu_s10.o
obj-$(CONFIG_ARMV8_PSCI)	+= psci.o
endif
endif

ifdef CONFIG_SPL_BUILD
ifdef CONFIG_TARGET_SOCFPGA_GEN5
obj-y	+= spl_gen5.o
obj-y	+= freeze_controller.o
obj-y	+= wrap_iocsr_config.o
obj-y	+= wrap_pinmux_config.o
obj-y	+= wrap_sdram_config.o
endif
ifdef CONFIG_TARGET_SOCFPGA_ARRIA10
obj-y	+= spl_a10.o
endif
ifdef CONFIG_TARGET_SOCFPGA_STRATIX10
obj-y	+= firewall.o
obj-y	+= spl_s10.o
obj-y	+= spl_soc64.o
endif
ifdef CONFIG_TARGET_SOCFPGA_AGILEX
obj-y	+= ccu_agilex.o
obj-y	+= firewall.o
obj-y	+= spl_agilex.o
obj-y	+= spl_soc64.o
endif
else
obj-$(CONFIG_SMC_SIP_FPGA_RECONFIG)	+= smc_fpga_reconfig_s10.o
endif

ifdef CONFIG_TARGET_SOCFPGA_GEN5
# QTS-generated config file wrappers
CFLAGS_wrap_iocsr_config.o	+= -I$(srctree)/board/$(BOARDDIR)
CFLAGS_wrap_pinmux_config.o	+= -I$(srctree)/board/$(BOARDDIR)
CFLAGS_wrap_pll_config.o	+= -I$(srctree)/board/$(BOARDDIR)
CFLAGS_wrap_sdram_config.o	+= -I$(srctree)/board/$(BOARDDIR)
endif
