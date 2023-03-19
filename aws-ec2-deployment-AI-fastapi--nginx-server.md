# Craete Instace by Clincking on Launch Instance

-    Open an SSH client.

-    Locate your private key file. The key used to launch this instance is aiattendance.pem

    $ chmod 400 aiattendance.pem

## Connect to your instance using its Public DNS:

      ec2-44-197-116-189.compute-1.amazonaws.com

## Example:
      ssh -i "aiattendance.pem" ubuntu@ec2-44-197-116-18.compute-1.amazonaws.com

# Update Packages 
      $ sudo apt update
      $ sudo apt upgrade

# Setup Python Environment
      $ sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget
      $ wget https://www.python.org/ftp/python/3.10.7/Python-3.10.7.tgz
      $ tar -xf Python-3.10.7.tgz 
      $ cd Python-3.10.7/
      $ ./configure --enable-optimizations
      $ sudo make install
      $ python3 --version
      $ sudo apt install python3-pip3 python3-virtualenv
   
# SSH - GitHub Securely
      $ sudo apt install git
      $ ssh-keygen -t ed25519 -C "skhapijulhossen@gmail.com"
      $ eval "$(ssh-agent -s)"
      $ ssh-add ~/.ssh/id_ed25519
      $ cat < .ssh/id_ed25519.pub
      $ git clone git@github.com:aieservices/AI_attendance.git
   
# NginX Server Setup
      $ sudo apt install nginx
      $ sudo nano etc/nginx/sites-enabled/aiserver
      $ sudo nano etc/nginx/sites-available/aiserver
  ## Add into Both File and Save it
     server {
                listen 80;
                server_name 44.197.116.18;
                location / {
                     include proxy_params;
                    proxy_pass http://127.0.0.1:8000;
             }
        }
  ## Then restart nginx
      $  sudo service nginx restart

# Setup as a Systemd Service

  ## add into server.service file
      [Unit]
      Description=AI Attendance System
      After=network.target

      [Service]
      User=ubuntu
      Group=ubuntu
      WorkingDirectory=/home/ubuntu/AI_attendance
      ExecStart=/opt/tensorflow/bin/uvicorn server:app 
   ## Then run below commands
      $ sudo nginx -t
      $ sudo systemctl daemon-reload
      $ sudo systemctl start server
      $ sudo systemctl enable server
      $ sudo systemctl enable server
      $ sudo systemctl restart nginx
      $ sudo systemctl status server.service 
  ## To stop Service
      $ sudo systemctl stop server
