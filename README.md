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

