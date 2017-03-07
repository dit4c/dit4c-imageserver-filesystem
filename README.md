# dit4c-imageserver-filesystem

A DIT4C image server using a file-system backend.

## Running

```
$ rkt trust --root http://dit4c.github.io/release-signing-key.asc
$ rkt --dns=8.8.8.8 run \
  --volume tls,kind=host,source=/etc/tls,readOnly=true \
  https://github.com/dit4c/dit4c-imageserver-filesystem/releases/download/0.1.0/dit4c-imageserver-swift.linux.amd64.aci \
  --set-env-file /etc/dit4c-imageserver.env \
  --port https:443 \
  --mount volume=tls,target=/tls
```

`dit4c-imageserver.env` example:
```
PORTAL_URI=https://dit4c.example
TLS_CERT=/tls/server.crt
TLS_KEY=/tls/server.key
```
