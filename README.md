# Certbot Ansible Role

This role installs and configures Certbot.

## Requirements

* Ansible 2.6+

## Role Variables

``` yaml
# Registration options
#
# If email is left blank and TOS is accepted,
# account will be registered using --register-unsafely-without-email 
certbot_email: ~
certbot_agree_tos: false
certbot_eff_email: false

# Renewal options
certbot_pre_hook: ""
certbot_post_hook: ""
certbot_deploy_hook: ""
certbot_args: ""

# Enable auto-renewal system timer?
certbot_enable_timer: true
```

## Dependencies

None.

## Example Playbook

``` yaml
- hosts: localhost
  roles:
  - rchouinard.certbot
  vars:
    certbot_email: tlsadmin@example.com
    certbot_agree_tos: true
    certbot_post_hook: systemctl reload nginx.service
```

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
