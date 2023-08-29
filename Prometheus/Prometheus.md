# Install Prometheus
## 1. Need to create user prometheus withot home directory, 
and we will setup directory to /bin/false
~~~
sudo useradd --no-create-home --shell /bin/false prometheus
~~~
