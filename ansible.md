#準備三台虛擬機  
#主ansible 192.168.56.102  
#被監控端1 192.168.56.106  
#被監控端2 192.168.56.102    
#安裝ansible  
yum install ansible  

#製作一個tes(x)t-ansible資料夾作為後續example存取  
#playbook的使用方法  
ansible-playbook playbook.yml  
配置server檔  

##1.    
用ansible安裝.啟動httpd等  
#複製httpd.conf到example1  
cp /etc/httpd/conf/httpd.conf /home/user/text-ansible/example1  

#設定playbook.yml  
gedit playbook.yml  

##2.利用變數  
#project playbook.yml的app1,2引用var_public.yml的wget跟gedit安裝  
#設定playbook.yml  
#執行  

製作j2可以客製化不同客戶端的安裝需求  
