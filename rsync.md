## 安裝啟動rsync
*準備兩台虛擬機  
  * 主rsync IP 192.168.56.105  
  * 副rsync IP 192.168.56.106  

# (兩邊)  
* 安裝rsync  
```
yum install rsync  
```
* 啟動rsync  
```
systemctl start rsyncd  
```
* 檢查rsync server有無正常運作  
```
netstat -tunlp | grep 873  
```
# 主rsync  
* 修改 /etc/rsyncd.conf  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/rsync-rsyncd.conf)  
* 新增一個 backup資料夾  
  * 新增一個 rsync.passwd  
  * 新增 vuser1密碼  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/rsync-backup.JPG)      
* 新增一個test資料夾  
  * 新增a~e.txt (用touch)  
```
touch {a..e}.txt  
```
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/rsync-test.JPG)  

* 使用rsync指令將主server的檔案同步到副server
```
rsync -avzh /test/ vuser1@192.168.56.106::mod1
```
# 自動登入
* 在副rsync 利用步驟2 在/back製作一個rsync.passwd
* 使用指令(免密碼)
```
rsync -avzh /test/ vuser1@192.168.56.106::mod1 --password-file=rsync.passwd
```

# 註:不知道為何在步驟4的時候 出現錯誤找不到mod1
