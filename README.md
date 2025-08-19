# ubuntu2404
A Docker version of Ubuntu 24.04.

# deploy
```
docker run -d \
  --name ubuntu \
  --restart unless-stopped \
  -v /etc/ubuntu:/home/user \
  -p 2222:22 \
  -p 8022:8022 \
  -e SSH_USER=user \
  -e SSH_PASSWORD=password \
  -e TTYD_USER=webuser \
  -e TTYD_PASS=password \
  ghcr.io/ukulele888/ubuntu2404:latest

# Docker compose.yml
```
services:
  ubuntu:
    image: ghcr.io/ukulele888/ubuntu2404:latest
    container_name: ubuntu
    restart: unless-stopped
    ports:
      - "2222:22"
      - "8022:8022"
    environment:
      SSH_USER: user
      SSH_PASSWORD: password
      TTYD_USER: webuser
      TTYD_PASS: password
    volumes:
      - /etc/ubuntu:/home/user
