# docker-ce-linuxubuntu18.04
A quick tutorial on how to set up Docker Community Edition for a Linux Ubuntu 18.04 server.

Install Docker CE on Linux Ubuntu 18.04 server

Install required dependencies:
    
	$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
    
Import repositories GPG key

	$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    
Add Docker APT repository

	$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    
Update apt package list and install latest version of docker ce (community edition)

	$ sudo apt update
	$ sudo apt install docker-ce


Check version

	$ docker --version

If you want to be able to skip using the sudo command, you have to create a docker group, where you will add your user.

Create Docker group

	$ sudo groupadd docker

Add user to docker group:
    
	$ sudo usermod -aG docker $USER
    
Log out and back in so that group membership is revaluated. You might need a reboot if your using a virtual machine, in that case, type:

	$ reboot


Verify that docker runs without sudo command by running the hello world image:

	$ docker run hello-world




Troubleshooting:

If Docker Daemon won’t start for some reason and you have to start it manually, type the command:
    
	$ dockerd

