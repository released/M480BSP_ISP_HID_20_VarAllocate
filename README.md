# M480BSP_ISP_HID_20_VarAllocate
 M480BSP_ISP_HID_20_VarAllocate

update @ 2021/05/18

1. LDROM : use BSP ISP_HID_20 sample code , with flag in SRAM (without initial) to control update flow

2. APROM : by terminal , digit 1 , will set flag to 0x5A5A , and reboot to LDROM , to start USB ISP flow

- since use below function , to jump to LDROM , either enable boot from LDROM or boot from APROM , both acceptable in ICP config setting

				SYS_UnlockReg();
				
				FMC_SET_LDROM_BOOT();
				
				SYS_ResetCPU();

3. use ISP programming tool (USB) , to programming APROM , project 01 and project 02

4. below is ICP config setting , set boot as LDROM

![image](https://github.com/released/M480BSP_ISP_HID_20_VarAllocate/blob/main/ICP_config.jpg)

5. below is KEIL config setting , to use SRAM last 16 bytes and not init to store data

![image](https://github.com/released/M480BSP_ISP_HID_20_VarAllocate/blob/main/KEIL_config.jpg)

