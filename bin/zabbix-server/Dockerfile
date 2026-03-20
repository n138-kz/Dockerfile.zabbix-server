FROM ubuntu
WORKDIR /tmp
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y wget
RUN apt-get install -y postgresql-client

# https://www.zabbix.com/jp/download
# https://www.zabbix.com/jp/download?zabbix=7.4&os_distribution=ubuntu&os_version=24.04&components=server_frontend_agent&db=pgsql&ws=apache

# Install Zabbix repository
RUN wget -O zabbix-release.deb https://repo.zabbix.com/zabbix/7.4/release/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.4+ubuntu24.04_all.deb
RUN dpkg -i zabbix-release.deb
RUN apt-get update

# Install Zabbix server, frontend, agent
RUN apt-get install -y zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent

# Create initial database
RUN mkdir -p /zabbix-sql && cp /usr/share/zabbix/sql-scripts/postgresql/server.sql.gz /zabbix-sql/

# Zabbix Server の設定ファイルを編集 (DB接続先を "database" に向ける)
RUN sed -i 's/^# LogType=file/LogType=console/g' /etc/zabbix/zabbix_server.conf && \
    sed -i 's/^# DBHost=localhost/DBHost=database/g' /etc/zabbix/zabbix_server.conf && \
    sed -i 's/^# DBPassword=/DBPassword=password/g' /etc/zabbix/zabbix_server.conf

# Start Zabbix server and agent processes
CMD ["/usr/sbin/zabbix_server", "-f", "-c", "/etc/zabbix/zabbix_server.conf"]
