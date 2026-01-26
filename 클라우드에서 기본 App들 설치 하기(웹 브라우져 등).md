# 웹브라우져(구글 크롬)

```
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt install -f
```
# docker 설치 하기 

```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo bash get-docker.sh

# root권한 실행을 위한 추가 작업 
sudo usermod -aG docker $USER
newgrp docker
```
