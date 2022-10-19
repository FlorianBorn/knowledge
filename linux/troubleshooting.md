**Does an email domain exist?**  
nslookup -q=MX <domain>  
*Example*  
```
root@localhost:~ $ nslookup -q=MX google.de
Server:         172.29.148.90
Address:        172.29.148.90#53

Non-authoritative answer:
google.de       mail exchanger = 0 smtp.google.com.

Authoritative answers can be found from:
google.de       nameserver = ns2.google.com.
google.de       nameserver = ns3.google.com.
google.de       nameserver = ns4.google.com.
google.de       nameserver = ns1.google.com.
ns1.google.com  internet address = 216.239.32.10
ns2.google.com  internet address = 216.239.34.10
ns3.google.com  internet address = 216.239.36.10
ns4.google.com  internet address = 216.239.38.10
ns1.google.com  has AAAA address 2001:4860:4802:32::a
ns2.google.com  has AAAA address 2001:4860:4802:34::a
ns3.google.com  has AAAA address 2001:4860:4802:36::a
ns4.google.com  has AAAA address 2001:4860:4802:38::a

```