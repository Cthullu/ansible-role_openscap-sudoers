# openscap-sudoers

An Ansible role which applies sudoers configuration according to the openSCAP rules.

More information regarding the openSCAP can be found [here]([http://static.open-scap.org/).

## Requirements

This role has been tested at a virtualized Ubuntu 20.04 LTS with Ansible Core 2.12.

## Role Variables

This role has 5 variables which can be used to configure the behaviour.

    # (string) The path of the logfile which should track sudo acitivities.
    var_sudo_logfile

    # (boolean) Configure if logrotate should send the rotated sudoers logfile by mail.
    var_send_sudoers_log_mail

    # (string) The account which should recieve the send logfile via mail.
    var_logrotate_sudoers_mail_address

    # (int) The amount of logfiles which should be kept by logrotate before deletion.
    var_log_rotate_amount

    # (string) The interval used by logrotate. Must be one of [daily, weekly, yearly].
    var_log_rotate_interval

## Example Playbooks

### Send mail to account of user foo

    - hosts: servers
      vars:
        var_logrotate_sudoers_mail_address: foo
      roles:
         - role: openscap-sudoers

### Send no mail

    - hosts: servers
      vars:
        var_send_sudoers_log_mail: false
      roles:
         - role: openscap-sudoers

## License

MIT

## Author Information
Author: Daniel Kuß
