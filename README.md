# Ansible Practice Repository

## Purpose
Purpose of this repository is for practicing ansible

## Prerequisites
In order to set your machine (assuming Windows) up to run playbooks here, you'll need to do the following:
1. Setup WSL2 - Documentation can be found [here](https://learn.microsoft.com/en-us/windows/wsl/install)
2. Install Docker Desktop - Documentation can be found [here](https://docs.docker.com/desktop/setup/install/windows-install/)
3. Install Python3 - Download from the official Python website [here](https://www.python.org/downloads/)

## Setting Up Your Environment
1. Open VSCode
2. Start a WSL terminal session
3. Create a python virtual environment with the command `python3 -m [name your virtual environment] [path for your virtual environment]`. ex:
    ```
    user@user-pc:~$ python3 -m venv venv
    ```
4. Activate your virtual environment with the command `source [path to virtual environment]/venv/bin/activate`. You should see venv in front of your user in the prompt ex:
    ```
    (venv) user@user-pc:~$
    ```
5. Update the python package handler pip with the following command:
    ```
    (venv) user@user-pc:~$ python3 -m pip install --upgrade pip
    ```
6. Install Ansible via pip with the following command:
    ```
    (venv) user@user-pc:~$ pip3 install ansible
    ```
7. Clone this repository:
    ```
    (venv) user@user-pc:~$ git clone https://github.com/Jeff-Marm-Al/ansiblePractice.git
    ```
8. Generate an ssh key pair
    ```
    (venv) user@user-pc:~$ ssh-keygen -t rsa -b 4096
    ```

## Playbooks
Currently there's only one playbook, the createContainers.yaml playbook. In order to run this playbook, you'll need to run the following command:

```
(venv) user@user-pc:~/ansiblePractice/playbooks$ ansible-playbook createContainers.yaml
```
If successful, you can check Docker Desktop to verify the containers exist or run the following command to list the containers:
```
docker ps -a
```
You can then try to ssh to the container by running the following command:
```
ssh -i [path to your private key/ansible_practice] -p [port number] ansible@localhost
```