### Gitlab CI Runner setup

----

In order to actually run you tests, you will need to configure a runner.

We have a runner server in our data center on the 3rd floor.

You can access the GitlabCI Runner at [https://gitlabrunner.cs.uno.edu](https://gitlabrunner.cs.uno.edu)

#### Adding a new runner.

After you register and get logged in, you can add runners.

> Gitlab CI just added "shared runners", so you only need to make one for the class. 
> We can use the same runner for each project.

You will need to get a couple of items from GitlabCI.

The URL for the CI server: **https://ci.gitlab.com/**

The token for the runner, which can be found here


![image](http://gdurl.com/C4dq)

After you have those two items you can use the add new runner form to create a new one.

Follow the image below for instructions.

![image](http://gdurl.com/dtrE)

#### Check that the runenr was added

You can then refresh the runners page in GitlabCI to see if the runner has been added.