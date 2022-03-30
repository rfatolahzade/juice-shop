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

Run this command to add cert to your DNS's (Change the E-mail address - Your Domains) :
```bash
./acme.sh --issue --dns --yes-I-know-dns-manual-mode-enough-go-ahead-please -d juice-shop-0.net -d juice-shop-1.net -m ramin.fathollahzadeh@gmail.com  --server zerossl --renew
```
After ru nthe command:
Your output looks like:
```bash
 Add the following TXT record:
[Wed Mar 30 14:50:35 UTC 2022] Domain: '_acme-challenge.juice-shop-0.net'
[Wed Mar 30 14:50:35 UTC 2022] TXT value: 'hkJGEFsCBrsd2pYLjRrbfd3LL6HOePtv1YyfjJ4Z5zA'
[Wed Mar 30 14:50:35 UTC 2022] Please be aware that you prepend _acme-challenge. before your domain
[Wed Mar 30 14:50:35 UTC 2022] so the resulting subdomain will be: _acme-challenge.juice-shop-0.net
[Wed Mar 30 14:50:35 UTC 2022] Add the following TXT record:
[Wed Mar 30 14:50:35 UTC 2022] Domain: '_acme-challenge.juice-shop-1.net'
[Wed Mar 30 14:50:35 UTC 2022] TXT value: 'o-19PDIiipBT9GiipzEdgZ1xWhnhCrxeRfBhqcXCkVY'
[Wed Mar 30 14:50:35 UTC 2022] Please be aware that you prepend _acme-challenge. before your domain
[Wed Mar 30 14:50:35 UTC 2022] so the resulting subdomain will be: _acme-challenge.juice-shop-1.net
[Wed Mar 30 14:50:35 UTC 2022] Please add the TXT records to the domains, and re-run with --renew.
```
Add the Domain with TXT value to your DNS list and then run:
```bash
./acme.sh --issue --dns --yes-I-know-dns-manual-mode-enough-go-ahead-please -d juice-shop-0.net -d juice-shop-1.net -m ramin.fathollahzadeh@gmail.com
```

