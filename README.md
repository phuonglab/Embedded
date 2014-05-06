Embedded
========

Note for embedded linux

+Edit permittin in buildroot : change in buildroot\target\
+Option for build kernel http://kernel.xc.net/html/linux-2.6.0-test3/sparc64/



*Uboot: add new cmd
+ I2C
*Uboot add eth:
change config:
#define CONFIG_SMC911X
#define CONFIG_SMC911X_16_BIT
#define CONFIG_SMC911X_BASE		0x44000000

add :
int board_eth_init(bd_t *bis)
{
	int rc = 0;
#ifdef CONFIG_SMC911X
	rc = smc911x_initialize(0, CONFIG_SMC911X_BASE);
#endif
	return rc;
}

or 
int cpu_eth_init(bd_t *bis)
{
	int ret = -ENODEV;
#ifdef CONFIG_SMC911X
	ret = smc911x_initialize(0, CONFIG_SMC911X_BASE);
#endif
	return ret;
}


###############################################
when config :set up io before write/read data


############ output console to lcd  #############
  + tty0::respawn:-/bin/sh

 *(volatile uint32_t *)(0x3fffff80) = 0x00000001;
    dummy_buf_32b = *(volatile uint32_t *)(0x3fffff80);
    
    http://mikrocontroller.bplaced.net/wordpress/?page_id=621
    
###########################################
Compare tool:Araxis Merge

#########################################
Image tool : GIMP tool


