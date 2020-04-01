# 云编译N1 Openwrt固件 Docker
注：本仓库纯属个人根据自己的设备配置使用，未有在任何论坛或者群组发布固件  
使用lean’s lede源代码  
主要集成插件✈️ShadowSocksR Plus+ AirPlay2 Passwall clash openclash koolproxyrPlus+ smartdns AdGuardHome...  
🖥️默认ip已更换为192.168.2.1  
添加N1作为旁路由的防🔥墙规则  iptables -t nat -I POSTROUTING -o eth0 -j MASQUERADE  
📅固件每天凌晨3时自动编译并上传dockerhub仓库  bobotoy/openwrt-aarch64:latest  
20200321  
----解决kpr无法启动的问题，虽然我不用，但不能没有  
20200324  
----lienol插件仓库代码更新，取消删除与lean插件重复代码  
----增加编译完成自动发布RLEASE和微信提醒功能  
20200325  
----精简若干Release文件，保留openwrt-armvirt-64-default-rootfs.tar.gz  
----增加发布：📦 配置.config 容器docker-img  
20200327  
----Fix bugs about N1.yml 精简部分代码  
20200328  
----Release保留每日自动发布的固件不再替换更新    
20200401   
----增加AirPlay2插件编译  
# 食用方法🥢
举例:  
----①.将docker-img-openwrt-aarch64-0317.gz文件上传至N1的/root目录   
----②.导入软路由docker包：  
----gzip -dc docker-img-openwrt-aarch64-0317.gz | docker load  
----或者docker pull bobotoy/openwrt-aarch64:latest（推荐跳过②①直接拉取使用）  
----③运行容器：  
----docker run  -d --restart always --network macnet --ip 192.168.2.1  --privileged bobotoy/openwrt-aarch64:latest /sbin/init  


# 鸣谢 📢
借鉴引用以下大佬代码  
https://github.com/coolsnowwolf/lede  
https://github.com/Lienol/openwrt-package  
https://github.com/fyglinfo/actions-openwrt-passwall  
https://github.com/P3TERX/Actions-OpenWrt   
https://github.com/zorzcc/openwrt-actions  
