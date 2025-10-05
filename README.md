# proxmox-freezing-fix

mkdir -p /etc/systemd/system/pveproxy.service.d
nano /etc/systemd/system/pveproxy.service.d/keepalive.conf

Copy and paste:

[Service]
Environment="PROXMOX_KEEPALIVE=3600"

Then:
echo "console: { keepalive: 3600 }" >> /etc/pve/datacenter.cfg
systemctl daemon-reload
systemctl restart pveproxy
