# test-ansible


#execuite change pass - from remote host root has password assigned
ansible-playbook changepass.yaml --extra-vars "newpassword=Password@123 user=svc-test" --ask-become-pass


#Execute to specific task '-K' is short for --ask-become-pass
ansible-playbook launch-app.yaml --start-at-task 'start apache2' -K

#sample Add-Hoc Commands
##ping
ansible web-server-1 -m ping
##create dir
ansible web-server-1 -m file -a "path=/home/krvnryssl/dir.test state=directory mode=700"
##create file
ansible web-server-1 -m file -a "path=/home/krvnryssl/file.test state=touch mode=700"
##delete file
ansible web-server-1 -m file -a "path=/home/krvnryssl/file.test state=absent"
## other Add-Hoc command, copy file, installing package, stop\start services:
## check status of services
ansible webservers -m command -a "systemctl status apache2" -K -b=true
#creating user:
 ansible webservers -m user -a "name=test-user home=/home/test-user shell=/bin/bash state=present" -b=true -K
