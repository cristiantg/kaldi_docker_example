# kaldi_docker_example
Easy docker configuration to run Kaldi locally

**1. Docker installation**

```
sudo apt update
sudo apt upgrade
sudo apt-get install  curl apt-transport-https ca-certificates software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt update
apt-cache policy docker-ce
sudo apt install docker-ce
```

**2. Docker-compose installation**
```
sudo apt-get install docker-compose
sudo apt-get install make
sudo apt-get install build-essential
```

**3. Project preparation**
```
mkdir -p kaldi-project && cd kaldi-project
```

```
vi docker-compose.yml

version: '3'
services:
    kaldi:
        container_name: clst-kaldi
        command: bash -c "bash"
        image: kaldiasr/kaldi:latest
        tty: true
        stdin_open: true
        volumes:
            - ./data:/data
```

**4. Entering the Docker image clst-kaldi:**

```
cd kaldi-project && docker-compose up -d
docker exec -it clst-kaldi bash
```


**5. Contact**

Cristian Tejedor-García

Email: cristian [dot] tejedorgarcia [at] ru [dot] nl
