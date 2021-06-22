# 準備
* 兩台虛擬機  
  * Server端 192.168.56.102  
  * Client端 192.168.56.106  

* Client端要安裝並啟動zabbix-agent  
```
yum install zabbix-agent  
systemctl start zabbix-agent  
systemctl enable zabbix-agent  
```
* 修改Client端 /etc/zabbix/zabbix_agentd.conf  
>修改Server,ServerActive,Hostname  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-w_get-%E5%AE%A2%E6%88%B6%E7%AB%AFagentd.conf-1.JPG)  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-w_get-%E5%AE%A2%E6%88%B6%E7%AB%AFagentd.conf-2.JPG)  
* 重新啟動  
```
systemctl restart zabbix-agent  
```

## zabbix_get 
# client端 
* 修改client端的/etc/zabbix/zabbix_agentd.conf  
> 修改UserParameter  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-w_get-%E5%AE%A2%E6%88%B6%E7%AB%AFagentd.conf-3.JPG)  
* 重新啟動  
```
systemctl restart zabbix-agent  
```
# Server端  
* 安裝zabbix-get  
```
yum install zabbix-get  
```
* 測試Client端  
```
zabbix_get -s 192.168.56.106 -p 10050 -k "check_users"  
```
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-zabbix-get%E6%B8%AC%E8%A9%A6Client.JPG)  

* 回到zabbix網站介面  
  * 點選Configuration/Hosts/items  
  * 點選右上角的Create item  
     * Name=隨意的名稱  
     * Key=關鍵詞 check_users  
     * Update interval=刷新時間  
     * Application=分類  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-add%20item.JPG)  


## 這樣就可以回到host的item查看新的監控項目了!!  



