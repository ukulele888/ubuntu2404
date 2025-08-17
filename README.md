# ubuntu2404
A Docker version of Ubuntu 24.04.

# deploy
```
docker run -d \
  --name ubuntu \
  -v /etc/ubuntu:/home/user \
  -p 2222:22 -p 8022:8022 \ 
  -e SSH_USER=user \
  -e SSH_PASSWORD='password' \
  -e TTYD_USER=user \
  -e TTYD_PASS='password' \
  ghcr.io/ukulele888/ubuntu2404:250816
