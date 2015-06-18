
### Alternate RubyMine Vagrant Configuration

----------

<!-- the large screenshots are supposed to be 700px wide, the smaller ones are 400px wide -->

If for some reason RubyMine cannot auto discover the Vagrant configuration, we can enter the information manually.

Select the ``SSH Credential`` option in the remote interpreter dialog, like so.

![enter image description here](http://gdurl.com/Yro9)

Enter the details as follows:

- Host -> ``localhost``
- Port -> ``2222``
  - This will be the port if only one Vagrant VM is running, otehrwise it will print the port when the VM is booting up.
- User name -> ``vagrant``
- Password -> ``vagrant``

The ``Ruby interpreter path`` is the same as the regula guide..