# SSL

## Create self-signed SSL Certificate
- also see:
  - <https://www.akadia.com/services/ssh_test_certificate.html>
  - <https://devcenter.heroku.com/articles/ssl-certificate-self#generate-ssl-certificate>

``` bash
# generate private key
openssl genrsa -des3 -out server.pass.key 2048

# remove passphrase from Key
openssl rsa -in server.pass.key -out server.key
rm server.pass.key

# generate csr (certificate signing request)
openssl req -new -key server.key -out server.csr

# generate self-signed certificate
openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt
```
