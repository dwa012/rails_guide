## Deploy Your App to Heroku

----

We will use ``git`` to push our changes to the server.
When we did the ``heroku create``, it added a git remote named ``heroku`` 

#### Deploy the app to the Heroku server

Pshing to to the ``heroku`` remote will trigger the app to build on the heroku server.

```
git push heroku master
```

> Keep an eye for errors, if you see an ``exit code`` and it is not ``0``, then there was an error deploying the application.


#### Migrate the database

We need to ensure that any pending migrations are ran properly.

```
heroku run rake db:migrate
```

#### Restart your application

This step will not always be needed, but is a good idea to restart in case there were any configuration changes.

```
heroku restart
```