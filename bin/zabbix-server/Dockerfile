from ubuntu
workdir /tmp
run apt-get update && DEBIAN_FRONTEND=noninteractive
run apt-get upgrade -y
# https://www.zabbix.com/jp/download
# https://www.zabbix.com/jp/download?zabbix=7.4&os_distribution=ubuntu&os_version=24.04&components=server_frontend_agent&db=pgsql&ws=apache
run apt-get install -y wget
run wget -O zabbix-release.deb https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu24.04_all.deb
run dpkg -i zabbix-release.deb
run apt-get update
run apt-get install -y zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
