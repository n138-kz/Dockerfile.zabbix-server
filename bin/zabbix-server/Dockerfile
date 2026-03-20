from ubuntu
workdir /tmp
run apt update
run apt upgrade -y
# https://www.zabbix.com/jp/download
run apt install -y wget
run wget https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu24.04_all.deb
run dpkg -i zabbix-release_latest_7.4+ubuntu24.04_all.deb
run apt update
