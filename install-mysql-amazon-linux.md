## INSTALL MYSQL 8 COMMUNITY EDITION ON AMAZON LINUX 2023

### VERIFY OS VERSION
```sh
cat /etc/*release*
```

### DOWNLOAD & INSTALL MYSQL REPOSITORY
```sh
sudo wget https://dev.mysql.com/get/mysql84-community-release-el9-1.noarch.rpm
sudo dnf install mysql80-community-release-el9-1.noarch.rpm
dnf repolist enabled | grep "mysql.*-community.*"
```

### INSTALL MYSQL SERVER
```sh
sudo dnf -y install mysql-community-server
```

### ENABLE MYSQL SERVICE TO AUTO-START ON REBOOT
```sh
systemctl status mysqld
sudo systemctl enable mysqld
```

### START MYSQL SERVICE
```sh
sudo systemctl start mysqld.service
```

### CHECK STATUS OF MYSQL SERVICE
```sh
systemctl status mysqld.service
```

### VERIFICATION
```sh
pidof mysqld
sudo lsof -u mysql
```

### GET TEMPORARY PASSWORD
```sh
sudo grep 'temporary password' /var/log/mysqld.log
```

### SECURE INSTALLATION
```sh
sudo mysql_secure_installation
```
