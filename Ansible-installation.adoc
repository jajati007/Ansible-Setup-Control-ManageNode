Step 1: Update your system
```
sudo apt update && sudo apt upgrade -y
```
Step 2: Install software dependencies
```
sudo apt install -y software-properties-common
```
Step 3: Add the official Ansible PPA
```
sudo add-apt-repository --yes --update ppa:ansible/ansible
```
Step 4: Install Ansible
```
sudo apt install -y ansible
```
Step 5: Verify installation
```
ansible --version
```

Expected output (example):
```
ubuntu@ip-172-31-22-78:~$ ansible --version
ansible [core 2.19.3]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/ubuntu/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /home/ubuntu/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible
  python version = 3.12.3 (main, Aug 14 2025, 17:47:21) [GCC 13.3.0] (/usr/bin/python3)
  jinja version = 3.1.2
  pyyaml version = 6.0.1 (with libyaml v0.2.5)
```
