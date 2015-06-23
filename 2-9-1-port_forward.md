## Port Forward Error

---


#### Issue

You may at times get an error when starting a vagrant vm similar to this:

```
Vagrant cannot forward the specified ports on this VM, since they
would collide with some other application that is already listening
on these ports. The forwarded port to 5432 is already in use
on the host machine.
 
To fix this, modify your current projects Vagrantfile to use another
port. Example, where '1234' would be replaced by a unique host port:
 
  config.vm.network :forwarded_port, guest: 5432, host: 1234
 
Sometimes, Vagrant will attempt to auto-correct this for you. In this
case, Vagrant was unable to. This is usually because the guest machine
is in a state which doesn't allow modifying port forwarding.
```

For our class this will usually mean that another VM is still running somewhere.


#### Solution

You may need to open the VirtualBox GUI to see what VMs are running.

When you have it open, there will be a list to the left that has all the VMs registered on your computer.

Find one that says it is running and suspend it. Similar to the following image:

![](http://gdurl.com/R759)