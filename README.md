## Vagrant Quickstart Project

# VAGRANT Recap:

** Start your vagrant project by making a new directory

mkdir `<project folder>` 

## vagrant init >> creates a Vagrantfile with default settings

### Add boxes info
* Ubuntu/precise64
* Ubuntu/trusty64

** Where to find more boxes? 

http://vagrantbox.es

>vagrant up - starts up the VM

### vagrant + following:

* box list - list the currently available and downloaded boxes

* box remove <name> —box-version <version>

*version - current vagrant version

*status -current state of vagrant vm

*suspend

*resume

*halt

*reload

*destroy

## To make custom vagrant boxes:

This will preserve the changes to vagrant boxes between destroys

Step 1. Make sure package manager are updated, 
>sudo apt-get update
> sudo apt-get upgrade

Step 2. Install git as an example
>which git - should return nothing
>sudo apt-get install git
>which git
/usr/bin/git 
>git version
>exit

Step 3. Save updated VM as a package
>vagrant package - will create a default package.box
>vagrant package —output custom-trusty.box

Step 4. Add the new box to the box list
>vagrant box add Custom-Trusty custom-trusty.box
>vagrant box list - will list the newly added customized VM

## After creating the new package SSH stopped working
Solution: Add config.ssh.insert_key = false to Vagrantfile before packaging

##ubuntu boot log file at /var/log/boot.log

Provisioning with Vagrant
Supported: Chef, Puppet, Ansible, etc
Bash as well
