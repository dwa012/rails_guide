### GitlabCI Environment variables

---

In order to resuse the buidl script from the previous section we are going to configure a set of environment variables per project.

---

#### Heroku API Key

We will add our API Key from Heroku first. This will be the same on all of our projects.

When you are logged into Heroku you need to go to the "Manage your account" section.

![image](http://gdurl.com/934u)

Once you are there, scroll down a bit to the API key section. And select "Show API Key..."

![](http://gdurl.com/6SWG)

Copy the displayed value.

#### Adding the key to your GitlabCI project

Open the project from GitlabCI and go to the ``Variables`` section.

We will go ahead and add 2 new variables.

The first will be the ``HEROKU_API_KEY``.

![](http://gdurl.com/MCNE)

The value will be the eky we copied from the previous section.

Next we will add the ``HEROKU_APP_NAME`` variable. The value here will be the name of the heroku app that you have already created.

![](http://gdurl.com/rIhGY)