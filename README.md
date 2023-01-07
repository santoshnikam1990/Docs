# Install and configure Jenkins

## 1)  Download the Jenkins repo
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat/jenkins.repo

## 2) Import key from Jenkins
sudo rpm --import https://pkg.jenkins.io/redhat/jenkins.io.key

## 3) Install Jenkins
yum install jenkins

## 3.1) Install Java
yum install java-1.8.0-openjdk

## 4) Start Jenkins service
sudo service jenkins start

## 5) Grant shell for Jenkins user
usermod -s /bin/bash jenkins

## 6) Grant sudo permissions for Jenkins user

### 6.1) Put Jenkins user on wheel group
usermod -aG wheel jenkins

### 6.2) Create sudoers file 
visudo -f /etc/sudoers.d/jenkins
#### write this on the file
jenkins ALL=(ALL) NOPASSWD:ALL
