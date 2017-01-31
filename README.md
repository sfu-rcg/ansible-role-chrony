# ansible-role-chrony

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-chrony.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-chrony)

RHEL/CentOS - Network Time Protocol daemon (chrony)

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    chrony_bindcmdaddress: [ '127.0.0.1', '::1' ]
    chrony_commandkey: 1
    chrony_driftfile: /var/lib/chrony/drift
    chrony_generatecommandkey: True
    chrony_keyfile: /etc/chrony.keys
    chrony_logchange: 0.5
    chrony_logdir: /var/log/chrony
    chrony_makestep: [ '10', '3' ]
    chrony_noclientlog: True
    chrony_rtcsync: True
    chrony_server:
      - 0.centos.pool.ntp.org
      - 1.centos.pool.ntp.org
      - 2.centos.pool.ntp.org
      - 3.centos.pool.ntp.org
    chrony_stratumweight: 0

Additional variables not defined by default

    chrony_allow:
      - 192.168/16
    chrony_local: 'stratum 10'
    chrony_log:
      - measurements
      - statistics
      - tracking

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.chrony

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
