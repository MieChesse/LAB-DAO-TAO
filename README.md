# FILE HUONG DAN SERVER LAB CENTOS

## I. DOI PORT SSH THANH PORT 2022

### 1. Truy cap vao file sshd_config

* vi etc/sshd/sshd_config

2. Doi dong #Port 22 thanh Port 2022 >>> SAVE FILE

4. Restart service SSH 

* systemctl restart ssh

***

## II. SSH BANG KEY GEN

1. Tao key SSH[^1]

* ssh-keygen
[^1]:
	Private key nam trong thu muc /home/root/.ssh/id_rsa / Public key nam trong thu muc /home/root/.ssh/id_rsa.pub

2. Copy file SSH KEY vua tao vao server

* ssh-copy-id -p 2022 user@remote_host

3. Kiem tra lai ket noi SSH

* ssh username@remote_host

4. 
