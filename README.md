# PAN-OS Upgrade / Downgrade Playbook

This playbook will perform the proper upgrade / downgrade sequence in order
to arrive at the desired software version.

# Usage

Edit the defaults/main.yml file to set the `desired_version` and PAN-OS authentication
information. You may also set the variables via CLI / Extra args. 

```bash

ansible-playbook -i inventory.yml ./manage_panos_software.yml -e 'desired_version=9.0.11' -e 'ip_address=10.10.10.131' -e 'username=admin' -e 'password=HI THERE!'

```