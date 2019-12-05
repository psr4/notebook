# 神州G6笔记本(gtx960)装deepin无法正常关机的解决方法

### 1.安装系统后运行以下命令
bumblebee会自动安装nvidia驱动
```shell
sudo apt-get install bumblebee-nvidia primus 
```

### 2.开机卡logo
我的设备出现安装成功后关机正常了 但是出现开机卡logo
##### 临时解决发方法
解决方法是 开机进入系统选择页面 按E
在 quiet后面增加 acpi_osi=! acpi="windows 2009"
```shell
linux	/boot/vmlinuz-4.15.0-30deepin-generic root=UUID=xxxx ro  splash quiet acpi_osi=! acpi="windows 2009" DEEPIN_GFXMODE=$DEEPIN_GFXMODE
```
##### 永久解决方法
开机后 打开终端 运行
```shell
sudo vim /etc/default/grub
```
找到第一个 quiet 同样在后面增加 acpi_osi=! acpi='windows 2009'

