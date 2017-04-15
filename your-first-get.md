# Your first GET
![](/assets/get.png)

Now that we know how to request a random article from Wikipedia, we can add that behavior to the horoscope app. We'll be using **HTTParty**, a Ruby library for making HTTP requests.

You can check out the full documentation for HTTParty at [https://github.com/jnunemaker/httparty](https://github.com/jnunemaker/httparty), but for now all you need to know is that to make a GET request, you use `HTTParty.get(url)`. Remember that the url for this request is just the Wikipedia API base url, with the **action**, **list**, and **rnnamespace** parameters at the end.

**Note: if you're using a Windows computer,  you'll need to add the parameter `verify: false` to all of your HTTParty requests, so your request will look like `HTTParty.get(url, verify: false)`**

Once you get a response from Wikipedia, you'll see that the response includes text that says:
```
This is the HTML representation of the JSON format.
HTML is good for debugging, but is unsuitable for application use.
Specify the format parameter to change the output format.
To see the non-HTML representation of the JSON format, set format=json.
```
This means we'll need one more parameter in our url, the format. **JSON** is a format that the vast majority of modern APIs use. You can read allllll about JSON at [http://www.json.org/](http://www.json.org/). It doesn't matter to us right now since HTTParty will turn the JSON response into a Ruby hash for us, but keep in mind that JSON is what's being returned by Wikipedia behind the scenes.

Finally, you'll need to get the title out of the response hash it returns. The full response contains stuff we don't need like the id of the page. If you're not very familiar with Ruby hash syntax, you can take a look at this tutorial on Hashes: https://www.tutorialspoint.com/ruby/ruby_hashes.htm

Use your new API documentation reading and HTTP requesting skills to change horoscope.rb so that instead of generating a prediction from a list of emoji, it uses a random Wikipedia article title. You shouldn't need to make any changes to index.erb for this, just horoscope.rb.