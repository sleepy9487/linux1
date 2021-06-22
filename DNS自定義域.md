## 設定正解域  
1.  
* 在/etc/named.rfc1912.zones 加上這段  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-named.rfc1912.zones.JPG)  
* 上到下代表的涵義為  
  * zone的名稱  
  * 是甚麼類型  
  * 檔案在哪裡(預設在/var/named/)  
  * 允不允許上傳更改  
2.  
* 在/var/named/新增一個b.com.zone的檔案  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-b.com.zone%E9%85%8D%E7%BD%AE.JPG)  
* 上到下代表的涵義 
  * 管理員信箱 EX:xxxx.gmail.com   
  * 序列號  
  * 重新刷新時間  
  * 重試時間(要小於刷新時間)  
  * 過期時間(輔助DNS儲存有效資料的時間)  
  * 其他DNS server抓取該資料的時間  
  * NS 指定操作的DNS server名稱  
  * b.com的IP為192.168.56.105  
  * www.b.com的IP為192.168.56.200  
  * CNAME為別名 ftp為www的別名 ftp.b.com的IP為192.168.56.200
3.  
* 重新啟動named
* Client端查詢
EX:  
```
nslookup www.b.com IP  
```
## 自定義反解域  
# 1.  
* 在/etc/named.rfc1912.zones新增zone  
>註 : 反定義命名 IP相反+.in-addr.arpa  

2.  
* 在原本正解域 b.com.zone進行修改  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-%E5%8F%8D%E8%A7%A3%E5%9F%9F.JPG)  
# 3.    
* 在/var/named/新增56.168.192-in-addr.arpa.zone  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/DNS-%E5%8F%8D%E8%A7%A3%E5%9F%9F-2.JPG)  
# 4.  
* 重新啟動服務  
```
systemctl restart named
```
# 註:檢查自定義域有沒有問題  
* named-checkzone +zone +檔案位址  
>EX : named-check b.com /var/named/b.com.zone  
