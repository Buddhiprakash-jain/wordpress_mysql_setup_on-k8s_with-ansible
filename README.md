# Wordpress_Mysql_Setup_on-K8s_with-Ansible

##WHAT TO DO FOR RUNNING THE SCRIPT->
## Download above given folder "wordpress_mysql_setup_on-k8s_with-ansible" in your vm and read following steps given below and perform according to it

1. Change in ansible conf(/etc/ansible/ansible.cfg) file in your vm "inventory='your inventory folder'"
2. Change "roles-path='path of your role'" in ansible conf file that is /etc/ansible/ansible.cfg
3. Change "remote_user='ec2-user'" in ansible conf file that is /etc/ansible/ansible.cfg
4. Change "ansible_private_key='path of your key" in ansible conf file that is /etc/ansible/ansible.cfg
5. Change permission of your private key by run cmd in bash shell "chmod 400 'key name'"
6. For dyanamic inventory run following commands in bash shell
 - export AWS_ACCESS_KEY_ID='access-key-id'
 - export AWS_SECRET_ACCESS_KEY='secret-access-key'
 - export AWS_REGION='region name'
7. Make sure your master instances name is "#master"
8. Make sure your worker1 instances name is "#worker1"
9. Make sure your worker1 instances name is "#worker2"
10. 💥Important Point:
11.    - In role "
