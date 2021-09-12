# RFX900 / RFX1800 


### 0X01 --- RFX900：

Include RFX900 board、SMA-Bulkhead Cable x 2、VERT900 Antenna x 2。

###### 0X01 --- ：

* RFX900 board

* SMA-Bulkhead Cable x 2

* VERT900 Antenna x 2

###### 0X01 --- ：

* Overview picture：

![Overview 01](https://s3.amazonaws.com/rfagora/image/img/RFX/RFX900_00001.JPG)


### 0X02 --- RFX1800：

VERT900 Antenna x 2

Include RFX1800 board、SMA-Bulkhead Cable x 2、VERT900 Antenna x 2.

###### 0X01 --- by **[openbts_v3.09_52M.iso](https://s3.cn-north-1.amazonaws.com.cn/microembedded/system_mirrors/openbts_v3.09_52M.iso)** 、**[Openbts_v2.09_64.iso](https://s3.cn-north-1.amazonaws.com.cn/microembedded/system_mirrors/Openbts_v2.09_64.iso)。** same way to rewrite daughter board。

* 1> download above ISO file

* 2> make DVD or [make live USB](<../../../../other/linux_development/Tools/USB/make_usb_boot.md>).

* 3> start computer by DVD or live USB.

* 4> change rfx900 --> rfx1800 （re-write EEPROM， rfx900 --> rfx1800）

```bash
  #/usr/local/src/gnuradio-3.3.0/usrp/host/apps/burn-db-eeprom -t rfx1800_mimo_b -A –f
```
