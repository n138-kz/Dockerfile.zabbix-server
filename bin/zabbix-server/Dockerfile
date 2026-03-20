from ubuntu
workdir /tmp
run apt update
run apt upgrade -y
# https://www.zabbix.com/jp/download
run apt install -y wget
run wget -O zabbix-release.deb https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu24.04_all.deb
run dpkg -i zabbix-release.deb
run apt update
run apt install -y zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
