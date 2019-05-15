## Ansible Notes
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQKj-00Z9LYlW1duGjVUKx7ifnKN40NvWPBk99Jf-iPEoA16Usa" alt="Image result for ansible icon" class="confluence-embedded-image confluence-external-resource" width="100" /></span>

Installed Ansible to virtualenv 



    `pip install ansible`


**ansible.cfg**

The Ansible configuration file is /etc/ansible/ansible.cfg

It can be edited at a global level or maintained at a playbook level
config file. Use a playbook level config file. 

Recommended config changes.
```
    gathering = explicit # runs the setup module on the host, disable for network oriented playbooks
    inventory = inv.yml  # inventory file, default is hosts with no extension
    retry_files_enabled = False # files that list failed hosts
    host_key_checking = False  # feeling lucky punk?
```
The config file search order:

-   `ANSIBLE_CONFIG`<span> </span>(environment variable if set)
-   `ansible.cfg`<span> </span>(in the current directory)
-   `~/.ansible.cfg`<span> </span>(in the home directory)
-   `/etc/ansible/ansible.cfg`

Ansible will process the above list
and use the first file found, all others are ignored.


**inv.yml**


    ---
    all:
      children:
          routers:
         switches:
        firewalls:
            hosts:
              R1:
              R2:

    # The yaml format is superior to using the INI format
    # INI format
    # [routers]
    # R1
    # R2



variables - create a directory named group\_vars

files routers.yml

"username and password needs moved out of the code"

**routers.yml**

    ---
    ansible_network os: "ios"
    ansible_user: "username"
    ansible_password: "password"



**switches.yml**

    ---
    ansible_network os: "ios"
    ansible_user: "username"
    ansible_password: "password"



**firewalls.yml**

    ---
    ansible_network os: "ios"
    ansible_user: "username"
    ansible_password: "password"

|---- ansible.cfg

|---- group\_vars

       |----- routers.yml

|---- inv.yml



Ansible documentation

**firewalls.yml**

    ansible-doc ios_command



In Ansible you can reference dictionary keys using dot notation
cli\_result.stdout or using python notation such as
cli\_result\['stdout'\]

dot notion is more compact

To format the JSON output into native config format

**firewalls.yml**

    cli_result.stdout[0] or cli_result['stdout'][0]



Network Authentication

You can use Ansible environment varialbes 

**firewalls.yml**

    export ANSIBLE_NET_USERNAME=cisco
    export ANSIBLE_NET_PASSWORD=cisco



They can be stored in .ansible.env file and then run to add then to the
enviroment

**firewalls.yml**

    source .ansible.env
