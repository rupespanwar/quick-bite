# file location
         $ ls -l /etc/ssh
        total 96
        -rw-r--r--  1 root  wheel  577388 Jan  1  2020 moduli
        -rw-r--r--  1 root  wheel    1511 Jan  1  2020 ssh_config < client
        -rw-r--r--  1 root  wheel    3169 Jan  1  2020 sshd_config < daemon
- read more about ssh
- man sshd_config
- search => /Allow

# ssh hardening
- port 2278
<img width="278" alt="image" src="https://user-images.githubusercontent.com/75510135/129907105-9c66226e-a396-4125-9e9e-e7f61bede3e1.png">
- Permit root login => no
- Allow only limited users
<img width="331" alt="image" src="https://user-images.githubusercontent.com/75510135/129907648-eb59422d-0c23-4225-a615-f5c6e31ea24a.png">
- Allow specific IP Range, sudo su
<img width="711" alt="image" src="https://user-images.githubusercontent.com/75510135/129907917-57c070d6-ccdc-431d-a5ef-7e49c1536ee0.png">
- limit the time interval for client and attempts
<img width="206" alt="image" src="https://user-images.githubusercontent.com/75510135/129908298-271deb6f-99b6-4b6e-a517-fa5a5670cdd2.png">
# Summary

## OpenSSH

 
# 1. Installing OpenSSH (client and server)
# Ubuntu
        sudo apt update && sudo apt install openssh-server openssh-client
 
# CentOS
        sudo dnf install openssh-server openssh-clients
 
# connecting to the server
        ssh -p 22 username@server_ip        # => Ex: ssh -p 2267 john@192.168.0.100
        ssh -p 22 -l username server_ip
        ssh -v -p 22 username@server_ip     # => verbose
 
# 2. Controlling the SSHd daemon
# checking its status
        sudo systemctl status ssh       # => Ubuntu
        sudo systemctl status sshd      # => CentOS
 
# stopping the daemon
        sudo systemctl stop ssh       # => Ubuntu
        sudo systemctl stop sshd      # => CentOS
 
# restarting the daemon
        sudo systemctl restart ssh       # => Ubuntu
        sudo systemctl restart sshd      # => CentOS
 
# enabling at boot time 
        sudo systemctl enable ssh       # => Ubuntu
        sudo systemctl enable sshd      # => CentOS

        sudo systemctl is-enabled ssh       # => Ubuntu
        sudo systemctl is-enabled sshd      # => CentOS
 
# 3. Securing the SSHd daemon
# change the configuration file (/etc/ssh/sshd_config) and then restart the server
man sshd_config
 
a) Change the port
Port 2278
 
b) Disable direct root login
PermitRootLogin no
 
c) Limit Users’ SSH access
AllowUsers stud u1 u2 john
 
d) Filter SSH access at the firewall level (iptables)
 
e) Activate Public Key Authentication and Disable Password Authentication
 
f) Use only SSH Protocol version 2
 
g) Other configurations:
```
                ClientAliveInterval 300
                ClientAliveCountMax 0
                MaxAuthTries 2
                MaxStartUps 3
                LoginGraceTime 20
 ```
