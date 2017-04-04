# GET and POST

To interact with the Wikipedia and Twitter APIs, we're going to be using HTTP requests, which are really just a combination of a **url** plus a **method** and sometimes **parameters**. Whenever you use a website, whether clicking in a browser or through an API, you are making HTTP requests.

Here's an example of an HTTP request, where the **url** is "[https://twitter.com/search](https://twitter.com/search)" \(Twitter's search page\), the **method **is GET, and the one **parameter **in the request is "q=pancakes."

```
https://twitter.com/search?q=pancakes
```

Although the url and parameters are easy to see in this example, the method is a little more abstract.

GET and POST are types of HTTP methods. There are several different types of HTTP requests that have different purposes. They are:

* **GET **requests bring data from a website to the person or robot who requested it. For example, if you go to the url [https://en.wikipedia.org/wiki/Pancake](https://en.wikipedia.org/wiki/Pancake), you're just going to get information about pancakes. You're not giving Wikipedia any new information about pancakes. Parameters for GET requests are visible in the url, like we saw earlier with q=pancakes.
* **POST **requests push data from a person or robot to a website. If you go to Twitter to tweet about how much you love pancakes, you're making a POST request. Unlike a GET request, you won't be able to see POST parameters from the url bar of your browser. 



