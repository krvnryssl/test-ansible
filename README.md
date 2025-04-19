# test-ansible


#execuite change pass - from remote host root has password assigned
ansible-playbook changepass.yaml --extra-vars "newpassword=Password@123 user=svc-test" --ask-become-pass

