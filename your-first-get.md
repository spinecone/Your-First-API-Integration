# Your first GET
![](/assets/get.png)

Now that we know how to request a random article from Wikipedia, we can add that behavior to the horoscope app. We'll be using HTTParty, a Ruby library for making HTTP requests.

You can check out the full documentation for HTTParty at [https://github.com/jnunemaker/httparty](https://github.com/jnunemaker/httparty), but for now all you need to know is that to make a GET request, you use `HTTParty.get(url)`. Remember that the url for this request is just the Wikipedia API base url, with the "action" and "list" parameters at the end.

Once you get a response from Wikipedia, you'll need to get the title out of the response hash it returns. The full response contains stuff we don't need like the id of the page.

One thing to note is that HTTParty will return a hash containing the random article data as the response from Wikipedia. If you access the random article url from the browser, you'll see that the text shown there is not exactly a Ruby hash. It's JSON, which is a format that the vast majority of modern APIs use. You can read allllll about JSON at [http://www.json.org/](http://www.json.org/). It doesn't matter to us right now since HTTParty is converting JSON into a hash for us, but keep in mind that JSON is what's being returned by Wikipedia behind the scenes.

Use your new API documentation reading and HTTP requesting skills to change horoscope.rb so that instead of generating a prediction from a list of emoji, it uses a random Wikipedia article title. You shouldn't need to make any changes to index.erb for this, just horoscope.rb.