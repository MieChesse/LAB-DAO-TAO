# FILE HUONG DAN SERVER LAB CENTOS

## I. DOI PORT SSH THANH PORT 2022

**1. Truy cap vao file sshd_config**

- vi etc/sshd/sshd_config

**2. Doi dong #Port 22 thanh Port 2022 >>> SAVE FILE**

**3. Restart service SSH**

- systemctl restart ssh

***

## II. SSH BANG KEY GEN

**1. Tao key SSH[^1]**

- ssh-keygen
[^1]:
	Private key nam trong thu muc /home/root/.ssh/id_rsa / Public key nam trong thu muc /home/root/.ssh/id_rsa.pub

**2. Copy file SSH KEY vua tao vao server**

- ssh-copy-id -p 2022 user@remote_host

**3. Truy cap vao thu muc /home/root/.ssh/id_rsa de COPY private key**

- vi .ssh/id_rsa

**4. Save lai file private key duoi duoi .ppk**

**5. Tai PuTTyGen ve de Import key vua save với duoi .ppk >>> save lai lan nua**

**6. Truy cap PUTTY >>> SSH >>> AUTH de Browse den file PRIVATE KEY vua SAVE**

**7. Vao muc Session cua PUTTY nhap Hostname và Port SSH 2022, nhap ten Session roi bam SAVE lai**

**8. Truy cap bang PUTTY**

**9. Neu truy cap SSH với MREMOTE them 2 dong sau vao file sshd_config**

- HostKeyAlgorithms +ssh-rsa
- PubkeyAcceptedKeyTypes +ssh-rsa

**10. Truy cap vao file sshd_config**

- vi /etc/ssh/sshd_config

**11. Sua lại 2 dong trong file sshd_config[^2]**

- PasswordAuthentication no
- PermitRootLogin no
[^2]:
	Disable ssh bang password va login user root
	
***

## II. Gioi han ket noi SSH cho phep voi IP wan toa nha MB

**1. Truy cap vao file hosts.deny de tu choi tat ca ket noi SSH**

- vi /etc/hosts.deny
- sshd: ALL

**2. Truy cap vao file hosts.allow de whitelist IP toa nha**

- vi /etc/hosts.allow
- sshd: IP : allow

***

## III. Cai dat tuong lua UFW

| **DAU MUC**       | **TAP LENH**           |
| ------------- |:-------------:|
| Xac minh trang thai tuong lua      | ufw status |
| Bat tuong lua      | ufw enable     |
| Check service tuong lua | systemctl status ufw     |
| Disable tuong lua | ufw disable |
| Mo port 80 | ufw allow 80/tcp comment 'accept Apache' |
| Mo port 443 | ufw allow 443/tcp comment 'accept HTTPS connections' |
| Allow port tcp range | ufw allow 3000:4000/tcp |
| Allow port udp range | ufw allow 3000:4000/udp |
| Allow IP | ufw allow from 104.22.10.214 |
| Allow IP to port | ufw allow from 104.22.10.214 to any port 25 proto tcp |
| Check number rule ufw | ufw status numbered |
| Delete rule | ufw status numbered |

Tham khao them o bai viet [https://www.cyberciti.biz/faq/how-to-configure-firewall-with-ufw-on-ubuntu-20-04-lts/]

***

## IV. Thay doi hostname chuan FQDN

**Kiem tra hostname hien tai**

- hostnamectl

**Doi hostname hien tai**

- hostnamectl set-hostname sv48d185.teammailmb.xyz

***

## V. Set Timezone

**Xem timezone hien tai**

- timedatectl

**Xem va tim cac time zone khac**

- timedatectl list-timezones

**Set time zone da tim**

- timedatectl set-timezone your_time_zone

***

## VI. Install CWP

- cd /usr/local/src
- wget http://centos-webpanel.com/cwp-el7-latest
- sh cwp-el7-latest

