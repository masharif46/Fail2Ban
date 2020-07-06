# Fail2Ban
Install Fail2Ban on CentOS 7

yum install epel-release

yum install fail2ban fail2ban-systemd

yum update -y selinux-policy*

cp -pf /etc/fail2ban/jail.conf /etc/fail2ban/jail.local  or  upload jail.local file in /etc/fail2ban/


systemctl enable firewalld
systemctl start firewalld

systemctl enable fail2ban
systemctl start fail2ban 


Tracking Failed login entries 

cat /var/log/secure | grep 'Failed password'

