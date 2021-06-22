# playbook.yml範本   
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/ansible-%E5%96%AE%E9%A0%85or%E5%BF%BD%E7%95%A5%E7%AF%84%E6%9C%AC.JPG)
* 執行單項任務   
```
ansible-playbook playbook.yml -t "install memcached" (任務名稱)
```
* 結果  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/ansible-%E5%9F%B7%E8%A1%8C%E5%96%AE%E9%A0%85%E4%BB%BB%E5%8B%99.JPG)
* 忽略某項任務
```
ansible-playbook playbook.yml --skip-tags "configured_memcache" 
```  
* 結果  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/ansible-%E5%BF%BD%E7%95%A5%E6%9F%90%E9%A0%85%E4%BB%BB%E5%8B%99.JPG)
