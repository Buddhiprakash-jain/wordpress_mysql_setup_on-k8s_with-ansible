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
7. Make sure your master instances name is "master" otherwise u can change inside the "setup.yml" file.
8. Make sure your worker1 instances name is "#worker1" otherwise u can change inside the "setup.yml" file.
9. Make sure your worker1 instances name is "#worker2" otherwise u can change inside the "setup.yml" file.
10. 💥Important Point:
11.    - In role "k8s_setup_wordpress_mysql" in file (files/k8s_configmap_deploy.yml) you can change environment variables values.
12.    - In my case values are:-
13.       - mysql_password: redhat
14.       - mysql_name: wordpress_database
15.       - mysql_user: buddhi
16.       - mysql_userpassword: prakash
17.    - you need to change at place of "redhat" , "wordpress_database" , "buddhi" , "prakash" your own custom values otherwise u can use same.
18.
