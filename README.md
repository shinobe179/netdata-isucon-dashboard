# netdata-isucon-dashboard
Netdata dashboard for ISUCON

![image](https://cdn-ak.f.st-hatena.com/images/fotolife/b/befs_anne/20200907/20200907004027.png)

# Prerequisites
You have already installed Netdata to your local machine and servers.

# How to Use

```
# clone this repo
git clone https://github.com/shinobe179/netdata-isucon-dashboard

# copy isucon.html
sudo cp -p netdata-isucon-dashboard/isucon.html /usr/share/netdata/web/isucon.html
sudo chown netdata:netdata /usr/share/netdata/web/isucon.html

# connect ssh port-forwarding

## for server-a
ssh -L 29999:localhost:19999 server-a

## for server-b
ssh -L 39999:localhost:19999 server-b

## for server-c
ssh -L 49999:localhost:19999 server-c
```

...and browze `http://localhost:19999/isucon.html`.
