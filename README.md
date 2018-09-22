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


# Special Thanks, Copyright

The ansible scripts/structure setup in this repo is highly based on [Kwpolska](https://github.com/Kwpolska)'s [ansible-nginx-uwsgi](https://github.com/Kwpolska/ansible-nginx-uwsgi), which is a great tool to learn how dynamic and modular ansible can be.

Copyright © 2016-2018, Chris Warrick. All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this list of conditions, and the following disclaimer.

Redistributions in binary form must reproduce the above copyright notice, this list of conditions, and the following disclaimer in the documentation and/or other materials provided with the distribution.

Neither the name of the author of this software nor the names of contributors to this software may be used to endorse or promote products derived from this software without specific prior written consent.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
