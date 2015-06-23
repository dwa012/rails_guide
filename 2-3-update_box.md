## Updating the Vagrant Box

----------

<!-- the large screenshots are supposed to be 700px wide, the smaller ones are 400px wide -->

From time to time your box can be updated with new tools and other fixes.

When you run ``vagrant up`` you will get a message in yellow/gold similar to the following, you can upgrade to  a new build

![enter image description here](http://gdurl.com/Lc9Y)

To update just run ``vagrant box update`` to download the new build.

---------- 

#### Rebuild the Vagrant Box

You will have to do a ``vagrant destroy`` so you can rebuild the box with the new changes.

> **Warning**: The destroy will completley erase the VM including the database.

To use the new box, run the following set of commands on your host machine

```
vagrant destroy
vagrant up
vagrant ssh -c "cd ~/; bundle install; rake db:create; rake db:migrate"
```