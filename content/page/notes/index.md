---
title: My Notes
links:
menu:
    main: 
        weight: 5
        params:
            icon: notes

comments: true
---

Here is where I put my personal notes for anything I need to use often, commands, websites, and other stuffs.

---

## Github Codespaces

GitHub Codespaces is a cloud-based development environment hosted by GitHub.

### X11 Display Server

When running a default Codespaces image, sometimes I want to use GUI applications (e.g. web browsers for testing).

This is possible with noVNC (a web-based VNC client) and Xtigervnc (a VNC server that supports X11). Here’s a script to set them up with Docker Compose. To use it, copy the following snippet into a new Bash terminal:

```diff
mkdir -p ~/setup-display && cd ~/setup-display
cat > docker-compose.yml <<EOF
services:
  display:
    image: ghcr.io/dtinth/xtigervnc-docker:main
    tmpfs: /tmp
    restart: always
    environment:
      VNC_GEOMETRY: 1440x900
    ports:
      - 127.0.0.1:5900:5900
      - 127.0.0.1:6000:6000
  novnc:
    image: geek1011/easy-novnc
    restart: always
    command: -a :5800 -h display --no-url-password
    ports:
      - 127.0.0.1:5800:5800
EOF
docker compose up -d
```

Once run, we need to tell our applications to connect to the server we started. To do that, set the DISPLAY environment variable to `127.0.0.1:0`:

```diff
export DISPLAY=127.0.0.1:0
```

Once that’s done, we can start our GUI applications from that terminal.
