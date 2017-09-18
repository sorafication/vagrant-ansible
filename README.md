# vagrant-ansible
With this Repo you create a debian VM, install ansible and configure the vm with ansible.


Self-installing linux-vm with vagrant and self-configuration with ansible.


## Installation

1. Install [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Vagrant](https://vagrantup.com).
3. Install the required Vagrant plugins:
    
    ```shell
    $ vagrant plugin install vagrant-hosts-provisioner
    $ vagrant plugin install vagrant-hosts
    ```
    
### Copy Files

1. Copy Vagrantfile and ansible folder to your "VirtualBox VMs" folder.
2. Configure Vagrantfile or playbook if you like to.

#### Start your VM

```shell
    $ vagrant up
    ```



Information: This Repo is currently only configured for my own workspace. There is my Public-Key, my preferred configuration for zsh,vim,git etc and so on.
You would need to change these to your parameteres if you would like to use it.
