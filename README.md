# [Packer](http://packer.io) and [Vagrant](http://vagrant.com) presentation

## Setup
Packer and Vagrant will need to be installed for this to work.

* For Vagrant, follow the instructions found here: https://docs.vagrantup.com/v2/installation/index.html
* For Packer, follow the instructions found here: https://packer.io/intro/getting-started/setup.html
  * Make sure you can run packer from the command line. If not, be sure to add it to your system path.
* Install Vagrant and the addons, found here: https://www.virtualbox.org/wiki/Downloads
* Clone this repo

## Running

### Packer
These are instructions to setup your environment to create and push a new vagrant box to your atlas account so others can view it.

#### Setup Atlas (If you want to push to your own repo)
* An atlas account needs to be created. Create one [here](https://atlas.hashicorp.com/account/new)
* Create a new token [here](https://atlas.hashicorp.com/settings/tokens)
* Linux:
  * place this your .profile folder or run it from the command line: `export ATLAS_TOKEN=”<the generated token>”`. If you run it from the command line, be sure to save it somewhere for later use. If you do lose it, you can simply create another one and delete the old one
* Windows:
  * Open up the command prompt and run this: `setx ATLAS_TOKEN <the generated token>`

#### Packer run
* Adjust the values in variables.json to fit your user. For example, change `atlas_username` to your atlas username.
* **To have Atlas build it for you** run this from the root directory
`packer push -var-file=variables.json ubuntu.json`

* **To build it yourself and push to atlas** use this command
`packer build  -var-file=variables.json ubuntu.json`


Atlas also has a great tutorial that can be run from here: https://atlas.hashicorp.com/tutorial/packer-vagrant/1
