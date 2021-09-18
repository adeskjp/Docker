# Docker
Docker Environment

# Docker install on Ubuntu (Ubuntu 20.04.2 LTS (GNU/Linux 5.4.0-80-generic x86_64))
- Date 09/18/2021
```sh
$sudo apt update
sudo apt install -y \
     apt-transport-https \
     ca-certificates \
     curl \
     software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

$ sudo add-apt-repository \
     "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) \
     stable" 
$ sudo apt update
$ sudo apt install -y docker-ce

$ sudo usermod -aG docker root

$ sudo usermod -g docker ubuntu
sudo mkdir /etc/systemd/system/docker.service.d
sudo bash -c "echo -e \"[Service]\nEnvironment=\"HTTPS_PROXY=http://<uid>:<pwd>@<Proxy-addr>:<Proxy-port>/\"\nEnvironment=\"NO_PROXY=localhost,127.0.0.1\"\" | tee /etc/systemd/system/docker.service.d/http-proxy.conf"
sudo systemctl daemon-reload
sudo systemctl restart docker
```
# Docker-Compose Install on Ubuntu (Ubuntu 20.04.2 LTS (GNU/Linux 5.4.0-80-generic x86_64))
```sh
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
$ docker-compose --version
```
