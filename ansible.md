#準備三台虛擬機  
#主ansible 192.168.56.102  
#被監控端1 192.168.56.106  
#被監控端2 192.168.56.102    
#安裝ansible  
yum install ansible  

#製作一個test-ansible資料夾作為後續example存取  
#playbook的使用方法  
ansible-playbook playbook.yml  
配置server檔  

##1.    
#Example1  用ansible安裝.啟動httpd等  
#複製httpd.conf到example1  
cp /etc/httpd/conf/httpd.conf /home/user/text-ansible/example1  

#設定playbook.yml  
gedit playbook.yml  

##2.  
#project2 用ansible安裝 httpd跟ftp  
#設定playbook.yml  
#執行  

##3.  
#project3 playbook.yml的app1,2引用var_public.yml的wget跟gedit安裝  
#設定playbook.yml  
#執行  

##4.  
