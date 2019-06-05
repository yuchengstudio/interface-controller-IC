# 1.USB2514
<br/>官网链接：https://www.microchip.com/wwwproducts/en/USB2514B
```
备注：可以在官网找到原理图检查及layout设计注意事项
1.	配置管脚CFG_SEL0/1, NON_REM0/1不能悬空，要外部接下拉。
    CFG_SEL0/1: 00 - 默认配置。
    NON_REM1
    NON_REM[1:0] = 00 : all ports are removable
    NON_REM[1:0] = 01 : port 1 is non-removable
    NON_REM[1:0] = 10 : ports 1 and 2 are non-removable
    NON_REM[1:0] = 11 : when available, ports 1, 2, and 3 are non-removable
    
2.	Test管脚接地。

3.	没用的usb端口3/4可以直接把D+/D-上拉到3.3v。
    USBDP_DN & USBDM_DN

4.	PRTPWRx/OCSx管脚如果不用的话可以悬空，不需要接地。一般最好接端口保护器件，比如mic2026。

5.	如果上行口要支持热插拔的话，vbus_det的5v要接到上行口的vbus上面。

6.	Vdd3.3v和vdda3.3v最好能够分开。

7.	请确认接地的pad设置为pin number 0是工具可以接受的。

8.	请确保其他部分的设计符合usb规范。
```
<br/>datasheet: https://github.com/yuchengstudio/interface-controller-IC/blob/master/USB_HUB/reference/USB251xB_Bi.pdf
<br/>硬件原理检查：https://github.com/yuchengstudio/interface-controller-IC/blob/master/USB_HUB/reference/Schematic%20Checklist%20USB2514B%20QFN%20Rev%20A.pdf
