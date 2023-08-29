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
## 5. Unarhive files
~~~
tar -xvf <file.tar>
~~~
## 6. Now we go to the unarchive folder and move nessesery files to folder
~~~
sudo mv console* /etc/prometheus/
~~~
~~~
sudo mv prometheus.yml /etc/prometheus/
~~~
## And give an permission to owner
~~~
sudo chown -R prometheus:prometheus /etc/prometheus/
~~~
## 7. We need move bineris to folder /user/local/bin/
~~~
sudo mv prometheus /usr/local/bin/
~~~
~~~
sudo mv promtool /usr/local/bin/
~~~
## And give an permisiion 
~~~
sudo chown prometheus:prometheus /usr/local/bin/prom*
~~~
## 8. Create service file for prometheus
~~~
sudo vim /etc/systemd/system/prometheus.service
~~~
## And write commands to this file
~~~
[Unit]
        Description=Prometheus
        Wants=network-online.target
        After=network-online.target

        [Service]
        User=prometheus
        Group=prometheus
        Type=simple
        ExecStart=/usr/local/bin/prometheus \
            --config.file /etc/prometheus/prometheus.yml \
            --storage.tsdb.path /var/lib/prometheus/ \
            --web.console.templates=/etc/prometheus/consoles \
            --web.console.libraries=/etc/prometheus/console_libraries

        [Install]
        WantedBy=multi-user.target
~~~
