# Toolchain

## Requirements

You need the following software to use, configure and update the Toolchain box.

#### VirtualBox including Extension Pack ( Version: 4.3.14 )

VirtualBox is a virtualization software that is used by Vagrant to supply environments. You also need the respective Oracle VM Extension Pack. The software and extension pack is available for download on the following url:

[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

#### Vagrant ( Version: 1.6.2 )

Vagrant is a software for managing virtual environments. It is used to setup, start and stop the virtual toolchain machine.
The software is available for download on the following url:

[http://www.vagrantup.com/](http://www.vagrantup.com/)

## How to use the Toolchain box

Using the Toolchain box is quite easy. All you need is a Vagrantfile and some patience. Vagrant will download and start your box. The rest is up to you. Login in do some cool stuff.

### Vagrantfile

A Vagrantfile is used to describe the type of machine (Toolchain) required for a project. Use the following command to create a Vagrantfile for your project.

	$ vagrant init orlandohohmeier/toolchain

#### Example (minimal Vagrantfile)

	# -*- mode: ruby -*-
	# vi: set ft=ruby :

	# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
	VAGRANTFILE_API_VERSION = "2"
	Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
	  	config.vm.define "toolchain" do |toolchain|
	  		toolchain.vm.box = "orlandohohmeier/toolchain"
	  	end
	end

For a detailed introduction and list of available configuration options please see:
https://docs.vagrantup.com/v2/vagrantfile/](https://docs.vagrantup.com/v2/vagrantfile/)

### Start, Stop, …

Use the following command to download, create and configure the Toolchain machine.

	$ vagrant up
	
If you want to start over, use the following command to shut down the running Toolchain and destroys all resources that were created during the machine creation process.

	$ vagrant destroy
	
For a full list of commands and options please see:

[https://docs.vagrantup.com/v2/cli/index.html](https://docs.vagrantup.com/v2/cli/index.html) 

### Login and do something cool

Login in using the following command. This will SSH into the running Toolchain machine and give you access to a shell.

	$ vagrant ssh

## How to update the Toolchain box

Updating packages, installing new software and changing the machine configuration is not hard. All you need to do, is to follow this few steps:

1. Import the Toolchain
2. Start the Toolchain 
3. Login to the machine
4. Update/alter some surf
5. Export and package the machine

### Import the Toolchain machine

Use the following command to import the Toolchain machine. This will add the machine to VirtualBox.

	$ ./toolchain import

### Start machine
	
Start the Toolchain machine with the following command. 

	$ ./toolchain start
	
### Stop machine
	
Use this command to start the Toolchain machine. 
	
	$ ./toolchain stop 

### Login to the machine

Login in using the following command. This will SSH into the running Toolchain machine and give you access to a shell.
	
	$ ./toolchain login

### Alter the welcome message	

Use the following command to alter and sync the SSH welcome message.
		
	$ ./toolchain motd
	
### Export and package the machine

Export and package the machine state using this command.
	
	$ ./toolchain export

### Share some love

Please commit your changes and share your updated box with the world!


## Specification

* Ubuntu Server 64-bit
* 1024 MB RAM
* 4.00 GB Disk space
* Minimal virtual machine installation

### Software

* Git 1.9.1
* SVN 1.8.8
* cURL 7.35.0
* CMake 2.8.12.2
* VIM 7.4.52
* Ruby 2.1.3
* Bundler 1.7.0
* Python 2.7.6
* NodeJS 0.10.32
* NPM 1.4.28
* Bower 1.3.12
* Grunt 0.1.13
* Gulp 3.8.7
* Java 1.7.0_65
* PHP 5.5.9

## Next steps

* Try to reduce the machine size even further
* Evaluate [Packer](http://www.packer.io/) for machine building
* Try different approaches to create a virtualized, encapsulated toolchain environment
* Do some other crazy cool stuff. :)
   	
## Authors

* Tobias Althoff, @____tobi
* Orlando Hohmeier, @orlandohohmeier
 
## License

MIT license
