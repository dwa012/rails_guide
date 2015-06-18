
### Updating the Vagrant Box

----------

<!-- the large screenshots are supposed to be 700px wide, the smaller ones are 400px wide -->

From time to time your box can be updated with new tools and other fixes.

When you run ``vagrant up`` you will get a message in yellow/gold similar to the following, you can upgrade to  a new build

![enter image description here](http://gdurl.com/Lc9Y)

To update just run ``vagrant box update`` to download the new build.

If the VM is already running, then you may want to do a ``halt`` and then do another ``up`` to make sure all the changes are integrated.