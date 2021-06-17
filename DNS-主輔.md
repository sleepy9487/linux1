#延續 DNS自定義域  
  
準備兩台虛擬機設為主輔DNS  
主DNS(DNS自定義域)  IP : 192.168.56.105  
輔DNS              IP : 192.168.56.106  
  
1.  
#輔DNS下載bind  
yum install bind  
2.  
#修改輔DNS /etc/named.conf  
#新增masterfile-format text;  

3.  
#修改主DNS /etc/named.conf  
#加入 allow-transfer also-notify允許輔DNS存取  

4.  
#在輔DNS /etc/named.rfc1912.zones新增zone b.com  

5.  
#檢查/var/named/slaves檢查主DNS的檔案有沒有存取到輔DNS  

6.  
#主,輔DNS都重啟服務  
systemctl restart named
