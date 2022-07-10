# Gigabyte-Z490i-Intel-10900k-6600XT
在基于技嘉Z490I AORUS ULTRA、Intel 10700k的平台上安装 MacOS Monterey
- 更新到 OC 0.8.2，支持 Mac OS Monterey
- 驱动更新到最新版本理论支持macOS Ventura（尚未安装测试）
- 网卡采用DW1560+转接板方案

## 整机硬件

- 处理器：Intel 10900k
- 主板：Gigabyte Z490I AORUS ULTRA
- 内存：美商海盗船 DDR4 3200 16GB * 2
- 硬盘：WD_Blue™ SN570 1TB NVMe™ SSD
- 显卡：ROG STRIX RX6600XT O8G GAMING
- 网卡：DW1560AC + M.2网卡转接板

## 功能

- 打开节能五项
- Wifi、蓝牙正常，支持隔空投送
- 音频正常
- 支持睡眠唤醒
- 定制USB接口（[黑苹果为什么要定制USB？黑苹果定制USB教程](https://www.bilibili.com/video/BV1aV411e7Vo?spm_id_from=333.337.search-card.all.click&vd_source=6d8e5045a21f15a1f8efb37046291a2e)）
- 板载Intel无线网卡和蓝牙模块可以使用（不完美，[黑苹果intel网卡驱动方法](https://www.bilibili.com/video/av287832297/?vd_source=6d8e5045a21f15a1f8efb37046291a2e)）

## BIOS设置

- 关闭『快速启动』
- 关闭『CSM』
- 集成显卡『开启』（而非自动）
- 其它默认 
## 安装步骤(懒人版安装)

- 制作启动盘
  - 微信搜索`黑果小冰的部落阁`并关注，菜单选择“安装镜像”，选择需要的版本，滑到推文最后，点击'喜欢作者'对作者进行打赏（最低是2CNY），就能获得下载链接；
  - 准备一个16G U盘（也可用移动硬盘或者移动固态，安装速度更快，烧录启动盘会格式化U盘,注意备份好自己的文件）；
  - 使用`balenaEtcher`软件(支持Windows和mac平台)，选中下载好的镜像和做启动盘的U盘，写入启动盘；
- 替换EFI
  - Windows下安装`DiskGenius`,找到U盘中放置OC的分区，强制删除所有文件，并将我的EFI解压后拖拽拷贝进去；
  - 至此安装U盘制作完成

## 安装步骤(纯净版安装)

为保证系统原始性，以下操作在白苹果上进行。

- 从 AppStore 下载 MacOS
- 准备一个 16GB U盘
- 格式化U盘
  - 插入U盘到白苹果
  - 打到『磁盘工具』-- 左上方『显示』--『显示所有设备』-- 选择你的U盘 -- 点击『抹掉』
    - 名称：USB
    - 格式：Mac OS扩展（日志式）
    - 方案：GUID分区图
    - 点击右下方『抹掉』，最后点击『完成』
- 将系统镜像写入U盘
  - 终端执行 `sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/USB`
  - 输入密码，并回车
  - 提示将擦除U盘设备，是否继续。输入`y`并回车继续
  - 等待U盘写入完成
- 添加EFI到U盘
  - 打开 [OpenCore Configurator](https://mackie100projects.altervista.org/) 软件
  - 菜单栏『工具』 -- 『挂载EFI』
  - 在EFI分区中，找到U盘并点击『挂载分区』--『打开分区』
  - 将本项目中 **EFI** 目录拷贝至新打开的 **EFI分区中**
  - 至此安装U盘制作完成
