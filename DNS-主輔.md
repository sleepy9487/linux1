### 延續 DNS自定義域  
##  準備
* 準備兩台虛擬機設為主輔DNS  
  * 主DNS(DNS自定義域)  IP : 192.168.56.105  
  * 輔DNS              IP : 192.168.56.106  
  
# 1.  
* 輔DNS下載bind  
```
yum install bind  
```
# 2.  
* 修改輔DNS /etc/named.conf  
> 新增masterfile-format text;  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-%E4%B8%BB%E8%BC%94-%E8%BC%94DNS-named.conf.JPG)  

# 3.  
* 修改主DNS /etc/named.conf  
>加入 allow-transfer also-notify允許輔DNS存取  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-%E4%B8%BB%E8%BC%94-%E4%B8%BBDNS-named.conf.JPG)  

# 4.  
* 在輔DNS /etc/named.rfc1912.zones新增zone b.com  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-%E4%B8%BB%E8%BC%94-%E8%BC%94DNS-rfc1912.JPG)

# 5.  
* 檢查/var/named/slaves檢查主DNS的檔案有沒有存取到輔DNS  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-%E4%B8%BB%E8%BC%94-slaves%E6%89%BE%E5%88%B0%E6%AA%94%E6%A1%88.JPG)

# 6.  
* 主,輔DNS都重啟服務  
```
systemctl restart named
```
