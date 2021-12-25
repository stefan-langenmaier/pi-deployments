First we start dns with:
$ podman play kube dns/dns.yml

Then we start proxy with:
$ podman play kube proxy/proxy.yml

Finally nextcloud with:
$ podman play kube nextcloud/nextcloud.yml


## Service installation

copy the service file to `~/.config/systemd/user/`

### enable service

```shell
systemctl --user daemon-reload
systemctl --user enable nextcloud --now
```
