# Windows templates for Packer 

## Introduction
This repository contains Windows templates that can be used to create boxes for Vagrant using Packer.
It is inspired by 
- [https://github.com/mwrock/packer-templates](https://github.com/mwrock/packer-templates)
- [https://github.com/MattHodge/PackerTemplates](https://github.com/MattHodge/PackerTemplates)
- [https://github.com/jacqinthebox/packer-templates](https://github.com/jacqinthebox/packer-templates).


## How to

### Prerequisites
The Windows boxes are created with Packer version 1.5.1 and are using WinRM.
[Vagrant](https://www.vagrantup.com), [Packer](https://www.packer.io) and Virtualbox.

**Linux:**
Install them with your package provider or manually, for example like so:

```bash
wget https://releases.hashicorp.com/vagrant/2.2.6/vagrant_2.2.6_linux_amd64.zip
unzip vagrant_2.2.6_linux_amd64.zip
sudo mv vagrant /usr/local/bin

wget https://releases.hashicorp.com/packer/1.5.1/packer_1.5.1_linux_amd64.zip
unzip packer_1.5.1_linux_amd64.zip
sudo mv packer /usr/local/bin
```

**Windows VirtualBox:**

You can install the prerequisites with packagemanagement:
```Powershell
Install-Package -ProviderName Chocolatey -ForceBootstrap -Force vagrant,virtualbox,packer
```


### Clone and run

Clone the repository:
```
git clone https://github.com/urskog84/packer-templates.git; cd packer-templates
```

### Create a box

Create a Windows 10 box:   

```bash
packer build --force virtualbox_windows_10_tscl.json
```

### Add box to (local) Vagrant
vagrant box add --name win_10_ltsc windows_10_virtualbox_ltsc.box