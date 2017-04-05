# What is OAuth?

OAuth is the authentication strategy that we'll be using to post messages on Twitter. It's one of the most common authentication strategies you'll see on an API, aside from just passing in a username and password or a secret token on every request. 

OAuth is pretty complicated, and most web developers \(fortunately!\) do not know or need to know exactly how it works in order to use it. Still, it can be useful to have a general idea of how OAuth works. An analogy that I like to use involves getting into a locked house.

At the end of the last section, you created an access token for your Twitter account. You'll need your Consumer Key, Consumer Secret, Access Token, and Access Token Secret to authenticate. Here's an example set of those values:

![](/assets/Screen Shot 2017-04-04 at 8.50.17 PM.png)![](/assets/Screen Shot 2017-04-04 at 8.50.22 PM.png)

You might be wondering why we couldn't just authenticate with your username and password. 

