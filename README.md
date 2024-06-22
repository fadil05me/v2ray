# V2ray

Install:

```
curl -O https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh;
sudo bash install-release.sh;
sudo systemctl enable v2ray;
sudo systemctl restart v2ray;
sudo nano /usr/local/etc/v2ray/config.json;
```


Config.json, change id to your UUID. [Generate](https://www.uuidgenerator.net/):
```
{
  "log": {
    "loglevel": "warning",
    "access": "/var/log/v2ray/access.log",
    "error": "/var/log/v2ray/error.log"
  },
  "inbounds": [
    {
      "port": 10000,
      "listen":"127.0.0.1",
      "protocol": "vmess",
      "settings": {
        "clients": [
          {
            "id": "fc348171-eb89-479e-93fd-e69f518913ba",
            "alterId": 64
          }
        ]
      },
      "streamSettings": {
        "network": "ws",
        "wsSettings": {
        "path": "/ray"
        }
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "freedom",
      "settings": {}
    }
  ]
}
```

```
systemctl restart v2ray;
```
