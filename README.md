# Setup Jenkins Server

### Make a new server

AWS, DigitalOcean, whatever. Using DigitalOcean with Ubuntu 18

### Install Java
```
> sudo add-apt-repository ppa:webupd8team/java
> sudo apt update
> sudo apt install oracle-java8-installer
> sudo apt install oracle-java8-set-default
```

### Install Jenkins
```
> cd /tmp && wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
> echo 'deb https://pkg.jenkins.io/debian-stable binary/' | sudo tee -a /etc/apt/sources.list.d/jenkins.list
> sudo apt update
> sudo apt install jenkins
```

### Start Jenkins
```
> sudo systemctl stop jenkins.service
> sudo systemctl start jenkins.service
> sudo systemctl enable jenkins.service
```

### Install Ansible
```
> sudo apt update
> sudo apt install software-properties-common
> sudo apt-add-repository ppa:ansible/ansible
> sudo apt update
> sudo apt install ansible
```

### Configure Ansible to work with DigitalOcean
```
> sudo apt install python-pip
> sudo pip install 'dopy>=0.3.5,<=0.3.5'
```
Copy this repo's `hosts` to `/etc/ansible`

### Configure Jenkins

Go to [jenkins_server_ip]:8080. Follow instructions.


# Special Thanks

The ansible scripts/structure setup in this repo is highly based on [Kwpolska](https://github.com/Kwpolska)'s [ansible-nginx-uwsgi](https://github.com/Kwpolska/ansible-nginx-uwsgi), which is a great tool to learn how dynamic and modular ansible can be.
