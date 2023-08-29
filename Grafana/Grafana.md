# Install Grafana
## 1. Install dependency foir grafana
~~~
sudo apt install libfontconfig
~~~
## Go to oficial web server 
~~~
https://grafana.com/grafana/download
~~~
## Look for instruction for Linux
~~~
wget https://dl.grafana.com/enterprise/release/grafana-enterprise_10.1.0_amd64.deb
~~~
## And use dockumentatin instruction
~~~
sudo dpkg -i grafana-enterprise_10.1.0_amd64.deb
~~~
## 2. Enable service
~~~
sudo systemctl daemon-reload
~~~
~~~
sudo systemctl enable grafana-server
~~~
~~~
sudo systemctl start grafana-server
~~~

