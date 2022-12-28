# 1. Preparation
1. install ansible https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
2. install FedTree https://github.com/Xtra-Computing/FedTree
3. set ssh connection for ansible clients https://docs.ansible.com/ansible/latest/inventory_guide/connection_details.html
    * set alias (server / client1 ...) in /etc/hosts
4. set ssh connection from fedtree clients to fedtree server

# 2. Ansible Setting
1. setting ansible hosts:

      vi /etc/ansible/hosts
   
       [fedtree_server]
       server1 ansible_ssh_host=<ip0>

       [fedtree_client]
       client1 ansible_ssh_host=<ip1>
       client2 ansible_ssh_host=<ip2>
       client3 ansible_ssh_host=<ip3>
2. set host_vars machine_index for each client
  
      vi /etc/ansible/group_vars/client1
       
       machine_index: 0
  
      vi /etc/ansible/group_vars/client2
          
       machine_index: 1
      
      vi /etc/ansible/group_vars/client3
       
       machine_index: 2

# 3. Start Training using ansible
   * after dataset is ready and both fedtree conf and start_training.yml are modified, run following cmd in terminal:
      
      ansible-playbook start_training.yml
            
