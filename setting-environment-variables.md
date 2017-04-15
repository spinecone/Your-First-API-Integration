# Setting environment variables

To authenticate with Twitter, your app will need to reference the keys we discussed in the last section. However, you shouldn't write code that looks like `Twitter.authenticate(token: 'my actual token')` \(this isn't real working code, btw\). That would mean that if you ever shared your code with someone else, they could steal your authentication tokens.

Instead, we're going to store these keys in a file named **.env**. In the introduction I mentioned that this file isn't included in the template, so you'll need to add it yourself. It should end up looking something like this:

 ![](/assets/Screen Shot 2017-04-04 at 9.53.19 PM.png)

Since the **dotenv **gem is loaded in horoscope.rb, you'll be able to access these tokens from there by using the ENV hash. For example, to use the `API_KEY` token, you'll use `ENV['API_KEY']`.

Add your authentication secrets to a new .env file, and test that you can access them from horoscope.rb.

**It's very important that you do not commit your .env file to GitHub! If you do, anyone in the world can use this information to post tweets on your behalf. **If you're planning on committing your changes, create a .gitignore file and add .env to it. This will ensure that it will not be tracked on GitHub.

