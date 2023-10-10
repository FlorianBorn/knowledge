# check if a server certificate is valid/trusted by the client
openssl s_client -proxy proxy.example.de:3128 -showcerts -connect my.example.net:443


# connect to a server using openssl
openssl s_client -connect  my.example.net:443

# get a server cert and show store it in a .pem file
```
# do not type the protocol with the connect param, but the port must be set
openssl s_client -showcerts -connect my.example:443 </dev/null 2>/dev/null|openssl x509 -outform PEM > mycertfile.pem
```
## show the certificates in human readable way
openssl x509 -in mycertfile.pem -text

# show the ssl/tls handshake with openssl
openssl s_client -state -nbio  -connect my.example.net:443

# How to: Download a certificate chain with openssl
See: https://unix.stackexchange.com/questions/368123/how-to-extract-the-root-ca-and-subordinate-ca-from-a-certificate-chain-in-linux

# Troubleshooting
## curl: (1) Received HTTP/0.9 when not allowed
Führe curl mit http0.9 handling aus
curl -vvv  my.example.net:443 --http0.9 --output -
https://stackoverflow.com/questions/59048926/php-curl-received-http-0-9-when-not-allowed