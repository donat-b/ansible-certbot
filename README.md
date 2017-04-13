# Certbot ansible role

Installs certbot on Ubuntu hosts and sets up a renewal cron job.
Certificates should be obtained first using the certbot-certonly command which
uses frontlb_servers dictionary from `nginx` role.

# Default variables

```yaml
certbot_authenticator: 'webroot'
certbot_cmd          : 'certbot'
certbot_etc_path     : '/etc/letsencrypt'
certbot_rsa_key_size : '4096'
certbot_webroot      : '/var/www/certbot'
```


# Debian

For Debian installation, use automated install script by EFF:
https://certbot.eff.org/all-instructions/#debian-7-wheezy-nginx
