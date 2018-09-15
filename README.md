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
