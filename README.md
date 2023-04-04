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
Now we need to get the IP Adresses of all the three machines. We can use this command to do that
```
hostname -I
```
![Displaying IP](images/ips_hostnames/KDC/ip.png)

![Displaying IP](images/ips_hostnames/Service/ip.png)

![Displaying IP](images/ips_hostnames/Client/ip.png)

Note : All 3 machines need to have a Host-only Adapter.

## 3-Adding IP Adresses in /etc/hosts files

The next step is to add the IP adresses of the three machines in /etc/hosts files.
We execute this command : 
```
sudo nano /etc/hosts
```
and we add these 3 lines in the /etc/hosts file for all of 3 machines
```
192.168.56.129  kdc.insat.tn kdc
192.168.56.128  service.insat.tn service
192.168.56.130  client.insat.tn client
```

![Changing /etc/hosts](images/etc_hosts/etc_hosts.png)

Now we can test our configuration by executing for example in kdc machine:
```
nslookup service
ping service
```
![Ping](images/etc_hosts/ping1.png)

and in service machine: 
```
nslookup kdc
ping kdc
```
![Ping](images/etc_hosts/ping2.png)