
# Deploy by K8s

kubectl apply -f jenkins-home-pvc.yaml
kubectl apply -f jenkins-deployment.yaml
kubectl apply -f jenkins-service.yaml


# Setup
1. Forward a port in local to setup
kubecrl get pods 

kubectl port-forward jenkins-545456974-r9858 8080:8080

open http://127.0.0.1:8080/ in your favirous browser.

2. Setup

docker logs jenkins-545456974-r9858

get the password for jenkins installation, example: 825d7f8e4b934cefa857a78b6b720bfa 

paste the password and continue.


3. Set an admin account


4. Done


# Config
1. link with openldap
Goto System => Global security => LDAP

Server: ldap://openldap:389
rootDN: dc=gkewang,dc=cn
User search base: **BLANK**
User search filter: cn={0}
Group search base: **BLANK**
Group search filter: **BLANK**
Group membership:  Search for LDAP groups containing user	
  Group membership filter	: **BLANK**
Manager DN	: cn=admin,dc=gkewang,dc=cn
Manager Password	: PASSWORD
Display Name LDAP attribute	: displayName
Email Address LDAP attribute	: mail


Then , click test .

验证成功后，退出admin账户，使用ldap中的admin用户，如 luochunhui@greenlandfinancial.com 登录。


2. Enable Matrix permission.

3. Setup github, link libs with giokuo
3.1 Create an "secret text" credential named gikoluo-github , value 172a80146f60cac63fc7af9c37b0730af92426c9
3.2 Create an "username with password" named gikoluo-github-pwd, 用户名： wo@luochunhui.com , 密码: password。
3.2 goto http://127.0.0.1:8080/configure , add Github server: name: gikoluo-github, 凭据:  gikoluo-github
3.3 test and save.
3.4 Global Pipeline Libraries, add a lib in github, Project Repository: lifecycle-pipeline . save.



4. Link 

