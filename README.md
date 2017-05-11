Certbot
=======

Installs certbot on Ubuntu hosts and sets up a renewal cron job.
Certificates should be obtained first using the certbot-certonly command which
uses frontlb_servers or nginx_servers dicts from `nginx` role.

Requirements
------------

None

Role Variables
--------------

```yaml
certbot_authenticator: 'webroot'
certbot_cmd          : 'certbot'
certbot_email        : 'email@example.com'
certbot_etc_path     : '/etc/letsencrypt'
certbot_rsa_key_size : '4096'
certbot_webroot      : '/var/www/certbot'
```

Example configuration
---------------------

```yaml
frontlb_servers:
  - name       : 'example.com'
    server_name: 'www.example.com'
    lb_method  : 'least_conn'
    certbot    : true
    upstreams  :
      - 10.1.250.2
      - 10.1.250.3
      - 10.1.250.4
```

Debian
------

For Debian installation, use automated install script by EFF:
https://certbot.eff.org/all-instructions/#debian-7-wheezy-nginx

License
-------

BSD
