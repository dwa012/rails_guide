### Adding Gravatar for Users
 
----------

#### Add the method to the UsersHelper

We will need to make some small modifications to our existing app

```
Module UsersHelper

  # Returns the Gravatar for the given user.
  #
  # @param [User] user
  # @param [Hash] options
  def gravatar_for(user, options = {}) 
    options = { 
        size: '200',
        default_icon: 'identicon',
        rating: 'pg'
    }.deep_merge(options)

    gravatar_id = Digest::MD5::hexdigest(user.email.downcase)
    gravatar_url = "https://secure.gravatar.com/avatar/#{gravatar_id}?r=#{options[:rating]}&s=#{options[:size]}&d=#{options[:default_icon]}"
    image_tag(gravatar_url, alt: user.first_name, class: "gravatar")
  end 
end

```

This method will be available in our view templates.

----------

#### Use the method to get the image for a user

Every where that you want to get a Gravatar, you can do the following

```
<%= gravatar_for(user) %>
```