# Deployments configurations

## Configure services

(TODO) Create the missing config files

### Configure DNS

To make the inter pod communication simpler add the local IP address to the `/etc/hosts` file.

## Start services

First we start dns with:
$ podman play kube dns/dns.yml

Then we start proxy with:
$ podman play kube proxy/proxy.yml

Finally nextcloud with:
$ podman play kube nextcloud/nextcloud.yml --configmap nextcloud-$CONFIG-configmap.yml


## Service installation

copy the service files to `~/.config/systemd/user/`

### enable service

```shell
systemctl --user daemon-reload
systemctl --user enable nextcloud@sontheim --now
```

## DNS

update the dyndns-config before starting the service

### reload Caddy

```shell
podman exec -w /etc/caddy proxy-service caddy reload
```
