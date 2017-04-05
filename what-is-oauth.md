# What is OAuth?

OAuth is the authentication strategy that we'll be using to post messages on Twitter. It's one of the most common authentication strategies you'll see on an API, aside from just passing in a username and password or a secret token on every request.

OAuth is pretty complicated, and most web developers \(fortunately!\) do not know or need to know exactly how it works in order to use it. Still, it can be useful to have a general idea of how OAuth works. An analogy that I like to use involves getting into your house.

At the end of the last section, you created an access token for your Twitter account. You'll need your Consumer Key, Consumer Secret, Access Token, and Access Token Secret to authenticate. Here's an example set of those values:

![](/assets/Screen Shot 2017-04-04 at 8.50.17 PM.png)![](/assets/Screen Shot 2017-04-04 at 8.50.22 PM.png)

You might be wondering why we couldn't just authenticate with your username and password. Your username and password are like a sledgehammer that can knock down the front door of your house. If someone gets ahold of your username and password, they can knock down your front door and replace it with a different one that you can't open. That's terrible and we don't want that to happen!

Your Access Token and Access Token Secret is like an invitation to a party at your house. If you give it to someone, they can visit and request access to your house. If someone you don't want to come to your party gets ahold of an invitation somehow, you can regenerate or destroy their tokens. We won't be doing this today, but you can make a unique Access Token and Secret for anyone who wants to use your app.

Your Consumer Key and Consumer Secret is like a key to your house. If you lose it or someone steals it, you can just replace the lock and get a new key \(by regenerating the Consumer Key and Secret\). 

In section about making POST requests, we'll use your own "GARP," "PLORP," "FLUMP," and "SKUMP" to request access to Twitter. First we'll need to add those keys to a secret file that only your app can see.

