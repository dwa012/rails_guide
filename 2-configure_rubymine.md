
###Making a new Rails app using the Vagrant Ruby interpreter

>**Note**: There a number of shell commands that you will need to run, which are indicated with the grey background and monospaced text.
>
>Anytime you see the following `<text>`, your are to substitute it with something of your own choosing.  Ex. If you are making a directory for Lab 1 then name it `lab1`,  something so you can tell what the rails app is for.
>
>**Windows users**: You will need to use the Cygwin Terminal app to follow this guide

----------

####Creating the app via the terminal

 - Create a new directory for the your Rails project
```bash
mkdir -p ~/Development/su15/CS4990/<name>
```
- Navigate to the newly created directory
```bash
cd ~/Development/su15/CS4990/<name>
```
- Get the Vagrantfile from the server
```bash
curl -o Vagrantfile http://www.cs.uno.edu/~daniel/boxes/4990_SU15/Vagrantfile
```
- Start the vagrant VM
```bash
vagrant up
```
- Once the VM is booted, open a shell for the VM
```bash
vagrant ssh
```
- Create the Rails app
```bash
rails new ~/workspace
```
- Create and initialize the database
```bash
rake db:create
rake db:migrate
```
- Exit the VM
```bash
exit
```
----------

<!-- the large screenshots are supposed to be 700px wide, the smaller ones are 400px wide -->

##Setting up RubyMine

>We are going setup RubyMine to use the Ruby interepter and Rails enviroment in the vagrant VM. You only need to do this the first time, for each new Rails project.

####**1.** Open RubyMine and open the project folder

![enter image description here](http://gdurl.com/3dWN)

> **Note**: When choosing the app, remember to select the containing folder of the application.

![enter image description here](http://gdurl.com/ioeA)

> **Note**: You will some errors when you first open the project, similar to the following image. You can ignore them, since we are about to fix it in the next step.

![enter image description here](http://gdurl.com/0m3D)
 
####**2.** Next we need to configure the remote Ruby intepreter

- Open the preferences, and navigate to `Ruby SDK and Gems`

> **Tip**: You can use the keyboard shortcurts to open the preferences.
> OSX: `⌘ Comma` , Windows/Linux: `Ctrl+Alt+S` 

- Once you have selected `Ruby SDK and Gems`, add a new remote with the small `+` symbol in step `2` on the following image. Once the menu pops up, select `New remote...` in step 3.
 
![enter image description here](http://gdurl.com/5qDC)

- You should see a popup similar to the following.

![enter image description here](http://gdurl.com/Yro9)

- Select the Vagrant radio button at the top, which should change the popup to look like this.
 
![enter image description here](http://gdurl.com/OFyf)

- In the `Ruby interpreterpath` erase the `/usr/bin/ruby` text and paste the following in.

```bash
/home/vagrant/.rvm/gems/ruby-2.2.2@global
```
- The popup should now be similar to the following.

![enter image description here](http://gdurl.com/jsGc)

- Click `OK` to close the window.

- If it is all correct, then RubyMine should show some progress dialogs while it is setting up the interpreter settings.

----------

##Working with vagrant inside of RubyMine

####**1.** We can start and stop the vagrant VM from within RubyMine, once the previous section is finished

![enter image description here](http://gdurl.com/i9-9)

>If you wish, you can open RubyMine and start/stop the vagrant vm.

####**2.** To open a shell into the VM, we can use the terminal widget in RubyMine which will allow you to perform `vagrant ssh`

![enter image description here](http://gdurl.com/l0Lo)
