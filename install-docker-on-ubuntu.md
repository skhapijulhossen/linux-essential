# Installing Docker on Ubuntu Linux
## Update System
    sudo apt update 
## Install Prerequisite
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
## Then add the GPG key for the official Docker repository to your system:
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
## Add the Docker repository to APT sources:
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
## Install docker-ce from newly added repo
    apt-cache policy docker-ce
    sudo apt install docker-ce
## Now Check Ststus of Docker daemon
    sudo systemctl status docker
    sudo docker --version
