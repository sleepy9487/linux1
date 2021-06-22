## 自動化安裝
* 準備兩台虛擬機  
  * 服務端        內部網路(a)+NAT+Host  
  * 客戶端(新建)  內部網路(a)  

# 服務端   
* 安裝tftp dhcp vsftpd 
 ```
yum install tftp-server dhcp  vsftpd  
```
* 設定DHCP server(圖)  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/pxe-dhcp.JPG)    
* ifconfig 將enp0s9設定為192.168.100.254    
* 修改tftp  
```
cd /use/lib/systemd/system  
gedit tftp.service  
```
* 修改路徑到 /tftpboot(圖)  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/pxe%20tftpserver.JPG)  
```
cp tftp.service /root/tftp.service.orig  
```
* 建立tftpboot  
```
mkdir /tftpboot  
```  
* 將syslinux的必要檔案複製到tftpboot  
```
cp pxelinux.0 menu.c32 nendisk mboot.c32 chain.c32 /tftpboot/  
```
* 修改權限  
```
chmod 755 /tftpboot  
```
* 用winscp將centos.iso複製到/mnt  
* mount centos.iso(代稱)取得 images裏頭的內核文件等等  
```
mount centos.iso /mnt  
```
* 將mount完的centos.iso複製到pub  
```
cp -R /mnt/* /var/ftp/pub  
```
* 將pxeboot裏頭的vmlinuz與initrd.img複製到/tftpboot/netboot  
```
cp vmlinuz initrd.img /tftpnoot/netboot/  
``` 
* 將ks.cfg複製到pub目錄下 修改權限 
```
cp /root/anaconda-ks.cfg /var/ftp/pub/ks.cfg  
chomd 644 /var/ftp/pub/ks.cfg  
```
*  編寫PXE server的開機選單  
```
gedit /tftpboot/pxelinux.cfg/default(圖)  
```
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/pxe-%E9%96%8B%E6%A9%9F.JPG)
* 重啟服務  
```
systemctl restart dhcpd tftp vsftpd  
```
>註:關閉防火牆與selinux 
>註2(超重要):系統開機順序記得網路>硬碟 不然一進去就強制找硬碟 
