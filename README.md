# ubuntu2404
A Docker version of Ubuntu 24.04.Only for research and learning use.

# deploy
This is merely a deployment example. Please obtain the latest image version from the Releases page.
```
docker run -d \
  --name ubuntu \
  --restart unless-stopped \
  -v /etc/ubuntu:/home/user \
  -p 2222:22 \
  -p 8022:8022 \
  -e SSH_USER=user \
  -e SSH_PASSWORD='password' \
  -e TTYD_USER=webuser \
  -e TTYD_PASS='password' \
  ghcr.io/ukulele888/ubuntu2404:250825
```

# Docker compose.yml
```
services:
  ubuntu:
    image: ghcr.io/ukulele888/ubuntu2404:250825
    container_name: ubuntu
    restart: unless-stopped
    ports:
      - "2222:22"
      - "8022:8022"
    environment:
      SSH_USER: user
      SSH_PASSWORD: 'password'
      TTYD_USER: webuser
      TTYD_PASS: 'password'
    volumes:
      - /etc/ubuntu:/home/user
```

# Third-party Licenses

Versions 250830 and later Docker image includes [Tailscale](https://tailscale.com/), which is licensed under the **BSD 3-Clause License**.

- The full Tailscale license can be found in [`TAILSCALE_LICENSE`](./TAILSCALE_LICENSE).
- During container build, the license is also copied to `/usr/share/doc/tailscale/LICENSE` inside the image.
