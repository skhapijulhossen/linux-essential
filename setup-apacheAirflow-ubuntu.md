# Update System
    sudo apt-get update
# Setup prerequisite
    sudo apt-get install software-properties-common
    sudo apt-add-repository universe
# Install Essential
    sudo apt-get install python3-setuptools python3-pip python3-virtualenv
    sudo apt-get install libmysqlclient-dev libssl-dev libkrb5-dev 
# Configure
    export AIRFLOW_HOME=~/airflow
    echo AIRFLOW_HOME
    sudo pip3 install apache-airflow typing_extensions
    sudo pip3 install 'apache-airflow==2.4.2'  --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-2.4.2/constraints-3.10.txt"
    
    airflow db init
    airflow users create --username happy --firstname SK --lastname  HOSSEN --role Admin --email skhapijulhossen@gmail.com
# Start Server
    airflow webserver -p 8080
