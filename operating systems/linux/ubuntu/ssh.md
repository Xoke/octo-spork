# Things to do generally

## SSH
- Make sure you can't ssh in as root (connect as a user then sudo to root!)
- vim /etc/ssh/sshd_config
- Look for PermitRootLogin yes
- Change to PermitRootLogin no
- :wq to **w**rite and **q**uit

## Install fail2ban
- apt install fail2ban
- [optional, if you want mail - apt install sendmail]
- ufw allow ssh
- ufw enable
- cp /etc/fail2ban/fail2ban.conf /etc/fail2ban/fail2ban.local
- vim /etc/fail2ban/fail2ban.local
- cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
- vim /etc/fail2ban/jail.local
- Check it is working with
  - fail2ban-client status

### Taken from the following pages
- [Fail2ban](https://www.linode.com/docs/security/using-fail2ban-for-security#ubuntu)
