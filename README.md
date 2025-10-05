# proxmox freezing fix

Copy and paste in terminal:
- mkdir -p /etc/systemd/system/pveproxy.service.d
- nano /etc/systemd/system/pveproxy.service.d/keepalive.conf

Copy and paste in editor:

```
[Service]
Environment="PROXMOX_KEEPALIVE=3600"
```

Then copy and paste in terminal:
- echo "console: { keepalive: 3600 }" >> /etc/pve/datacenter.cfg
- systemctl daemon-reload
- systemctl restart pveproxy
