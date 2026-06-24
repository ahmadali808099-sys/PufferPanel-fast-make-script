#!/bin/bash

apt update
apt install -y curl gnupg apt-transport-https

curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | bash

apt update
apt install -y pufferpanel

systemctl daemon-reload
systemctl enable pufferpanel
systemctl restart pufferpanel

echo "=================================="
echo "PufferPanel Installed Successfully"
echo "=================================="

pufferpanel user add

IP=$(curl -s ifconfig.me)

echo
echo "Panel URL:"
echo "http://$IP:8080"
echo

systemctl status pufferpanel --no-pager

echo
echo "If the service is not running, start manually:"
echo "pufferpanel run"
