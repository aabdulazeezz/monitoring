### Install Prometheus

## 1. Create user prometheus without home-directory and set up directory to /bin/false
~~~
sudo useradd --no-create-home --shell /bin/false prometheus
~~~

## 2. Create folders for Prometheus
~~~
sudo mkdir /etc/prometheus
sudo mkdir /var/lib/prometheus
~~~
## 3. Add to this folder owner prometheus 
~~~
sudo chown prometheus:prometheus /var/lib/prometheus
~~~

