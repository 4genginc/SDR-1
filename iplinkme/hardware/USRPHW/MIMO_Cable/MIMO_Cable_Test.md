# MIMO Cable Test

###### 0x01 --- Intro:

MIMO cable is used to connect two USRP N2xx. Its length is 0.5 meter. (Not fit USRP1 and USRP E100)。

###### 0x02 --- 使用USRP N2XX MIMO电缆测试

* 1.	用 MIMO 电缆将两台 USRP N210 连起来在其中的一台 USRP N210 用网线与电脑连起来。如 ``图-1`` （注意两台 USRP N210 的 ip 不能设为一样）

![MIMO Cable Test 1](https://s3.amazonaws.com/rfagora/image/img/MIMO_Cable_Test/MIMO_Cable_Test01.png)

图-1

* 2.	给两台USRPN210通电后，在root用户下终端输入下面命令：
`uhd_find_devices`
出现``图-2``表示MIMO电缆好使。

![MIMO Cable Test 2](https://s3.amazonaws.com/rfagora/image/img/MIMO_Cable_Test/MIMO_Cable_Test02.png)

图-2

* 3.	修改USRP N210设备IP修改命令如下：

```
$cd /usr/local/lib/uhd/utils
$sudo ./usrp_burn_mb_eeprom --key=ip-addr --val=192.168.10.2
$sudo ./usrp_burn_mb_eeprom --key=ip-addr --val=192.168.10.3
```

###### 0x03 --- 使用USRP2 MIMO电缆测试

[USRP2 MIMO Cable Test](https://s3.amazonaws.com/rfagora/sooof/software/Test/MIMO_Cable_Test/MIMO_Cable.tar.gz)

```bash]
├── master
│   ├── txrx.bin
│   └── u2_rev3.bin
├── readme
├── slave
│   ├── txrx_slave.bin
│   └── u2_rev3_slave.bin
└── u2_flash_tool
2 directories, 6 files
```

将两个USRP2用mimo cable相连，master插上网线。
* 1.首先将fpga和firmware刷入SD卡

*master:命令如下:*

```Bash
/share/u2_flash_tool  --dev=/dev/sdb -t fpga /root/mimo/master/u2_rev3.bin -w
/share/u2_flash_tool  --dev=/dev/sdb -t s/w /root/mimo/master/txrx.bin -w
```

*slave:命令如下:*

```Bash
/share/u2_flash_tool  --dev=/dev/sdb -t fpga /root/mimo/slave/u2_rev3_slave.bin -w
/share/u2_flash_tool  --dev=/dev/sdb -t s/w /root/mimo/slave/txrx_slave.bin -w
```

* 2.将SD卡插入，先给slave加电,slave F灯亮，再给master加电,slave B D F灯亮。
