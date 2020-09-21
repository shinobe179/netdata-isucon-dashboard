# netdata-isucon-dashboard
Netdata dashboard for ISUCON

![image](https://cdn-ak.f.st-hatena.com/images/fotolife/b/befs_anne/20200907/20200907004027.png)

# Prerequisites
You have already installed Netdata to your local machine and servers.

# How to Use

## on monitored server

```
# clone this repo
git clone https://github.com/shinobe179/netdata-isucon-dashboard

# copy files
sudo cp -p netdata-isucon-dashboard/go.d/mysql.conf /etc/netdata/go.d/mysql.conf

# restart netdata to load mysql.conf
sudo systemctl restart netdata
```

## on monitoring server

```
# clone this repo
git clone https://github.com/shinobe179/netdata-isucon-dashboard

# copy files
sudo cp -p netdata-isucon-dashboard/isucon.html /usr/share/netdata/web/isucon.html
sudo cp -p netdata-isucon-dashboard/isucon_mysql.html /usr/share/netdata/web/isucon_mysql.html
sudo cp -p netdata-isucon-dashboard/isucon.css /usr/share/netdata/web/isucon.css
sudo chown netdata:netdata /usr/share/netdata/web/isucon.html
sudo chown netdata:netdata /usr/share/netdata/web/isucon_mysql.html
sudo chown netdata:netdata /usr/share/netdata/web/isucon.css

# connect ssh port-forwarding

## for server-a
ssh -L 29999:localhost:19999 server-a

## for server-b
ssh -L 39999:localhost:19999 server-b

## for server-c
ssh -L 49999:localhost:19999 server-c
```

...and browse `http://localhost:19999/isucon.html`.
