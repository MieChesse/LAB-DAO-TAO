# FILE HUONG DAN SERVER LAB CENTOS

## I. DOI PORT SSH THANH PORT 2022

### 1. Truy cap vao file sshd_config

* vi etc/sshd/sshd_config

### 2. Doi dong #Port 22 thanh Port 2022 >>> SAVE FILE

### 3. Restart service SSH 

* systemctl restart ssh

***

## II. SSH BANG KEY GEN

### 1. Tao key SSH[^1]

* ssh-keygen
[^1]:
	Private key nam trong thu muc /home/root/.ssh/id_rsa / Public key nam trong thu muc /home/root/.ssh/id_rsa.pub

### 2. Copy file SSH KEY vua tao vao server

* ssh-copy-id -p 2022 user@remote_host

### 3. Kiem tra lai ket noi SSH

* ssh username@remote_host

### 4. Truy cap vao thu muc /home/root/.ssh/id_rsa de COPY private key

* vi .ssh/id_rsa

### 5. Save lai file private key duoi duoi .ppk

### 6. Tai PuTTyGen ve de Import key vua save với duoi .ppk >>> save lai lan nua

### 7. Truy cap PUTTY >>> SSH >>> AUTH de Browse den file PRIVATE KEY vua SAVE

### 8. Vao muc Session cua PUTTY nhap Hostname và Port SSH 2022, nhap ten Session roi bam SAVE lai

### 9. Truy cap bang PUTTY 
