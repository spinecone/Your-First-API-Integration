# Your first POST

Now you're ready to post messages on Twitter from your app! This will require 2 changes, **a new method in horoscope.rb** and **a new button in index.erb.**

For the new method in horoscope.rb, you'll need to use the oauth gem to generate a new access token using all 4 of the keys you put in your .env file. Then, you'll make a POST request to Twitter which includes the new access token and the message you want to send. You aren't actually going to need HTTParty at all for this part since you can make POST requests by using the oauth gem alone.

If you visit[ the GitHub page for the oauth gem](https://github.com/oauth-xx/oauth-ruby), you'll see an examples of how to use it in the "Demonstration of Usage" section. There's a lot of information here, but again, oauth is a complicated thing that you don't need to worry about understanding fully! You can ignore the parts about sessions, setting a callback url, and redirecting since that assumes your app has users that can log in and out. Without those parts, we're left with:

```
consumer = OAuth::Consumer.new("key","secret", :site => "https://agree2")
hash = { oauth_token: "token", oauth_token_secret: "token_secret" }
request_token  = OAuth::RequestToken.from_hash(consumer, hash)
access_token = request_token.get_access_token
photos = access_token.get("/photos.xml")
```

You can use all of that code as-is. You'll just need to replace "key", "secret", "https://agree2", token, token\_secret, and "/photos.xml" with the correct values for the horoscope app.

