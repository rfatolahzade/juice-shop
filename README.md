# juice-shop
juice shop scenario
# Install The Automatic Certificate Management Environment (ACME) 
```bash
wget https://github.com/rfinland/acme.sh/archive/refs/tags/acme.zip
apt install zip unzip
unzip acme.zip
cd acme.sh-acme
```

#Install nginx 
```bash
apt install nginx -y
```
#curl the server
```bash
http://185.235.43.181/
```
If the nginx web page doesnt show, make sure the port 80 is open:
```bash
ufw allow from any to any port 80
```