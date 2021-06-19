#下載zabbix教學  
https://www.zabbix.com/download?zabbix=4.0&os_distribution=centos&os_version=7&db=mysql&ws=apache  

1.    
#要下載並啟動mariadb  不然步驟c無法達成
yum install -y mariadb-server
systemctl start mariadb 
 
#設定mysql密碼  
mysql_secure_installation  

#設定密碼 1234  


2.  
#到步驟c mysql -uroot -p
#輸入1234
#password可設定為zabbix
#到步驟e Europe/Riga 改成Asia/Taipei