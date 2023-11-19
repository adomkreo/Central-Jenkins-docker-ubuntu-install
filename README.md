# Jenkins-docker-ubuntu- t2. medium install
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
BASH

Copied!
# java installation
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
# Grand sudo access to jenkins user
sudo echo "jenkins ALL=(ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/jenkins

sudo apt-get install docker.io -y

# 2. Enable PasswordAuthentication in the server
sudo sed -i "/^[^#]*PasswordAuthentication[[:space:]]no/c\PasswordAuthentication yes" /etc/ssh/sshd_config
sudo service sshd restart
#
sudo usermod -aG docker jenkins

sudo hostname admin
sudo su - jenkins
# install kops software
# install kubectl
# install aws cli
# attache kubernetes role to this server

