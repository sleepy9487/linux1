準備兩台虛擬機  
Server端與Client端  

Server端  
1.  
#安裝bind9  
yum install bind  
2.  
#設定 /etc/named.conf檔  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-named.conf-1.JPG)  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-named.conf-2.JPG)  
#改listen port為any ->server端任何IP都能用  
#改allow-query為any ->讓所有主機都能訪問
#include -> 包含xxx檔案 很重要 如果要在named.rfc1912.zones設定zone 沒在此include 無論如何都得不到結果    
3.  
#啟動DNS server
systemctl start named  

註:每次改寫DNS相關檔案可用 named-checkconf檢查有何錯誤


