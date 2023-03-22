# check if a server certificate is valid/trusted by the client
openssl s_client -proxy proxy.example.de:3128 -showcerts -connect my.example.net:443


# connect to a server using openssl
openssl s_client -connect  my.example.net:443

# get a server cert and show store it in a .pem file
openssl s_client -showcerts -connect my.example:443 </dev/null 2>/dev/null|openssl x509 -outform PEM > mycertfile.pem
## show the certificates in human readable way
openssl x509 -in mycertfile.pem -text