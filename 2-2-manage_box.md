## Managing the VM

----

We are going to use Vagrant to manage the VM as far as we are concerned.
The execution environment for the VM is handled by VirtualBox for us.

#### Starting the VM

To start the VM we will do the following:

```
vagrant up
```

This will boot and configure the VM acccording to the Vagrantfile.

#### Suspending the VM

When you are done with development for a while, it is a good idea to suspend the VM. This will prevent your laptop battery from draining too quickly when not developing.

```
vagrant suspend
```

This will save the state of the VM and stop it from running.

#### Stoping the VM

If you need to issue the shutdown command in the VM:

```
vagrant halt
```

This completly shutsodwn the VM and the next time you do an ``up`` it will take a bit longer than from a ``suspend``.

#### Destroy the VM

If you run into issues, often you can destroy the VM and restart.

> This is one of the big advantages to Vagrant

**WARNING: This will delete the VM and all data with it. Including the database that is in the VM**

```
vagrant destroy
```

It will ask you for a confirmation, before it deletes the VM.