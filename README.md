# Ansible-Setup-Control-ManageNode
### This is the repo for having steps of setting up control node and manage node connection using passwordless mechanism

- In the below step I am using my .pem file to login to managed-node server and also creating /.ssh folder along with assigning 700 permission
```
jaju93@Arpita-Pc:~$ ssh -i manage-node-key.pem ubuntu@34.224.51.243 "mkdir -p ~/.ssh && chmod 700 ~/.ssh"
```
The authenticity of host '34.224.51.243 (34.224.51.243)' can't be established.
ED25519 key fingerprint is SHA256:/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '34.224.51.243' (ED25519) to the list of known hosts.

-------------------------------------------------------------------------------------------------------------
- In this step I am logging in to the managed-node server
```
jaju93@Arpita-Pc:~$ ssh -i manage-node-key.pem ubuntu@34.224.51.243
```
Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 6.14.0-1015-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Nov  4 19:30:35 UTC 2025

****  System load:  0.05              Temperature:           -273.1 C
  Usage of /:   26.2% of 6.71GB   Processes:             114
  Memory usage: 22%               Users logged in:       0
  Swap usage:   0%                IPv4 address for ens5: 172.31.17.0
----------------------------------------------------------------------------------------------------------------------------**

- In the below steps I am creating /.ssh folder and assigning 700 permission to it and then logging out of the server
```
ubuntu@ip-172-31-17-0:~$ mkdir -p ~/.ssh
ubuntu@ip-172-31-17-0:~$ chmod 700 ~/.ssh
ubuntu@ip-172-31-17-0:~$ exit
```
----------------------------------------------------------------------------------------------------------------------------**

- In this step I am again logging in to the managed-node server using .pem key
```
jaju93@Arpita-Pc:~$ ssh -i manage-node-key.pem ubuntu@34.224.51.243
```
Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 6.14.0-1015-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com

- In the below step I am generating a ssh key (private and public key) in my control-node which I will transfer to my other managed-nodes
```
jaju93@Arpita-Pc:~$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/jaju93/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/jaju93/.ssh/id_rsa
Your public key has been saved in /home/jaju93/.ssh/id_rsa.pub

-----------------------------------------------------------------------------------------------------------------------------------------------------------------
- In the below step, I am copying ssh public key from control-node to managed-node server at folder /.ssh/authorized_keys after successful login using .pem file and then assigning 600 permission to the folder
```
jaju93@Arpita-Pc:~$ cat ~/.ssh/id_rsa.pub | ssh -i manage-node-key.pem ubuntu@34.224.51.243 "cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"
```
- Now finally I am doing logging in from control-node to managed-node server using only ssh command with username and server IP
```
jaju93@Arpita-Pc:~$ ssh ubuntu@34.224.51.243
```
Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 6.14.0-1015-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Nov  4 19:33:20 UTC 2025
 * Support:        https://ubuntu.com/pro

 System information as of Tue Nov  4 19:32:09 UTC 2025

### Try the same steps for other managed-node server.
