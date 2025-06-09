# NAMRATHA-7
wsl -install
    suDo apt install wsl
    sudo apt install wsl
    wsl
    sudo apt upgrade
    sudo apt install ansible -y
    ansible --version
    mkdir ansible_project
    mkdir ansible_project2
    cd ansible_project2
    nano host
    ansible -i host local -m ping
   nano install_nginx.yml
    ansible-playbook-i host install_nginx.yml
    ansible-playbook -i host install_nginx.yml
   nano host
    nano install_nginx.yml
   ansible-playbook -i host install_nginx.yml
    curl http://localhost
    ip addr

    experiment 7 installation 
sudo apt update
sudo apt-get install software-properties-common
sudo apt-add-repostitory --yes--update ppa:ansible/ansible 
sudo apt-get install ansible 
   give yes 
ansible --version 


    - name: Description
  hosts: webservers
  become: true
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present


TASK [Ensure NGINX is running] *************************************************
ok: [localhost]

PLAY RECAP *********************************************************************
localhost                  : ok=3    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

nithya@LAPTOP-097EWO0F:~/nithya$ curl http://localhost
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    html { color-scheme: light dark; }
    body { width: 35em; margin: 0 auto;
           font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>

nithya@LAPTOP-097EWO0F:~/nithya$


Experiment 7 - Using Ansible
1. Update Your System
Open your terminal and run:
sudo apt update
sudo apt upgrade -y
​
2. Install Ansible
Install Ansible using apt:
sudo apt install ansible -y
​
Verify the installation by checking the version:
ansible --version
​
Expected Output Example:

3. Creating an Ansible Inventory
An inventory file lists the hosts you want to manage. For this experiment, you can use the local host.
Create an Inventory File
Open your text editor to create a file called hosts.ini:
gedit hosts.ini
​
Add the following content to define the local host:
[local]
localhost ansible_connection=local
​
Explanation:
[local] is a group name.
localhost is the target host.
ansible_connection=local tells Ansible to execute commands on the local machine without SSH.
3. Save and exit the file.
4. Writing a Basic Ansible Playbook
You will now create a simple playbook that performs two common tasks:
Updating the apt cache
Installing a package (e.g., curl)
5. Create the Playbook File
Open your text editor to create a file called setup.yml:
gedit setup.yml
​
Add the following YAML content:
---
- name: Basic Server Setup
  hosts: local
  become: yes # Use privilege escalation (sudo)
  tasks:
    - name: Update apt cache
      apt:
        update_cache: yes

    - name: Install curl
      apt:
        name: curl
        state: present
​
Explanation:
name: Provides a descriptive name for the play.
hosts: Specifies the group or hosts from the inventory file.
become: yes: Uses sudo to perform tasks that require elevated privileges.
Tasks Section:
Update apt cache: Uses the apt module to update the package cache.
Install curl: Uses the apt module to install the curl package if it isn't already installed.
Save and exit the file.
6. Running the Ansible Playbook
1. Execute the Playbook
In your terminal, run the following command:
sudo ansible-playbook -i hosts.ini setup.yml
​
Explanation:
ansible-playbook: The command to run an Ansible playbook.
i hosts.ini: Specifies the inventory file.
setup.yml: The playbook file you just created.
Expected Output:
An output that details each task. For example, a task summary might show "ok=2 changed=1" (if the apt cache was updated and curl was installed).


   
sudo apt update
sudo apt-get install software-properties-common
sudo apt-add-repostitory --yes--update ppa:ansible/ansible 
sudo apt-get install ansible 
   give yes 
ansible --version 
