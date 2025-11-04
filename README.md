# Ansible-Setup-Control-ManageNode
This is the repo for having steps of setting up control node and manage node connection using password less
```
jaju93@Arpita-Pc:~$ ssh -i manage-node-key.pem ubuntu@34.224.51.243 "mkdir -p ~/.ssh && chmod 700 ~/.ssh"
```
The authenticity of host '34.224.51.243 (34.224.51.243)' can't be established.
ED25519 key fingerprint is SHA256:/xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '34.224.51.243' (ED25519) to the list of known hosts.

-------------------------------------------------------------------------------------------------------------
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
```
ubuntu@ip-172-31-17-0:~$ mkdir -p ~/.ssh
ubuntu@ip-172-31-17-0:~$ chmod 700 ~/.ssh
ubuntu@ip-172-31-17-0:~$ exit
```
----------------------------------------------------------------------------------------------------------------------------**
```
jaju93@Arpita-Pc:~$ ssh -i manage-node-key.pem ubuntu@34.224.51.243
```
Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 6.14.0-1015-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.comjaju93@Arpita-Pc:~$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/home/jaju93/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/jaju93/.ssh/id_rsa
Your public key has been saved in /home/jaju93/.ssh/id_rsa.pub
-----------------------------------------------------------------------------------------------------------------------------------------------------------------
```
jaju93@Arpita-Pc:~$ cat ~/.ssh/id_rsa.pub | ssh -i manage-node-key.pem ubuntu@34.224.51.243 "cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"
jaju93@Arpita-Pc:~$ ssh ubuntu@34.224.51.243
```
Welcome to Ubuntu 24.04.3 LTS (GNU/Linux 6.14.0-1015-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

 System information as of Tue Nov  4 19:33:20 UTC 2025
 * Support:        https://ubuntu.com/pro

 System information as of Tue Nov  4 19:32:09 UTC 2025

 Try the same steps for other managed-node server.
