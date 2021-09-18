# Docker
Docker Environment

# Docker install on Ubuntu
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
