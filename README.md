# trash
apt update -y && \
apt install -y docker.io && \
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
sudo chmod +x /usr/local/bin/docker-compose && \
docker-compose --version && \
git clone https://github.com/vegasbrianc/prometheus.git && \
cd prometheus

docker compose up
3.83.219.79:9100
docker-compose up -d --build
admin
foobar

    wget https://github.com/prometheus/node_exporter/releases/download/v1.3.1/node_exporter-1.3.1.linux-amd64.tar.gz && \
    tar -xvzf node_exporter-1.3.1.linux-amd64.tar.gz && \
	cd node_exporter-1.3.1.linux-amd64 && \
	cp node_exporter /usr/local/bin/ && \
	useradd --no-create-home --shell /bin/false node_exporter && \
	cd /etc/systemd/system && \
	nano node_exporter.service
	
[Unit]
Description=Node Exporter
Wants=network-online.target
After=network-online.target

[Service]
User=node_exporter
Group=node_exporter
ExecStart=/usr/local/bin/node_exporter 

[Install]
WantedBy=default.target
	
/home/ubuntu/node_exporter-1.3.1.linux-amd64# cp node_exporter /usr/local/bin/
useradd --no-create-home --shell /bin/false node_exporter

cd /etc/systemd/system
    ls -a
    nano node_exporter.service
    systemctl daemon-reload && \
    systemctl start node_exporter.service && \
    systemctl status node_exporter.service
	
	07072022

useradd -M -r -s /bin/false alertmanager
wget https://github.com/prometheus/alertmanager/releases/download/v0.24.0/alertmanager-0.24.0.linux-amd64.tar.gz
tar xzf alertmanager-0.24.0.linux-amd64.tar.gz
cp alertmanager-0.24.0.linux-amd64/{alertmanager,amtool} /usr/local/bin/
mkdir /etc/alertmanager/
cp alertmanager-0.24.0.linux-amd64/alertmanager.yml /etc/alertmanager/
chown alertmanager: /etc/alertmanager/alertmanager.yml /usr/local/bin/{alertmanager,amtool}
nano /etc/alertmanager/alertmanager.yml

cat > /etc/systemd/system/alertmanager.service << 'EOL'
[Unit]
Description=AlertManager Server Service
Wants=network-online.target
After=network-online.target

[Service]
User=root
Group=root
Type=simple
ExecStart=/usr/local/bin/alertmanager --config.file /etc/alertmanager/alertmanager.yml

[Install]
WantedBy=multi-user.target
EOL


systemctl daemon-reload
systemctl enable --now alertmanager
systemctl status alertmanager

systemctl stop alertmanager
systemctl disable alertmanager

alertmanager:
    image: prom/alertmanager
    ports:
      - 9093:9093
    volumes:
      - ./alertmanager/:/etc/alertmanager/
    networks:
      - back-tier
    restart: always
    command:
      - '--config.file=/etc/alertmanager/config.yml'
      - '--storage.path=/alertmanager'
	  
	  
	 err="*email.loginAuth

global:
  resolve_timeout: 1m

route:
  receiver: 'gmail-notifications'

receivers:
- name: 'gmail-notifications'
  email_configs:
  - to: monitoringinstances@gmail.com
    from: monitoringinstances@gmail.com
    smarthost: smtp.gmail.com:587
    auth_username: monitoringinstances@gmail.com
    auth_identity: monitoringinstances@gmail.com
    auth_password: password
    send_resolved: true
	
http://44.203.111.162
	
sudo apt update -y && \
sudo apt install nginx  -y && \
sudo ufw app list && \
sudo ufw allow 'Nginx HTTP'
sudo ufw status

service nginx restart
curl localhost:81/metrics

cd /tmp  && \
wget https://github.com/nginxinc/nginx-prometheus-exporter/releases/download/v0.7.0/nginx-prometheus-exporter-0.7.0-linux-amd64.tar.gz && \
tar -xf nginx-prometheus-exporter-0.7.0-linux-amd64.tar.gz && \
mv nginx-prometheus-exporter /usr/local/bin && \
useradd -r nginx_exporter 

# Create Systemd Service File

nano /etc/systemd/system/nginx_prometheus_exporter.service

systemctl daemon-reload

service nginx_prometheus_exporter status
service nginx_prometheus_exporter start

52.91.43.68

/etc/nginx/nginx.conf

server { 
		listen localhost:81;
		location /metrics {
			stub_status on;
		}
}

service nginx restart
curl localhost:81/metrics

docker run \
  -p 9113:9113 \
  nginx/nginx-prometheus-exporter:0.2.0 \
  -nginx.scrape.uri=http://localhost:81/metrics \
  -nginx.retries=10 \
  -web.telemetry-path=/prometheus
  
 35.175.220.188:3000
 
 52.91.43.68 | 
 
 docker run \
  -p 9113:9113 \
  nginx/nginx-prometheus-exporter:0.2.0 \
  -nginx.scrape.uri=http://52.91.43.68:81/metrics \
  -nginx.retries=10 \
  -web.telemetry-path=/prometheus
  
  http://52.91.43.68:8080/metrics 
  
  
  docker run \
  -p 9113:9113 \
  nginx/nginx-prometheus-exporter:0.2.0 \
  -nginx.scrape.uri=http://172.31.17.231:81/metrics \
  -nginx.retries=10 \
  -web.telemetry-path=/prometheus
  
  
 wget https://github.com/vozlt/nginx-module-vts/archive/v0.1.18.tar.gz
 
 ./configure --with-compat --add-dynamic-module=/usr/src/nginx-module-vts-0.1.18
 /usr/src# ls -al nginx-module-vts-0.1.18/
 
 nginx -V
    2  git clone git://github.com/vozlt/nginx-module-vts.git
    3  rm -f nginx-module-vts
    4  rm -r nginx-module-vts
    5  git clone git://github.com/vozlt/nginx-module-vts.git
    6  ping 8.8.8.8
    7  git clone git://github.com/vozlt/nginx-module-vts.git
    8  cd /usr/src
    9  wget https://github.com/vozlt/nginx-module-vts/archive/v0.1.18.tar.gz
   10  tar xf v0.1.18.tar.gz
   11  ls -al nginx-module-vts-0.1.18/
   12  wget http://nginx.org/download/nginx-1.18.0.tar.gz
   13  tar zxvf nginx-1.18.0.tar.gz
   14  cd nginx-1.18.0
   15  /usr/src# ls -al nginx-module-vts-0.1.18/
   16  ./configure --with-compat --add-dynamic-module=/usr/src/nginx-module-vts-0.1.18
   17  apt install gcc
   18  ./configure --with-compat --add-dynamic-module=/usr/src/nginx-module-vts-0.1.18
   19  apt install libpcre3 libpcre3-dev libssl-dev
   20  ./configure --with-compat --add-dynamic-module=/usr/src/nginx-module-vts-0.1.18
   21  apt install zlib
   22  apt update
   23  apt install zlib
   24  apt install zlib1g
   25  ./configure --with-compat --add-dynamic-module=/usr/src/nginx-module-vts-0.1.18
   26  apt install glib
   27  apt install zlib1g-dev
   28  ./configure --with-compat --add-dynamic-module=/usr/src/nginx-module-vts-0.1.18
   29  make modules
   30  cp objs/ngx_http_vhost_traffic_status_module.so /etc/nginx/modules
   31  chmod 644 /etc/nginx/modules/ngx_http_vhost_traffic_status_module.so
   32  nano /etc/nginx/nginx.conf
   33  history


52.91.163.249
ssh -i ".ssh/my-key.pem" ubuntu@ec2-52-91-163-249.compute-1.amazonaws.com

cd /opt/ \
    && wget https://nginx.org/download/nginx-1.18.0.tar.gz \
    && tar xf nginx-1.18.0.tar.gz
	
./configure \
    --prefix=/etc/nginx \
    --sbin-path=/usr/sbin/nginx \
    --modules-path=/usr/lib/nginx/modules \
    --conf-path=/etc/nginx/nginx.conf \
    --error-log-path=/var/log/nginx/error.log \
    --http-log-path=/var/log/nginx/access.log \
    --pid-path=/var/run/nginx.pid \
    --lock-path=/var/run/nginx.lock \
    --http-client-body-temp-path=/var/cache/nginx/client_temp \
    --http-proxy-temp-path=/var/cache/nginx/proxy_temp \
    --http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp \
    --http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp \
    --http-scgi-temp-path=/var/cache/nginx/scgi_temp \
    --user=nginx \
    --group=nginx \
    --with-http_ssl_module \
    --with-http_realip_module \
    --with-http_addition_module \
    --with-http_sub_module \
    --with-http_dav_module \
    --with-http_flv_module \
    --with-http_gunzip_module \
    --with-http_gzip_static_module \
    --with-http_random_index_module \
    --with-http_secure_link_module \
    --with-http_stub_status_module \
    --with-http_auth_request_module \
    --with-threads --with-stream \
    --with-stream_ssl_module \
    --with-http_slice_module \
    --with-mail \
    --with-mail_ssl_module \
    --with-file-aio \
    --with-http_v2_module \
    --with-cc-opt='-g -O2 -fstack-protector-strong -Wformat -Werror=format-security -Wp,-D_FORTIFY_SOURCE=2' \
    --with-ld-opt='-Wl,-Bsymbolic-functions -Wl,-z,relro -Wl,--as-needed' \
    --add-module=/opt/nginx-module-vts-0.1.15
	
	
	wget https://github.com/prometheus-community/postgres_exporter/releases/download/v0.10.1/postgres_exporter-0.10.1.linux-amd64.tar.gz O - | tar -xzv -C /tmp
	
	wget https://github.com/wrouesnel/postgres_exporter/releases/download/v0.10.1/postgres_exporter_v$VERSION_linux-amd64.tar.gz -O - | tar -xzv -C /tmp
	
	3.90.105.232
	
	54.91.230.205 prometheus
	
git clone https://github.com/deviantony/docker-elk.git
ELASTIC_VERSION=7.17.0
docker-compose up -d --build

git clone https://github.com/deviantony/docker-elk.git ELASTIC_VERSION=7.17.0 .env
docker-compose up -d --build --force-recreate

apt update -y && \
apt install -y docker.io && \
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose && \
sudo chmod +x /usr/local/bin/docker-compose && \
docker-compose --version && \
git clone https://github.com/vegasbrianc/prometheus.git && \
cd prometheus

3.85.135.185:5601

7.15.1

kibana_1        "tags":["error","elasticsearch-service"],"pid":6,"message":"Unable to retrieve version information from Elasticsearch nodes. getaddrinfo ENOTFOUND elasticsearch"}

docker-elk_elasticsearch_1   /bin/tini -- /usr/local/bi ...   Exit 137 

https://github.com/hpcugent/logstash-patterns/blob/master/files/grok-patterns
https://grokdebug.herokuapp.com/
https://www.elastic.co/guide/en/logstash/current/plugins-filters-grok.html

filter {
        grok {
            match => { "message" => "%{IP:clientip} (?:-|(%{WORD}.%{WORD})) %{USER:ident} \[%{HTTPDATE:timestamp}\] (?:%{WORD:verb} %{NOT
SPACE:request}(?: HTTP/%{NUMBER:httpversion})?|%{DATA:rawrequest}) %{NUMBER:response}" }
        }
}

%{IP:clientip} %{NOTSPACE:any1} %{NOTSPACE:any2} \[%{HTTPDATE:timestamp}\]

filter {
        grok {
            match => { "message" => "%{IP:clientip} (?:-|(%{WORD}.%{WORD})) (?:-|(%{WORD}.%{WORD})) \[%{HTTPDATE:timestamp}\] \"%{WORD:method} %{URIPATHPARAM:request} (?:%{SPACE}HTTP/(%{NUMBER:http_version})?|%{DATA:rawrequest})\" %{NUMBER:http_status_code} (?:%{NUMBER:bytes}|-) \"%{GREEDYDATA:sessionId}\" \"(?:%{SPACE}HTTP/(%{NUMBER:http_versionAnother})?|%{DATA:rawrequestAnother})\"" }
        }
}

%{IP:clientip} (?:-|(%{WORD}.%{WORD})) (?:-|(%{WORD}.%{WORD})) \[%{HTTPDATE:timestamp}\] %{WORD:method} %{URIPATHPARAM:request} (?:%{SPACE}HTTP/(%{NUMBER:http_version})?|%{DATA:rawrequest}) %{NUMBER:http_status_code} (?:%{NUMBER:bytes}|-) %{SPACE}%{GREEDYDATA:sessionId} (?:%{SPACE}HTTP/(%{NUMBER:http_versionAnother})?|%{DATA:rawrequestAnother})

7a49868c-b144-485a-ada4-b27b1544d7f7
