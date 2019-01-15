一．Ubuntu安装

1. 使用Universal-USB-Installer制作安装盘；

2. F12，U盘启动安装。分区如下：

    * swap  8192MB，逻辑分区

    * /    20480MB，逻辑分区

    * /home  剩余，逻辑分区

    * 启动：/ 所在分区

二．BIOS设置

1. 设置BIOS密码

2. boot切换为UEFI，secure boot设置为disable；

3. select an UEFI file as trusted,依次选择：

   HDD0->EFI->ubuntu->grubx64.efi  命名为Grub

4. 启动顺序，将Grub调整到顶端。


重启后将使用ubuntu引导。

 另一种解决方案，将做好的启动盘中EFI文件夹删除再安装。未测试过。

参考方案：
https://blog.csdn.net/kyjl888/article/details/80790687
https://blog.csdn.net/maxadda/article/details/52277804
http://tieba.baidu.com/p/2316824451
https://blog.csdn.net/GJXS2017/article/details/80296267#legacy%E5%90%AF%E5%8A%A8%E6%A8%A1%E5%BC%8F%E4%B8%8B%E5%AE%89%E8%A3%85win10ubuntu%E5%8F%8C%E7%B3%BB%E7%BB%9F
http://tieba.baidu.com/p/5597848278
https://ubuntuforums.org/showthread.php?t=2358003
https://askubuntu.com/questions/627416/acer-aspire-e15-will-not-dual-boot
https://askubuntu.com/questions/870022/how-to-get-grub-boot-option/870074
https://ubuntuforums.org/showthread.php?t=2297947&p=13369742#post13369742