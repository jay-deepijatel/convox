
# 3.2 Installation

---

## Convox Versions

- 3.0 (unavailable)
- 3.2.4
- 3.3.1
- 4.0
- 4.0.1
- 4.0.2

---

## Pre-requisites for Convox Installation

- Configure YUM repository.
- Disable Firewall & SELinux:
  ```bash
  systemctl status firewalld
  systemctl stop firewalld
  systemctl disable firewalld
  getenforce
  setenforce 0
  vi /etc/selinux/config
  # Set: SELINUX=disabled
  ```
- If yum packages are not installing, check DNS:
  ```bash
  ping google.com
  ```

---

## Basic YUM Packages

```bash
yum install openssh* -y
yum install ncurses* -y
yum install sox* -y
yum install svn* -y
yum install make* screen* gcc* -y
yum install perl* -y
yum install maria* -y
yum install http* -y
yum install php* -y --skip-broken
yum install wget* -y
yum install kernel* -y
yum install libxm* -y
yum install vim* -y
yum install zip* unzip* -y
```

Or install all in one command:

```bash
yum install openssh* ncurses* sox* svn* make* screen* gcc* perl* maria* http* php* --skip-broken wget* kernel* libxm* vim* zip* unzip* -y
yum -y install openssh* svn* mysql* mariadb* perl* httpd* ncurses* gcc* sox* make* screen* wget* kernel* libxm* vim* zip unzip -y
```

---

## Digest-Packages Installation and Configuration

Download the packages from: `https://omnisupport.deepijatel.in/ahmed/`  
Copy them into `/usr/src/packages/`

### Installation Commands

```bash
# 1. Digest-MD5
tar -xvf Digest-MD5-2.36.tar
cd Digest-MD5-2.36
perl Makefile.PL
make
make test
make install
cd ..

# 2. Digest-SHA1
tar -xvf Digest-SHA1-2.11.tar
cd Digest-SHA1-2.11
perl Makefile.PL
make
make test
make install
cd ..

# 3. Net-Telnet
tar -xvf Net-Telnet-3.03.tar
cd Net-Telnet-3.03
perl Makefile.PL
make
make test
make install
cd ..

# 4. Net-MySQL
tar -xvf Net-MySQL-0.08.tar
cd Net-MySQL-0.08
perl Makefile.PL
make
make test
make install
cd ..

# 5. Time-HiRes
tar -xvf Time-HiRes-1.90.tar
cd Time-HiRes-1.90
perl Makefile.PL
make
make test
make install
cd ..

# 6. asterisk-perl
tar -xvf asterisk-perl-0.08.tar
cd asterisk-perl
perl Makefile.PL
make
make install
```

Check if packages installed:

```bash
instmodsh -l
```

---

## Additional Package Installation

```bash
yum install libtool* make gcc patch perl bison flex-devel gcc-c++ ncurses-flex libtermcap-devel autoconf* automake* autoconf libxml2-devel cmake openssl*
```

Download from: `https://omnisupport.deepijatel.in/ahmed/`

### DAHDI Linux

```bash
tar -xvf dahdi-linux-complete-2.9.0+2.9.0.tar.gz
cd dahdi-linux-complete-2.9.0+2.9.0
make
make install
make config
cd ..
```

### LibPRI

```bash
tar -xvf libpri-1.4.10.tar.gz
cd libpri-1.4.10
make
make install
cd ..
```

### Asterisk

```bash
tar -xvf asterisk-1.4.32.tar.gz
cd asterisk-1.4.32
./configure
make
make install
make samples
cd ..
```

To start Asterisk:

```bash
asterisk -vr
safe_asterisk
asterisk -vr
```

### Enable Services

```bash
systemctl start httpd
systemctl enable httpd

systemctl start mariadb
systemctl enable mariadb
```

---

## ConVox Installation (3.2.4)

Download:

```bash
wget https://dtelhelp.deepija.com/Hymavathi/convoxccs-3.2.4_c58a11ff.zip
cd /usr/src/packages
unzip convoxccs-3.2.4_c58a11ff.zip
cd convoxccs\ 3.2
sh convox32_setup.sh
```

Configure:

- `/etc/convox32.conf`:
  ```ini
  crm_account_id=ACC1722
  hostip=<network IP>
  ethernet_port=enp2s0
  asterisk_version=1.8
  operational_hours=00
  ```

- `/etc/convoxwebpanel.conf`:
  ```ini
  serverIP=<your IP>
  ```

- `/etc/sysconfig/network-scripts/ifcfg-enp2so`:
  ```ini
  IPADDR=<your IP>
  HWADDR=<MAC Address>
  ```

Enable PHP Short Tag:

```bash
vim /etc/php.ini
# Set: short_open_tag = on
```

---

## Ioncube Installation

Download and install:

```bash
wget https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.zip
unzip ioncube_loaders_lin_x86-64.zip
cd ioncube/
scp ioncube_loader_lin_5.4.so /usr/lib64/php/modules/
chmod -R 777 /usr/lib64/php/modules/ioncube_loader_lin_5.4.so
```

Edit `/etc/php.d/ooioncube.ini`:

```ini
ZEND_Extension=/usr/lib64/php/modules/ioncube_loader_lin_5.4.so
```

Restart httpd and refresh the page.

---

## MySQL DB Table Configuration

- Password is in `/etc/convox32.conf`
- Connect to MySQL:

```bash
mysql convoxccs32 -u convox32 -p
show tables;
select * from convoxccs_agent_details;
```

Insert data:

```sql
INSERT INTO convoxccs_servers VALUES (3,'Normal Server','172.16.13.110','Y','172.16.13.110',5038,'convox','convox','updateconvox','listenconvox','sendconvox','N','N','FILE',0,0);
INSERT INTO convoxccs_web_servers VALUES (" ",'172.16.13.110','80','Normal Server','Y');
```
