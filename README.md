# ansible-role-chrony

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-chrony.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-chrony)

RHEL/CentOS - Network Time Protocol daemon (chrony)

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    chrony_commands:
      driftfile: /var/lib/chrony/drift
      logdir: /var/log/chrony
      makestep: '1.0 3'
      rtcsync: True
      server:
        - 0.centos.pool.ntp.org iburst
        - 1.centos.pool.ntp.org iburst
        - 2.centos.pool.ntp.org iburst
        - 3.centos.pool.ntp.org iburst
    chrony_sysconfig: ''

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.chrony
          chrony_commands:
            allow:
              - 10.0.0.0/8
              - 172.16.0.0/12
              - 192.168.0.0/16
            hwtimestamp: '*'
            keyfile: /etc/chrony.keys
            log: 'measurements statistics tracking'
            driftfile: /var/lib/chrony/drift
            logdir: /var/log/chrony
            makestep: '1.0 3'
            minsources: 2
            rtcsync: True
            server:
              - 0.centos.pool.ntp.org iburst
              - 1.centos.pool.ntp.org iburst
              - 2.centos.pool.ntp.org iburst
              - 3.centos.pool.ntp.org iburst
          chrony_sysconfig: '-F 1'

## License

GPLv3

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
