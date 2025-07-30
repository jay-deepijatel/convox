# Convox 3.0 installation Manual
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
### Asterisk-addons

```bash
tar -xvf asterisk-addons-1.4.6.tar.gz
cd asterisk-addons-1.4.6.
./configure
make
make install
cd ..
```

### Asterisk-sounds

```bash
tar -xvf asterisk-sounds-1.2.1.tar
cd asterisk-sounds-1.2.1
make install
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

## ConVox Installation (3.0)

Download:

```bash
svn checkout http://172.16.12.34/svn/ConVoxCCS3.0/tags/encrypted/Civil_Supplies_ENC/
``` 
- Enter root password for your system
- username : `aijaz`
- password : `aijaz@1`
