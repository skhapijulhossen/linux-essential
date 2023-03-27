# Update SYtem
    sudo apt-get update
# Steup prerequisite
    sudo apt-get install software-properties-common
    sudo apt-add-repository universe
# Install Essential
    sudo apt-get install python3-setuptools python3-pip python3-virtualenv
    sudo apt-get install libmysqlclient-dev libssl-dev libkrb5-dev 
# Configure
    export AIRFLOW_HOME=~/airflow
    echo AIRFLOW_HOME
    sudo pip3 install apache-airflow typing_extensions
    airflow db init
# Start Server
    airflow webserver -p 8080
