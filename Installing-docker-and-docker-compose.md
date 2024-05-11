#Installing Docker and Docker Compose on Ubuntu Server

Step 1 — Prepare the system for installation
Before we can start installing docker & docker-compose we need to make sure that the system is up to date. You can do it by running the following commands:
```
sudo apt update
sudo apt upgrade -y
```
Step 2 — Download and Install the docker repository
Docker is using an installation repository. to install the repository and use it we need to install the following packages:
```
sudo apt install -y ca-certificates curl gnupg lsb-release
```
After the package installation, we need to add Docker’s GPG Key to our system by running the following commands:
```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```
Now we can install the docker repository by running the following commands:
```
sudo echo  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
```
Step 3 — Installing Docker
You can proceed to install Docker by executing the provided command below. This straightforward command will enable you to initiate the Docker installation process on your system.
```
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
Step 4 — Installing Docker Compose
To install docker-compose tun the following commands:

sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
To verify that your Docker Compose installation was successful, you can use the following command:

docker-compose --version
