# HAProxy

This page contains the instruction to build HAProxy Web server for use with Strudel Web

## Pre-requisite
- A server running Ubuntu 18.04
- SSL certificate key file, SSL certificate, and SSL intermediate certificate

## Building haproxy
- `apt install haproxy`

## Setting up haproxy
1. Create the certificate PEM file by appending the contents of the key, certificate, and intermediate cerficate in this order. For example:
```
-----BEGIN RSA PRIVATE KEY----- 
(Your Private Key: server.key) 
-----END RSA PRIVATE KEY----- 
-----BEGIN CERTIFICATE----- 
  (Your Primary SSL certificate: server.crt)
-----END CERTIFICATE-----  -----BEGIN CERTIFICATE----- 
(Your Intermediate certificate) 
-----END CERTIFICATE----- 
```
Put this file in `/etc/ssl/private` directory.
2. Create `/etc/haproxy/crtlist.txt` with the path to the PEM file, for example:
`/etc/ssl/private/certificate.pem`
3. Configure `/etc/haproxy/haproxy.cfg` with the frontends and backends pointing to the Strudel Web instance, for example::
```
frontend strudel_web_frontend_http
        bind 0.0.0.0:80
        reqadd X-Forwarded-Proto:\ http
        redirect scheme https code 301 if !{ ssl_fc }

frontend strudel_web_frontend_https
        bind 0.0.0.0:443 ssl crt-list /etc/haproxy/crtlist.txt
        reqadd X-Forwarded-Proto:\ https
        default_backend strudel_web_backend

backend strudel_web_backend
        balance roundrobin
        cookie SERVERID insert indirect nocache
        server www-0 12.34.56:443 weight 1 check ssl verify none check cookie www-0
```
4. Restart haproxy: `systemctl restart haproxy`
        


