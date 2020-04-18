

在build_android.sh中查找“make_qt_system”
```
314572800
修改为
13958643712
```

emmc
```
1 on
2 off
3 on
```

扩展root分区
```
setenv fastboot "flash=mmc,2:uboot:2nd:0x200,0x78000;flash=mmc,2:2ndboot:2nd:0x200,0x4000;flash=mmc,2:bootloader:boot:0x8000,0x70000;flash=mmc,2:boot:ext4:0x00100000,0x04000000;flash=mmc,2:system:ext4:0x04100000,0x340000000;"
saveenv
reset
```

```
sdfuse flashall
setenv bootsystem qt
setenv lcdtype 4.3
saveenv
reset
```

进入串口终端后
```
df -h
```

