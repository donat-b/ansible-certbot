Certbot
=======

Installs certbot on Ubuntu Trusty (and newer), configures
a cron job with renewal command and deploys the script to fetch certificates.

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
    server_name:
      - 'example.com'
      - 'www.example.com'
      - 'foo.example.com'
      - 'bar.example.com'
    lb_method  : 'least_conn'
    certbot    : true
    upstreams  :
      - 10.1.250.2
      - 10.1.250.3
      - 10.1.250.4
```

Usage
-----

- Set `certbot_email` to your email and other variables if necessary
- Install certbot and scripts by running playbook
- Obtain certificates with the certbot-certonly command
- Done! Following certificate renewal will be handled by the cron job

Debian
------

For Debian installation, use automated install script by EFF:
https://certbot.eff.org/all-instructions/#debian-7-wheezy-nginx

License
-------

BSD
