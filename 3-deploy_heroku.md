###Configuring and deploying to Heroku

>**Note**: You will need a [Heroku](http://heroku.com) account for this tutorial 

----------

####Configuring Herkou for an existing Rails app

We will need to make some small modifications to our existing app

>**Note**: If this is the first time you are using Heroku for a project, you will need execute the folowing to login to Heroku.
>```bash
>heroku login
>```

#### Create a ``git`` repository, if you don't have one already
```bash
git init
curl -o .gitignore https://cdn.rawgit.com/dwa012/794d1bf61602689e0b32/raw/
git commit -a -m 'First Commit'
```
#### Add the 12 factor gem to the ``Gemfile``
- Open the ``Gemfile`` in RubyMine and paste this at the bottom
```ruby
gem 'rails_12factor', group: :production
```

####Update the ``config/database.yml`` to have the proper production settings
- Change the following at the bottom of the file
```yaml
production:
    <<: *default
    database: workspace_production  
    username: workspace
    password: <%= ENV['WORKSPACE_DATABASE_PASSWORD'] %>
```
- To this
```yaml
production:
    <<: *default
    url: <%= ENV['DATABASE_URL'] %>
```

####Create the Heroku app
```bash
heroku create
```
> **Note**: The web address will print to screen, so take note of the location so you can view it.

####Deploy the app to the Heroku server
```bash
git push heroku master
```
####Migrate the database
```bash
heroku run rake db:migrate
```
####Restart your application
```bash
heroku restart
```