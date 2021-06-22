## 首頁細項
* 首頁的Configuration/Hosts可以看監視的主機  
* item=細項 比如記憶體 CPU等  
* Graphs=圖形化介面  
# Create host  
* host name=取名  
* groups=分類  
* IP=要監視的主機IP  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-add%20host%E4%BB%8B%E9%9D%A2.JPG)  

* 切換到templates  
  * Template為預設的監視模板  
  * 我們實驗都是用linux +windows  
    所以採用template OS Linux  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-add%20host-template%E4%BB%8B%E9%9D%A2.JPG)  

# 新增Groups  
到Configuration/Host groups 點擊右上角Create Host Group  


# 圖形化監控  
* 比較正統的監控方式是點選moniotring的graph  
* 去點選要監看的Group,item跟時間範圍  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/zabbix-monitoring.JPG)  
