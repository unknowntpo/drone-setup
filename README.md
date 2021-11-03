# Drone Setup

## Quick Start

```
# Install Caddy (see https://caddyserver.com/docs/install#debian-ubuntu-raspbian).
apt --yes install -y debian-keyring debian-archive-keyring apt-transport-https
curl -L https://dl.cloudsmith.io/public/caddy/stable/gpg.key | sudo apt-key add -
curl -L https://dl.cloudsmith.io/public/caddy/stable/debian.deb.txt | sudo tee -a /etc/apt/sources.list.d/caddy-stable.list
apt update
apt --yes install caddy
```

Set up caddy

```
mkdir /etc/caddy
mv ./Caddyfile /etc/caddy
```

make directory to put drone config file.

```
$ mkdir /etc/drone
$ mv ./server.env ./runner.env ./docker-compose.yml /etc/drone
```

set up service daemon.

```
$ mv ./drone.service /etc/systemd/system/
# start the service daemon.
$ sudo systemctl start drone
```
