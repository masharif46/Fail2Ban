
# Fail2Ban

###
Fail2ban is an open-source software that actively scans the servers log files in real-time for any brute force login attempts, and if found, summarily blocks the attack using the servers firewall software (firewalld or iptables). Fail2Ban runs as a background process and continuously scans the log files for unusual login patterns and security breach attempts 
###

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


Checking the banned IPs by Fail2Ban

iptables -L -n

Check the Fal2Ban Status

fail2ban-client status


Unbanning an IP address

fail2ban-client set sshd unbanip IPADDRESS

------------------Thanks you ------------------
