# Squid_Auth_Kerberos

## 1-Changing Hostnames
We start by executing this command
```
hostnamectl --static set-hostname kdc.insat
```
![Changing Hostname](images/ips_hostnames/KDC/hostname.png)

We do this step for the 2 other machines (service and client machines).

![Changing Hostname](images/ips_hostnames/Service/hostname.png)

![Changing Hostname](images/ips_hostnames/Client/hostname.png)

## 2- Getting IP Adresses