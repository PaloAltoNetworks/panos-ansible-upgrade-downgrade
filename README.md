# PAN-OS Upgrade/Downgrade and Licensing Playbooks

## Full Upgrade/Downgrade Playbook

This playbook will:

    * Activate and fetch licenses for the NGFW using an auth-code
    * Download and install the latest threat and AV content updates
    * Perform the proper upgrade/downgrade sequence in order to arrive at the desired software version

### Usage with Ansible

Edit the defaults/main.yml file to set the following variables: 

1. PAN-OS authentication information (`ip_address`, `username`, and `password`)
2. Auth-code, if NGFW is not already licensed
3. End-state `desired_version` of PAN-OS
4. Content Update options
   
    a. `update_contet` (yes/no)
   
    b. `force_update_content` (yes/no)
   
    c. `update_av` (yes/no)

You may also set the variables via CLI / Extra args. 

```bash
  ansible-playbook -i inventory.yml ./manage_panos_software.yml -e 'desired_version=9.0.11' -e 'ip_address=10.10.10.131' -e 'username=admin' -e 'password=HI THERE!' ...
```

### Usage with Skillet Players

In addition, this playbook can be run as a skillet using PanHandler (or other skillet players, such as SLI). Once this repository
is imported into PanHandler, you can find the **PAN-OS Full Upgrade / Downgrade** *docker* skillet in the **Deployment Tools** Skillet Collection.



## License Activation Playbook

This playbook will:

    * Activate and fetch licenses for the NGFW using an auth-code

### Usage with Ansible

Edit the defaults/main.yml file to set the following variables: 

1. PAN-OS authentication information (`ip_address`, `username`, and `password`)
2. Auth-code, if NGFW is not already licensed

You may also set the variables via CLI / Extra args. 

```bash
  ansible-playbook -i inventory.yml ./activate_licenses.yml -e 'ip_address=10.10.10.131' -e 'username=admin' -e 'password=HI THERE!' -e 'auth_code=SOMECODEHERE'
```

### Usage with Skillet Players

In addition, this playbook can be run as a skillet using PanHandler (or other skillet players, such as SLI). Once this repository
is imported into PanHandler, you can find the **PAN-OS Activate License** *docker* skillet in the **Deployment Tools** Skillet Collection.



## Full Content Update Playbook

This playbook will:

    * Download and install the latest threat and AV content updates

### Usage with Ansible

Edit the defaults/main.yml file to set the following variables: 

1. PAN-OS authentication information (`ip_address`, `username`, and `password`)

You may also set the variables via CLI / Extra args. 

```bash
  ansible-playbook -i inventory.yml ./perform_content_update.yml -e 'ip_address=10.10.10.131' -e 'username=admin' -e 'password=HI THERE!' 
```

### Usage with Skillet Players

In addition, this playbook can be run as a skillet using PanHandler (or other skillet players, such as SLI). Once this repository
is imported into PanHandler, you can find the **PAN-OS Content Update** *docker* skillet in the **Deployment Tools** Skillet Collection.



## License Activation Playbook

This playbook will:

    * Set the licensing API key on your PAN-OS, if not already set
    * Deactivate all licenses automatically 

### Usage with Ansible

Edit the defaults/main.yml file to set the following variables: 

1. PAN-OS authentication information (`ip_address`, `username`, and `password`)
2. Customer Support Portal Licensing API Key

You may also set the variables via CLI / Extra args. 

```bash
  ansible-playbook -i inventory.yml ./deactivate_licenses.yml -e 'ip_address=10.10.10.131' -e 'username=admin' -e 'password=HI THERE!' -e 'api_key=SOMEKEYHERE'
```

### Usage with Skillet Players

In addition, this playbook can be run as a skillet using PanHandler (or other skillet players, such as SLI). Once this repository
is imported into PanHandler, you can find the **PAN-OS Deactivate License** *docker* skillet in the **Deployment Tools** Skillet Collection.


