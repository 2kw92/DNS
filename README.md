# DNS
дз Otus по теме split-dns


Для проверки дз необходимо склонироваь репозиторий себе.        
Потом запустить Vagrantfile,который поднимет всю необходимую структуру.       

После того как стенд развернется необходимо зайти на client и там         
выполнить следующие команды:

```
[root@client ~]# nslookup dns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   dns.lab
Address: 192.168.50.11
Name:   dns.lab
Address: 192.168.50.10

[root@client ~]# nslookup web1.dns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

Name:   web1.dns.lab
Address: 192.168.50.15

[root@client ~]# nslookup web1.dns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   web1.dns.lab
Address: 192.168.50.15

[root@client ~]# nslookup web2.dns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

** server can't find web2.dns.lab: NXDOMAIN

[root@client ~]# nslookup web2.dns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

** server can't find web2.dns.lab: NXDOMAIN

[root@client ~]# nslookup newdns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

Name:   newdns.lab
Address: 192.168.50.10
Name:   newdns.lab
Address: 192.168.50.11

[root@client ~]# nslookup newdns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   newdns.lab
Address: 192.168.50.11
Name:   newdns.lab
Address: 192.168.50.10

[root@client ~]# nslookup www.newdns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

Name:   www.newdns.lab
Address: 192.168.50.15

[root@client ~]# nslookup www.newdns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   www.newdns.lab
Address: 192.168.50.15
```         

Заходим на client2 и там выполняем:        
```
[root@client2 ~]# nslookup dns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

Name:   dns.lab
Address: 192.168.50.11
Name:   dns.lab
Address: 192.168.50.10

[root@client2 ~]# nslookup dns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   dns.lab
Address: 192.168.50.11
Name:   dns.lab
Address: 192.168.50.10

[root@client2 ~]# nslookup web1.dns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

Name:   web1.dns.lab
Address: 192.168.50.15

[root@client2 ~]# nslookup web1.dns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   web1.dns.lab
Address: 192.168.50.15

[root@client2 ~]# nslookup web2.dns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

Name:   web2.dns.lab
Address: 192.168.50.16

[root@client2 ~]# nslookup web2.dns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

Name:   web2.dns.lab
Address: 192.168.50.16

[root@client2 ~]# nslookup newdns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

** server can't find newdns.lab: NXDOMAIN

[root@client2 ~]# nslookup newdns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

** server can't find newdns.lab: NXDOMAIN

[root@client2 ~]# nslookup www.newdns.lab 192.168.50.10
Server:         192.168.50.10
Address:        192.168.50.10#53

** server can't find www.newdns.lab: NXDOMAIN

[root@client2 ~]# nslookup www.newdns.lab 192.168.50.11
Server:         192.168.50.11
Address:        192.168.50.11#53

** server can't find www.newdns.lab: NXDOMAIN
```        
На этом провера дз закончена.