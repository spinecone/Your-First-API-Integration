# Your first POST

![](/assets/post.png)

We can now move on to posting messages on Twitter from your app! This will require 2 changes, **a new method in horoscope.rb** and **a new button in index.erb.**

For the new method in horoscope.rb, you'll need to define a new POST url. It will use the same syntax as the existing `get '/'` url, but with 'post' instead of 'get' and with a different url.

Next, you'll use the oauth gem to generate a new access token using all 4 of the keys you put in your .env file. Then, you'll make a POST request to Twitter which includes the new access token and the message you want to send. You aren't actually going to need HTTParty at all for this part since you can make POST requests by using the oauth gem alone.

## Using the oauth gem

[ The GitHub page for the oauth gem](https://github.com/oauth-xx/oauth-ruby) has examples and background information about using OAuth. It isn't important right now but you can read it if you're interested in learning more. For our purposes, you just need to copy the template below into horoscope.rb:

```
consumer = OAuth::Consumer.new(
  api_key, api_secret,
  { site: 'https://www.blah.gov', scheme: 'header' }
)
token_hash = { oauth_token: access_token, oauth_token_secret: access_token_secret }
access_token = OAuth::AccessToken.from_hash(consumer, token_hash )
access_token.request(:post, 'https://www.blah.gov/api/do_something', parameter_name: parameter_value)
```

You'll need to replace `api_key`, `secret`, "https://www.blah.gov", "access\_token", "access\_token\_secret_", _"https://www.blah.gov/api/do_something", "parameter\_name", and "parameter\_value" with the correct values for the horoscope app. We'll learn how to get those values in the next section.

## Using the Twitter API

To find the correct urls to pass in to OAuth, we'll need to consult [the Twitter API documentation](https://dev.twitter.com/rest/public). Like the Wikipedia API documentation, the home page has a lot more information than we need to read right now. If you click on "Reference Documentation," you'll see a list of all the different requests we can make on the Twitter API. The one we want to read about right now is "POST statuses/update." If getting to that page seemed like a confusing process, you could also google "twitter api post tweet" and get to that page much faster \(it's an unfortunate reality that sometimes Google is the easiest way to get what you want out of API documentation\).

![](/assets/Screen Shot 2017-04-04 at 11.53.37 PM.png)

There are 2 pieces of information we need from this page: the **resource url **and the **required parameters. **We will take the part of the resource url up to ".com" \(this is called the "hostname" of the url\) and use that as the "site" parameter of OAuth::Consumer.new. We'll take the rest of the resource url \(this is called the "path"\)  and use that to call `access_token.request` instead of "https://www.blablabla.gov/api/do_something."

We'll also need to pass required parameters to `access_token.request`. The API documentation shows that there's just one required parameter, the message itself. Use the name of that parameter as the key, and the message as the value. Now you're ready to POST!

# Adding a button

The last thing we'll need to do is add a button to index.erb that will post your message to Twitter. If you're not familiar with making buttons in HTML, they usually look like this:

```
<form method="post" action="some url">
    <input name="some name" value="some value">
    <button type="submit">Here's my button!</button>
</form>
```

This sets up a form that sends data from all of the inputs inside of it to the url at "some url" when the submit button is clicked. You'll need to change the action to the name of the POST method you added to horoscope.rb, and pass in @prediction as the value to your input. You can add `type="hidden"` to the input so that it doesn't show up as a form field on your page.

Now when you click on the submit button, your post method will be able to access the value for input some\_name through the params hash with `params[:some_name].`

🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨🤖✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖


