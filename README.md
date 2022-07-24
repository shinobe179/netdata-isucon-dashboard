# netdata-isucon-dashboard
Netdata dashboard for ISUCON

![image](https://cdn-ak.f.st-hatena.com/images/fotolife/b/befs_anne/20200907/20200907004027.png)

# Prerequisites
You have already installed Netdata to your local machine and servers.

# HTML

- isucon.html
  - for monitoring compute resources and MySQL
- isucon_grid.html
  - for monitoring compute resource and MySQL, devided by CSS grid
- isucon_mysql.html
  - for monitoring MySQL

# How to Use

## on monitored server

```
# local machine
# send mysql.conf to monitored server
cd path/to/netdata-isucon-dashboard
scp go.d/mysql.conf isucon@isucon1:/tmp

# in monitored server
sudo cp -p /tmp/mysql.conf /etc/netdata/go.d/mysql.conf

# restart netdata to load mysql.conf
sudo systemctl restart netdata
```

## on monitoring server

```
# clone this repo
git clone https://github.com/shinobe179/netdata-isucon-dashboard

# copy files
sudo cp -p netdata-isucon-dashboard/isucon* 
sudo chown netdata:netdata /usr/share/netdata/web/isucon*

# connect ssh port-forwarding

ssh -L 29999:localhost:19999 isucon1 -fN && \
ssh -L 39999:localhost:19999 isucon2 -fN && \
ssh -L 49999:localhost:19999 isucon3 -fN
```

...and browse `http://localhost:19999/isucon.html`.

# Sharing the dashboard

You can share the dashboard by using Ngrok. Note that shared members also need SSH port-forwarding.

```
$ ngrok http 19999
```
