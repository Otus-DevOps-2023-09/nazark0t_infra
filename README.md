# nazark0t_infra
nazark0t Infra repository

hw3. Part1
1. ssh -o ProxyCommand="ssh -W %h:%p <bastion ip> -l <login>" <destination ip> -l <login>
	ssh -o ProxyCommand="ssh -W %h:%p 158.160.42.23 -l appuser" 10.128.0.31 -l appuser
2. Additional.
	alias someinternalhost='ssh -o ProxyCommand="ssh -W %h:%p 158.160.42.23 -l appuser" 10.128.0.31 -l appuser'
		or  better add this alias to  ~/.bashrc and restart session.


hw3. Part2

bastion_IP = 158.160.42.23
someinternalhost_IP = 10.128.0.31


Additional

sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install certbot

sudo systemctl stop mongod pritunl

sudo certbot certonly --standalone


Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator standalone, Installer None
Please enter in your domain name(s) (comma and/or space separated)  (Enter 'c'
to cancel): 158.160.42.23.nip.io
Obtaining a new certificate
Performing the following challenges:
http-01 challenge for 158.160.42.23.nip.io
Waiting for verification...
Cleaning up challenges

IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/158.160.42.23.nip.io/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/158.160.42.23.nip.io/privkey.pem
   Your cert will expire on 2024-01-29. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot
   again. To non-interactively renew *all* of your certificates, run
   "certbot renew"
 - If you like Certbot, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le


sudo systemctl restart mongod pritunl

open on
https://158.160.42.23.nip.io/login#dashboard
