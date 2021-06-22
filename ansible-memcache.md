* 利用memcached 透過客戶端記憶體做配置
* memcached是將資料存放在記憶體,讓速度加快許多

## 實驗 
*利用ansibled指令透過memcache.j2抓取各裝置的記憶體  
* memcached.j2  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/ansible-memcache-j2.JPG)  
* playbook.yml  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/ansible-memcache-playbook.yml)  
* 結果  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/ansible-memcache-%E7%B5%90%E6%9E%9C.JPG)  