## Vagrantfile

---

The ``Vagrantfile`` is how ``vagrant`` knows how to provision the VM and configure settings for it.

The Vagrant file we are using is as follows:

```
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Don't provision using this file; it's only for packaging with the image.

Vagrant.configure('2') do |config|
  config.vm.box = "dwa012/4990_SU15"
  config.vm.box_url = "http://www.cs.uno.edu/~daniel/boxes/4990_su15.json"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 5432, host: 5432
 
  config.vm.network :private_network, ip: '192.168.50.50'
  config.vm.synced_folder '.', '/vagrant', nfs: true
 
  config.vm.provider :virtualbox do |v, override|
    v.gui = false

    # Linked clones for extremely fast import of machines
    v.linked_clone = true
    
    # box customizations for speed
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--audio", "none"]
    v.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
    v.customize ["modifyvm", :id, "--usb", "off"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end
end

```

- ``config.vm.box`` -> specifies the base VM that we are using
- ``config.vm.box_url`` -> specifies where to get the information about the URL
- ``config.vm.network`` -> specifies the ports to forward from the host to the guest so we can access specific resources in the guest machine.
	- Port 3000 is the where Rails is serving its content.
	- Port 5432 is the default PostgreSQL port.