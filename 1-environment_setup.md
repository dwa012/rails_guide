###Configuring your computer and environment

>**Note**: There are number of steps here. 
> There is a specific set of instructions for Windows users that need to be followed.

----------

####Download the 3 initial tools

- Download and install Virtualbox
	- https://www.virtualbox.org/wiki/Downloads

- Download and install Vagrant
	- http://www.vagrantup.com/downloads

- Download and install RubyMine
	- https://www.jetbrains.com/ruby/
	- You can get a free student license by applying here https://www.jetbrains.com/student/

####Pre-download the vagrant box

```bash
vagrant box add --force --clean "dwa012/4990_SU15" http://www.cs.uno.edu/~daniel/boxes/4990_su15.json
```

#####All set, if you are on OSX
>Windows users continue to the next section

----------

####Windows Specific Steps

- Install Cygwin

	- Use the following as a general guide
		- http://www.cs.uno.edu/~jfinigan/Installing_Cygwin.pdf 
	- On step 7, you need to install an additional tool `curl`
		- `curl` will also be under the `Net` category
	- On step 8, I suggest you install `Vim` instead of `Emacs`. 
- Once Cygwin is installed you will have a the `Cygwin Terminal` application on your Desktop

	- You will be using the app for all shell/terminal commands for the class

#####Configure the Cygwin environment

- Open the `Cygwin Terminal` app

- Setup the home in the shell to be your Windows home

```bash
echo "db_home: windows" >> /etc/nsswitch.conf
```

- Close the `Cygwin Terminal` app

- Open RubyMine so we can change the terminal widget to use Cygwin

- Open Settings
```
File->Settings
```
- Search for `terminal`

- Select the 3 dots button, in step 2 of the following image
 
![enter image description here](http://gdurl.com/FOZT)	

- Navigate and select the Cygwin.bat file, as in the following image
 
![enter image description here](http://gdurl.com/uLVI)