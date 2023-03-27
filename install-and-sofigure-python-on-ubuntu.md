# Update System
    sudo apt update
# Install Prerequisite
    sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libreadline-dev libffi-dev wget libsqlite3-dev
#  Download Python from Source
    wget https://www.python.org/ftp/python/3.10.7/Python-3.10.7.tgz
# Extract
    tar -xf Python-3.10.7.tgz 
    cd Python-3.10.7/
# Install
    ./configure --enable-loadable-sqlite-extensions --enable-optimizations
    sudo make install
    python3 --version

