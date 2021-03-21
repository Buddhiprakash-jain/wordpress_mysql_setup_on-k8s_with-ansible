# Wordpress_Mysql_Setup_on-K8s_with-Ansible

##WHAT TO DO FOR RUNNING THE SCRIPT->
## For Launching instance you can run instance_master,yml,instance_worker1.yml,instance_worker2.yml and do changes in file according to your requirement.
## Download above given folder "wordpress_mysql_setup_on-k8s_with-ansible" in your vm and read following steps given below and perform according to it.

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
     - In role "k8s_setup_wordpress_mysql" in file (files/k8s_configmap_deploy.yml) you can change environment variables values.
     - In my case values are:-
           - mysql_password: redhat
           - mysql_name: wordpress_database
           - mysql_user: buddhi
           - mysql_userpassword: prakash
      - you need to change at place of "redhat" , "wordpress_database" , "buddhi" , "prakash" your own custom values otherwise u can use same.
11. For Accessing Wordpress use "Master instance public ip with service port number  Format: master_public_ip:svc port number" in browser.
    - for service port number use command "kubectl get svc" in your master node.
12. 💥💥Another Important Point:
      - For connecting mysql_database to the wordpress:-
        Give:
       - Database name: <Give your database name that u r use in "k8s_setup_wordpress_mysql/files/k8s_configmap_deploy.yml" file otherwise use "wordpress_database">
       - username: <Give your username that u r use in "k8s_setup_wordpress_mysql/files/k8s_configmap_deploy.yml" file otherwise use "buddhi">
       - password: <Give your password that u r use in "k8s_setup_wordpress_mysql/files/k8s_configmap_deploy.yml" file otherwise use "prakash">
       - <Give your localhost name "ip of the mysql pod">
23.   - For mysql pod ip use command "kubectl describe pods <name of mysql pod>"
## After reading above instructions for deploying the wordpress_mysql setup use "ansible-playbook setup.yml" command. 
