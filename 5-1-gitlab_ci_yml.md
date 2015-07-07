### GitlabCI YAML

----

In order to instruct the CI server what to test we need to add a file to our repository.

GilabCi and similarily Travis CI use a yaml file as the build instructions.

Firstly we need to create the ``.gitlab-ci.yml`` file in the app root.
Everytime we push to our repository, the code will be tested according to the contents of the yaml.

#### .gitlab-ci.yml

For our Rails and Heroku setup, we can use folowwing:

```
before_script:
  - export PATH=~/bin:/usr/local/bin:/usr/bin:/bin:$PATH

spec:
  script:
    - gem install bundler --no-ri --no-rdoc
    - bundle install --without production development test
    - bundle exec rake db:setup RAILS_ENV=gitlabci
    - bundle exec rake db:migrate RAILS_ENV=gitlabci
    - RAILS_ENV=gitlabci bundle exec rspec

heroku:
  type: deploy
  script:
    - gem install heroku
    - heroku git:remote --ssh-git -a $HEROKU_APP_NAME
    - mkdir -p ~/.ssh/
    - echo "Host heroku.com" >> ~/.ssh/config
    - echo "   StrictHostKeyChecking no" >> ~/.ssh/config
    - echo "   CheckHostIP no" >> ~/.ssh/config
    - echo "   UserKnownHostsFile=/dev/null" >> ~/.ssh/config
    - heroku keys:clear
    - echo -e  'y\n' | ssh-keygen -q -t rsa -N "" -f ~/.ssh/id_rsa
    - echo "Y" | heroku keys:add
    - git push heroku master
    - heroku run rake db:migrate
    - heroku restart
```

You will notice that there are a couple of environment variables in this file. 
To make this build script work for all of our projects, we are going to only define the two different items in the following section.

> **Tip** You can validate you yaml file witht the [GitLabCI Lint Tool](https://ci.gitlab.com/lint)