# 3x-ui-Tutorial
# Install & Update 
    bash <(curl -Ls https://raw.githubusercontent.com/mhsanaei/3x-ui/master/install.sh)
# Install Legacy Version
    VERSION=v2.6.6 && bash <(curl -Ls "https://raw.githubusercontent.com/mhsanaei/3x-ui/$VERSION/install.sh") $VERSION
# Configure your firewall with the following commands
    sudo ufw allow 1:443/tcp
    sudo ufw allow 1:8080/udp
    sudo ufw enable
# SSL Certificate

To install and use Certbot:

```
apt-get install certbot -y
sudo certbot certonly --standalone -d yourdomain.com
certbot renew --dry-run
```
# **Clone the Project Repository:**
    git clone https://github.com/MHSanaei/3x-ui.git
    cd 3x-ui
    
# VPN Server Guide

## SSH Access Fix 
PuTTy နဲ့ ဝင်မရရင် ဒါတွေလုပ်ပါ- ssh ထဲဝင်
* `nano /etc/ssh/sshd_config` ထဲဝင်
* `PermitRootLogin yes` ပြောင်း
* `PasswordAuthentication yes` ပြောင်း
* `systemctl restart ssh`
* `passwd` password အသစ်ပေးပြီးရင် PuTTy နဲ့ join ပြီးဝင်လို့ရပါပြီ

## Build Swap

Allocate the space first (1GB will be created)
```bash
sudo fallocate -l 1G /swapfile
```
Permission
```bash
sudo chmod 600 /swapfile
```
Change it to a Swap File
```bash
sudo mkswap /swapfile
```
Start using it
```bash
sudo swapon /swapfile
```

စက်ပိတ်ပြီးပြန်ဖွင့်ရင် အလိုအလျောက်အလုပ်လုပ်အောင်
```bash
echo '/swapfile none swap sw 0 0' | sudo tee -a /etc/fstab
``` 

အောင်မြင်မမြင်စစ်နည်း
```bash
free -h
```
## Cron Job (Schedule a daily auto-cleanup for unnecessary logs)
### Automatically clear junk log files every day at midnight without deleting user usage records

Run Terminal (Press 1 if asked to choose an editor)
```bash
crontab -e
```
အောက်ဆုံးကြောင်းမှာ ရိုက်ထည့်ပါ
```bash
0 0 * * * rm -rf /var/log/*.log && rm -rf /var/log/x-ui/*.log && apt clean
```



