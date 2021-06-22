## 安裝啟動docker
# 1.  
* docker安裝與啟動  
```
yum install docker  
systemctl start docker  
```
# 2.  
* docker下載image (centos7 or httpd)  
```
docker pull centos:7   
docker pull httpd  
```
* 檢查有無下載成功  
```
docker images  
```
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/docker%20image.JPG)  
# 3.  
* docker啟動image  
```
docker run -itd centos:7 /bin/bash  
docker run -itd -p 8082:80 httpd  
```
>註:虛擬機預設httpd的port是8080 用docker運行8080port的話 可能會因先前httpd佔用而無法執行   
# 4.
* 點入httpd的成功畫面  
>http://IP:8082  
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/docker%20httpd.JPG)   
* 在未關閉docker的情況下離開docker  
>按下control鍵+P+Q  

* 進去正執行的docker  
```
docker exec -it containerID bash  
```
* 終止docker(在docker介面)  
```
exit  
```
## 刪除、複製與上傳
# 刪除docker images and container  
```
docker rmi ImageID  
docker rmi 要移除的軟體+版本  
docker rm containerID  
```
>註 : 如果image裡還有container的行程運行 得先把container刪除才能移除image  

* 一次刪除所有images and container  
```
docker rmi -f $(docker images -a -q)  
docker rm -f $(docker ps -a -q)  
```
# 複製container並重新命名  
* 利用image裡的container複製一個image出來並重新命名  
* 確認運行中的container 
 ```
docker ps  
```
* 複製container並重新命名  
```
docker commit /new_name/new_server:new_tag  
```
>new_name=帳號  
* 確認有無成功  
```
docker images  
```
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/docker%20commit.JPG)  

# 上傳docker  
* 將image 上傳到自己的docker裡面  
* 登入docker帳號  
```
docker login  
```
* 上傳  
```
docker push new_name/new_server:new_tag  
```
![image](https://github.com/sleepy9487/linux1/blob/master/linux%20images/docker%20push%202.JPG)  
>註: push的上傳格式其實是 dockerhub/new_name/new_server:new_tag  
只是docker hub可以省略  
