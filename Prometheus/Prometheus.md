# Install Prometheus
## 1. Need to create user prometheus withot home directory, 
and we will setup directory to /bin/false
~~~
sudo useradd --no-create-home --shell /bin/false prometheus
~~~
## 2. Now we need create folders for prometheus
~~~
sudo mkdir /etc/prometheus
~~~
## Another folder for library 
~~~
sudo mkdir /var/lib/prometheus
~~~
## 3. Now we need add to this folders owner prometheus
~~~
sudo chown prometheus:prometheus /var/lib/prometheus
~~~
## 4. Dowload Prometheus
## Oficial website 
~~~
https://prometheus.io/download/
~~~
## command
~~~
wget https://github.com/prometheus/prometheus/releases/download/v2.46.0/prometheus-2.46.0.linux-amd64.tar.gz
~~~
