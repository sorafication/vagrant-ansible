# vagrant-ansible
With this Repo you create a debian VM, install ansible and configure the vm with ansible.
You only need to have the Vagrantfile downloaded and it will itself download all the Ansible Config files from Github.


Self-installing linux-vm with vagrant and self-configuration with ansible.


## Installation

1. Install [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Vagrant](https://vagrantup.com).
3. Install the required Vagrant plugins:
    
    ```shell
    $ vagrant plugin install vagrant-hosts-provisioner
    $ vagrant plugin install vagrant-hosts
    ```
    
### Configuration

1. Copy Vagrantfile 
2. Change the Repository URL to your own. You can fork this project or just use my Repo Url.
3. If desired you can change the Ansible Configuration. Some things are already set as variables (/vars/all.yml) for easy change. 

#### Start your VM

```shell
    $ vagrant up
```
