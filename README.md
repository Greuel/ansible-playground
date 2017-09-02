# ansible-playground
Test your ansible plays in a local vm

## Prerequisites
- ansible
- vagrant, also:
```
vagrant plugin install vagrant-vbguest
```
which is needed to update the guest additions for the VM when spawning it
(otherwise you might face networking issues - and the Vagrantfile won't work)
- virtualbox
- The vagrant centos7 box should be downloaded from vagrant cloud automatically)
- more boxes can be found here: https://app.vagrantup.com/boxes/search
- alternatively, use packer to build your own box from scratch https://www.packer.io/intro/index.html. Ideally, download an iso image for your required OS.

You could also put a vagrant.box in the root dir of this project(minor changes to the Vagrantfile are necessary).
Make sure to add to your .gitignore

## Usage
Make changes to playbook.yml in order to test your playbooks.

```
vagrant up
```
will spawn the box and run the ansible script playbook.yml which can be found in the ansible folder.

Once the machine is up use
```
vagrant provision
```
to test changes made to the playbook to avoid having to spawn the vm again.

## playbook
Look at ansible/playbook.yml. All it does right now is making sure nginx and mysql are installed for your vm.
Add packets and configurations accordingly. The ansible documentation is a good place to start http://docs.ansible.com/ansible/latest/index.html

## sources
https://github.com/geerlingguy
