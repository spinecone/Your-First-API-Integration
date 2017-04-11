# Your first POST
![](/assets/post.png)

We can now move on to posting messages on Twitter from your app! This will require 2 changes, **a new method in horoscope.rb** and **a new button in index.erb.**

For the new method in horoscope.rb, you'll need to use the oauth gem to generate a new access token using all 4 of the keys you put in your .env file. Then, you'll make a POST request to Twitter which includes the new access token and the message you want to send. You aren't actually going to need HTTParty at all for this part since you can make POST requests by using the oauth gem alone.

## Using the oauth gem

If you visit[ the GitHub page for the oauth gem](https://github.com/oauth-xx/oauth-ruby), you'll see an examples of how to use it in the "Demonstration of Usage" section. There's a lot of information here, but again, OAuth is a complicated thing that you don't need to worry about understanding fully! You can ignore the parts about sessions, setting a callback url, and redirecting since that assumes your app has users that can log in and out. Without those parts, we're left with:

```
consumer = OAuth::Consumer.new("key","secret", site: "https://agree2")
hash = { oauth_token: "token", oauth_token_secret: "token_secret" }
request_token  = OAuth::RequestToken.from_hash(consumer, hash)
access_token = request_token.get_access_token
photos = access_token.post("/photos.xml", parameter_key: parameter_value)
```

You can use all of that code as-is. You'll just need to replace "key", "secret", "[https://agree2](https://dev.twitter.com/rest/reference/post/statuses/update)", token, token\_secret_, _"/photos.xml", parameter\_key, and parameter\_value with the correct values for the horoscope app.

## Using the Twitter API

To find the correct urls to pass in to OAuth, we'll need to consult [the Twitter API documentation](https://dev.twitter.com/rest/public). Like the Wikipedia API documentation, the home page has a lot more information than we need to read right now. If you click on "Reference Documentation," you'll see a list of all the different requests we can make on the Twitter API. The one we want to read about right now is "POST statuses/update." If getting to that page seemed like a confusing process, you could also google "twitter api post tweet" and get to that page much faster \(it's an unfortunate reality that sometimes Google is the easiest way to get what you want out of API documentation\).

![](/assets/Screen Shot 2017-04-04 at 11.53.37 PM.png)

There are 2 pieces of information we need from this page: the **resource url **and the **required parameters. **We will take the part of the resource url up to ".com" \(this is called the "hostname" of the url\) and use that as the "site" parameter of OAuth::Consumer.new. We'll take the rest of the resource url \(this is called the "path"\)  and use that to call `access_token.post` instead of "/photos.xml."

We'll also need to pass required parameters to `access_token.post`. The API documentation shows that there's just one required parameter, the message itself. Use the name of that parameter as the key, and the message as the value. Now you're ready to POST!

# Adding a button

The last thing we'll need to do is add a button to index.erb that will post your message to Twitter. If you're not familiar with making buttons in HTML, they usually look like this:

```
<form method="post" action="some url">
    <input name="some name" value="some value">
    <button type="submit">Here's my button!</button>
</form>
```

This sets up a form that sends data from all of the inputs inside of it to the url at "some url" when the submit button is clicked. You'll need to change the action to the name of the POST method you added to horoscope.rb, and pass in @prediction as the value to your input. You can add `type="hidden"` to the input so that it doesn't show up as a form field on your page.

🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨🤖✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 ✨ 🤖 

That's it! You now have the power to use any API to make any weird thing you want. May all of your GET and POST dreams come true.

